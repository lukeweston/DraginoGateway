
This Arduino-compatible board is designed to be mounted on top of a Dragino, just like the Flukso daughterboard for Dragino, except larger. (It's approximately the same size
as the Dragino.)

It incorporates an ATmega328 clocked at 16 MHz (compatible with Arduino bootloader) and Arduino-compatible shield headers. Programming and serial communications with the AVR
can be done via a standard 6-pin FTDI serial cable or equivalent.

The board includes a socket for an XBee module (or any similar "Bee" module with serial communications and a compatible pinout), with the XBee serial port connected to
Arduino-equivalent pins 2 and 3. Arduino-equivalent pins 0 and 1 are connected to the UART of the AR2317 chipset on the Dragino.

The board incorporates two sensors - a light dependant resistor and a DS18B20 temperature sensor. A micro-SD card socket is also included, with the SD card's SPI
bus connected to four of the AR2317's GPIO libraries.

The five "+" inputs on the Dragino input terminal block are connected to the AVR's ADC input pins 1-5. (Pin 0 is used for the LDR). These inputs are connected through
1:4 voltage dividers, meaning that they can read voltage inputs between 0-20 V, and they include additional resistors and 5.6 V Zener diodes to clamp each line, so the
AVR is protected against overvoltages being connected on these inputs. The five "-" inputs are connected to ground.

The "A" and "B" terminals on the terminal block are connected to +12V and an open-collector transistor output respectively, allowing those two terminals to be connected up
to drive a 12V relay, or any other such moderately-low-power 12V device.

12V DC power is supplied to the board, along with the Dragino's regulated 5 V and 3.3 V rails, via the Dragino. 

No display or touchscreen is included, because in the future we presume we will be eventually developing an Arduino GLCD shield anyway, with a dedicated on-board
microcontroller to handle the GLCD and touchscreen, and this can just be plugged into the Arduino shield headers or something like that.

With the exception of the microSD card socket, there are no surface-mount components on the board.

Arduino-equivalent shield pin:		Function:
------------------------------		---------
0					Microcontroller RXD, TXD from Dragino
1					Microcontroller TXD, RXD into Dragino
2					Soft-serial RXD for TX data from XBee
3					Soft-serial TXD for RX data into XBee
4					Not used.
5					OneWire bus (DS18B20 temp sensor)
6					Relay or digital transistor output
7					Not used.
8					Not used.
9					Not used.
10					Not used. Usually SPI chip select.
11					Not used. SPI MOSI for shield devices.
12					Not used. SPI MISO for shield devices.
13					Blinkenlichten. SPI clock for SPI shield devices.
A0					Analog output from LDR
A1					Analog input 1 (from terminal block, attenuated and protected.)
A2					Analog input 2 (from terminal block, attenuated and protected.)
A3					Analog input 3 (from terminal block, attenuated and protected.)
A4					Analog input 4 (from terminal block, attenuated and protected.)
A5					Analog input 5 (from terminal block, attenuated and protected.)

AR2317 GPIO pin:	Function:
----------------	---------
GPIO0			Micro-SD SCK
GPIO1			Micro-SD MOSI
GPIO2			Not used.
GPIO3			Micro-SD MISO
GPIO4			Micro-SD CS
	
Information about packages/drivers for SD card use with OpenWRT: http://tinyhack.com/2010/04/04/d-link-dir-300-serial-port-and-sd-mod/





