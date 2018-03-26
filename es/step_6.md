## Encendiendo y apagando un LED

GPIO Zero es una nueva librería de Python que proporciona una interfaz sencilla para interactuar con componentes a través de los pines GPIO
- Abre Python 3 desde el menú principal

- Puedes encender y apagar un LED tecleando comandos directamente en la ventana del intérprete de Python (también llamada Python shell). Vamos a hacerlo así primero, importando la librería GPIO Zero. También es necesario establecer qué pin GPIO es el que vamos a usar; en este caso será el 17.  Junto a los símbolos `>>>`, teclea:

	``` python
	from gpiozero import LED
	
	led = LED(17)
	```
Pulsa **Enter** en el teclado.

- Para que hacer que el LED se encienda, escribe la siguiente línea y pulsa Enter:

	``` python
	led.on()
	```

- Para apagar el LED puedes teclear:

	``` python
	led.off()
	```
	
