# bruce-embedded-firmware-record

The record a firmware image built on [bruce-esp-idf](https://github.com/bruceskingle/bruce-esp-idf) carries of the
board it was built for, the firmware and its version. A flasher, e.g.
[bruce-embedded-flash](https://github.com/bruceskingle/bruce-embedded-flash), reads it from the image and from the
firmware already on a board, before flashing, and refuses to flash firmware built for another board: a wrong board's
firmware drives the wrong pins, and can damage it.

The record is put in ESP-IDF's `.rodata_custom_desc` section, straight after the app descriptor at the start of the
app image, so that a flasher finds it in the first few hundred bytes, read over the serial port from the ROM
bootloader, whether or not the firmware runs. It starts with a magic string, so that it can be told from anything
else there.

It is `no_std`, with no dependencies, so that both the firmware and a flasher on a computer use it.

License
=======

Licensed under either of

* Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
* MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

Contribution
------------

Unless you explicitly state otherwise, any contribution intentionally
submitted for inclusion in the work by you, as defined in the Apache-2.0
license, shall be dual licensed as above, without any additional terms or
conditions.
