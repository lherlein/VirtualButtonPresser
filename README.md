# What

A rig for testing gpio inputs, such as button presses, automatically. (Without having to physically push the button.)

# Why 

A testing rig like this can be used for a multitude of projects to test button presses without actually having to press the button, but my reason for doing it is so that I can test robotics software quickly and efficiently.

# How

My plan is to use a beaglebone black board to push GPIO inputs into a  PCAL6416A chip. The beaglebone and PCAL chip each have 16 GPIO I/O. The beaglebone will receive commands from the network on which GPIO pin to power, and when the PCAL chip receives that command it will be as if a button was pressed. 

# Hardware

This project uses two parts, the first being the beaglebone black. The beaglebone is kind of like a raspberry pi, except better. The beaglebone black is is more powerful, much easier to set up, and has more than 8 times the GPIO I/O capabilities as the Raspberry pi, for only $10 more. Furthermore, the Beaglebone Black has a faster processor using the ARMv7 processor instructions, as opposed to the Pi’s dated ARMv6. The benefits of the better processor is long, but in general it means much better performance. Even if the Pi’s processor was overclocked to the same clock speed as the beaglebone black, the Black’s processor is still almost twice as fast as the Pi’s. The other chip is the PCAL6416A. This chip is a 16 bit GPIO port expander, which is important for robotics because it can support 16 GPIO pins with just a few wires - this is especially useful for water based robots because it limits the amount of hull penetrations. Another nice feature of this chip is level shifting, making it easy to use the 5V GPIO pins on just about any connection. By connecting this chip to the Beaglebone Black, and writing some pretty simple code, I can create my “virtual button presser.”

