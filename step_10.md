## Haciendo un interruptor
Con un interruptor, pulsando el botón un avez deberá encender el LED, y con la siguiente pulsación el LED se volverá a apagar.

- Modifica tu código para que quede como este. Estamos usando un flag llamado active para almacenar el estado del LED. La línea `active = not active` conmutará el LED entre los estados `True` y `False`:

	``` python
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

Estaría genial si pudieramos hacer que el LED se encendiera sólo cuando el botón está pulsado. Con la librería GPIO Zero, es bien sencillo.

- Hay dos métodos de la clase Button llamados `when_pressed` y `when_released`. Estos métodos no bloquean el flujo del programa, así que si se colocan en un bucle, el programa se ejecutará indefinidamente. 

- Modifica tu código para que quede como este:

	``` python
	from gpiozero import LED, Button
	from signal import pause

	led = LED(17)
	button = Button(2)

	button.when_pressed = led.on
	button.when_released = led.off

	pause()

	```
- Guarda y ejecuta el programa. Ahora cuando el botón está pulsado, el LED se encenderá, y se volverá a apagar cuando el botón deje de estar pulsado. 

