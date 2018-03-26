## Haciendo parpadear el LED

Con la ayuda de la librería time y un pequeño bucle, podemos hacer que el LED parpadee.

- Crea un nuevo archivo en **Archivo** > **Archivo nuevo**.
- Guarda el archivo en **Archivo** > **Guardar**.
- Guarda el archivo como `gpio_led.py`
- Escribe el siguiente código para empezar:

	``` python
	from gpiozero import LED
	from time import sleep

	led = LED(17)

	while True:
		led.on()
		sleep(1)
		led.off()
		sleep(1)

	```
14. Guarda con **Ctrl + s** y ejecuta el código con **F5**.
15. El LED debería estar encendiéndose y apagándose continuamente. Para salir del programa pulsa **Ctrl + c** en el teclado.

