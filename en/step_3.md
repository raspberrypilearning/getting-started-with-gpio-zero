## GPIO pins

The bank of pins along one side of the Raspberry Pi are called General-Purpose Input/Output.

These pins allow the Raspberry Pi to control things in the real world. You can connect components to these pins: output devices like LEDs (light emitting diodes) which can be turned on and off at will; or input devices like a button or sensor which can be used to trigger events, such as turning on an LED when a button is pressed.

There are 40 pins on the Raspberry Pi (26 pins on early models), and the pins provide various different functions.

If you have a RasPIO pin label, it can help to identify what each pin is used for. Make sure your pin label is placed with the keyring hole facing the USB ports, pointed outwards.

![](images/raspio-ports.jpg)

If you don't have a pin label then this guide can help you to identify the pin numbers:

![](images/pinout.png)

You'll see pins labelled as 3V3, 5V, GND and GP2, GP3, etc:

|     |     |     |
| --- | --- | --- |
| 3V3 | 3.3 volts | Anything connected to these pins will always get 3.3V of power |
| 5V | 5 volts | Anything connected to these pins will always get 5V of power |
| GND | ground | Zero volts, used to complete a circuit |
| GP2 | GPIO pin 2 | These pins are for general-purpose use and can be configured as input or output pins |
| ID_SC/ID_SD/DNC | Special purpose pins | | |

