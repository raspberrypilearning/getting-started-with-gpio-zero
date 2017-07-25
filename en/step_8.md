## Usando los botones para tener una entrada
Ahora eres capaz de controlar un componente de salida, un LED. Vamos a conectar y controlar un componente de entrada: un botón.

- Conecta un botón a un pin GND y a al pin 2 GPIO, como se muestra en el diagrama:

    ![](images/button.png)
	
- Crea un nuevo archivo en **Archivo** > **Archivo nuevo**.
- Guarda el archivo en **Archivo** > **Guardar**.
- Guarda el archivo como `gpio_button.py`.

- Esta vez necesitarás la clase Button (botón en inglés), y declarar que el botón estará en el pin 2. Escribe el siguiente código en tu archivo: 

	``` python
	from gpiozero import Button
	button = Button(2)
	```

- Ahora puedes hacer que el programa haga algo cuando el botón esté pulsado. Prueba a añadir esta línea:

	``` python
	button.wait_for_press()
	print('Me has apretado')
	```

- Guarda con **Ctrl + S** y ejecuta el código con **F5**.
- Pulsa el botón y verás cómo tu texto aparece en pantalla.
 
