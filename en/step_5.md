## Encender un LED
Prueba a conectar un LED a los pins de 3.3V y GND con una resistencia.

![](images/led-3v3.png)

El LED se debería encender. Siempre estará encendido, porque está conectado a un pin de 3.3 voltios.

Ahora prueba a moverlo del pin 3.3V al pin GPIO 17:

![](images/led-gpio17.png)

El LED ahora se debería apagar, pero como está conectado a un pin GPIO podemos controlarlo con código.

