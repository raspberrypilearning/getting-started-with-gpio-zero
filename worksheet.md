# Getting started with GPIO Zero

## GPIO pins

The bank of pins along one side of the Raspberry Pi are called GPIO pins - General Purpose Input Output.

These pins allow the Raspberry Pi to control things in the real world. You can connect components to these pins: output devices like LEDs (light emitting diodes) which can be turned on and off at will; or input devices like a button or sensor which can be used to trigger events (e.g. when a button is pressed, turn on the LED).

There are 40 pins on the Raspberry Pi (26 pins on early models) - and some pins provide different functions to others.

If you have a RasPIO pin label it can help to identify what each pin is used for. Make sure your pin label is placed with the key-ring hole facing the USB ports, pointed outwards.

![](images/raspio-ports.jpg)

If you don't have a pin label then this guide can help you to identify the pin numbers.

![](images/pinout.png)

You'll see pins labelled as 3V3, 5V, GND and GP2, GP3, etc.

|     |     |     |
| --- | --- | --- |
| 3V3 | 3.3 volts | anything connected to these pins will always get 3.3V of power |
| 5V | 5 volts | anything connected to these pins will always get 5V of power |
| GND | ground | zero volts, used to complete a circuit |
| GP2 | GPIO pin 2 | these pins are for general purpose use and can be configured as input or output pins |
| ID_SC/ID_SD/DNC | special purpose pins | | |

## Lighting an LED

Try connecting an LED to the Pi (to 3V3 and GND) with a resistor:

![](images/led-3v3.png)

The LED should light up. It was always be on, because it's connected to a 3V3 pin.

Now try moving it from 3V3 to GPIO pin 17:

![](images/led-gpio17.png)

The LED should now turn off. But now it's on a GPIO pin, it can be controlled by code.

## Switching an LED on and off

GPIO Zero is a new Python library which provides a simple interface to everyday GPIO components.

1. Open Python 3 from the main menu

1. You can switch an LED on and off straight from the Python shell. Firstly you'll need to import the gpiozero library. You also need to tell the Pi which GPIO pin you are using - in this case pin 17.

	```python
	from gpiozero import LED
	led = LED(17)

	```

1. To make the LED switch on, type the following:

	```python
	led.on()
	```

1. To make it switch off you can type:

	```python
	led.off()
	```

## Flashing an LED

1. With the help of the `time` library and a little loop, you can make the LED flash	

1. Create a new file by clicking **File > New file**

1. Save the new file by clicking **File > Save**

1. Save the file as `gpio_led.py`

1. Enter the follow code to get started:

    ```python
    from gpiozero import LED
    from time import sleep

    led = LED(17)

    while True:
        led.on()
        sleep(1)
        led.off()
        sleep(1)
    ```

1. Save with **Ctrl + S** and run with **F5**

1. The LED should be flashing. Press **Ctrl + C** to exit the program

## Using buttons to get input.

1. Now connect a button to another GND pin and GPIO pin 2:

    ![](images/button.png)

1. You can test that your button is working to start off with.

1. Create a new file by clicking **File > New file**

1. Save the new file by clicking **File > Save**

1. Save the file as `gpio_button.py`

1. This time you'll need the Button class, and to tell it that the button is on pin 2. Write the following code in your new file:

	```python
	from gpiozero import Button
	button = Button(2)
	```

1. Now you can get your program to do something when the button is pushed. Add these lines:

	```python
	button.wait_for_press()
	print('You pushed me')
	```

## Manually controlling the LED

1. You can now combine your two programs to control the LED using the button.

1. Create a new file by clicking **File > New file**

1. Save the new file by clicking **File > Save**

1. Save the file as `gpio_control.py`

1. Now write the following code.

	```python
	from gpiozero import LED, Button
	from time import sleep
	
	led = LED(17)
	button = Button(2)

    button.wait_for_press()
    led.on()
	sleep(3)
	led.off()
	```
1. Save and run your program. When you push the button the LED should come on for three seconds.

## Making a switch

1. With a switch, a single press and release on the button would turn the LED on, and another press and release would turn it off again.

1. Modify your code so that it looks like this. You're using a `flag` called active to record the state of the LED. the line `active = not active` will switch the flag between `True` and `False`.

	```python
	from gpiozero import LED, Button
	from time import sleep

	led = LED(17)
	button = Button(2)
	active = False

	while True:
		if active == False:
			led.off()
		else:
			led.on()
		button.wait_for_press()
		button.wait_for_release()
		active = not active

	```

1. It would be great if you could make the led switch on, only when the button is being held down. With gpiozero, that's easy.

1. There are two methods of the Button class called `when_pressed` and `when_released`. These don't block the flow of the program, so if they are placed in a loop, the program will continue to cycle indefinitely.

1. Modify your code to look like this:

    ```python
    from gpiozero import LED, Button
    from time import sleep

    led = LED(17)
    button = Button(2)

    while True:
		button.when_pressed = led.on
		button.when_released = led.off

    ```

1. Save and run the program. Now when the button is pressed, the LED will light up and will turn off again when the button is release.

## What next

There are lots of other things to try with GPIO Zero. You can have a look at the [documentation here](http://pythonhosted.org/gpiozero/).

Have a go at controlling other components, such as a:
- Buzzer
- RGB LED
- Motor
- Robot.