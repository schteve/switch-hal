# switch-hal

Switch-HAL is a `no_std` embedded Rust library for working with buttons, switches, LEDs, and transistors.
Basically, anything that acts like a switch, whether an input or output.

It is both a driver that uses the `embedded-hal::digital` traits and is an abstraction in it's own right.
It provides a simple, zero-cost, abstraction to clarify the _intent_ of your application code.

## Why Switch-HAL? Why not just use raw GPIO?

Did you mean to drive that line high?  
Or did you mean to _turn that LED off_?  
Wait a second... is that LED active _high_?  
Where's the schematic?  
Okay... cathode is wired to the input line... that means it's active low.

Now repeat this every place in your code where you need to turn that LED on or off.  
What happens when the hardware changes?  
Using the raw GPIO to set pins high and low will have you making changes all over your code base.

Wouldn't it be nicer if you only had to think about that once, when you initialize your application,  
and from then on out, simply called `led.on()` or `led.off()`.  
Having an abstraction at the proper level reduces cognitive load.  
Specifying whether a simple peripheral is active high or low in a single place in your application reduces the maintenace burden.

The target audience for this library is:
- Application developers
- Board Support Package developers

## Documentation

https://docs.rs/crate/switch-hal

## License

Licensed under either of

- Apache License, Version 2.0 ([LICENSE-APACHE](./LICENSE-APACHE) or
  http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](./LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

## Architectural Decision Records

Major design decisions are tracked in the [adr](./adr) directory.