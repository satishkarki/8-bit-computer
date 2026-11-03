## [Tri-State Buffer](https://youtu.be/faAjse109Q8?si=GxSNrjkaNE9UZHme)
A bus connects several registers, such as the ALU register, the address register, and the RAM register. But only one of them can put its value on the bus at a time.

So far, we’ve treated the output of a latch or flip-flop as either high or low, 1 or 0. That works for digital logic, but what does it mean electrically? Inside a logic gate, transistors steer current in one of two directions. This is where the terms source and sink come in:

* `Source`: current flows out of the output pin into the load. The chip is supplying current.
* `Sink`: current flows into the output pin and through the chip to ground. The chip is absorbing current.

A high output means the pin is sourcing, and a low output means the pin is sinking. That is the key to the bus problem. You might think the other registers can simply output 0 while one register drives the bus. But a low output is not “off”. It actively pulls the line to ground. If one register drives the bus high while another drives it low, one is sourcing current while the other sinks it, and the two fight each other.

A tri-state buffer solves this by adding a third output state: high impedance (Hi-Z), where the output is electrically disconnected from the bus. Each register connects through a tri-state buffer, and only the selected register’s buffer is enabled. All the others sit in Hi-Z and stay out of the way.

![Tri-State Buffer](Image-assets/part-3-bus-architecture/tristate_buffer.webp)

Here is the datasheet of [SN54 / 74LS24](https://www.amigawiki.org/lib/exe/fetch.php?media=de:parts:74ls245_motorola_datasheet.pdf) octal bus transreciever that Ben Eater explains in his [Tri-state Logic video](https://youtu.be/faAjse109Q8?si=GxSNrjkaNE9UZHme).

## [Designing and building 1-bit register](https://youtu.be/-arYx_oVIj8?si=bSJsu6Qh4PgKhjuh)








