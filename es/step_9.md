## Controlando un LED manualmente

Ahora podemos combinar los dos programas que has escrito hasta ahora para controlar el LED usando el botón

- Crea un nuevo archivo en **Archivo** > **Archivo nuevo**.
2. Guarda el archivo en **Archivo** > **Guardar**.
3. Guarda el archivo como `gpio_control.py`.
4. Ahora escribe el siguiente código:

	``` python
	from gpiozero import LED, Button
	from time import sleep

	led = LED(17)
	button = Button(2)

	button.wait_for_press()
	led.on()
	sleep(3)
	led.off()
	```

- Guarda y ejecuta el programa. Cuando pulses el botón, el LED deberé encenderse durante 3 segundos.

