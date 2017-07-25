## Switching an LED on and off

GPIO Zero is a new Python library which provides a simple interface to everyday GPIO components.

- Open Python 3 from the main menu.

- You can switch an LED on and off by typing commands directly into the Python interpretor window (also known as the Python shell). Let's do this by first, importing the GPIO Zero library. You also need to tell the Pi which GPIO pin you are using - in this case pin 17. Next to the chevrons `>>>`, type:

	```python
	from gpiozero import LED
	led = LED(17)

	```
	Press **Enter** on the keyboard.

- To make the LED switch on, type the following and press enter:

	```python
	led.on()
	```

- To make it switch off you can type:

	```python
	led.off()
	```

