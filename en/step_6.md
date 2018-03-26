## Flashing an LED

With the help of the `time` library and a little loop, you can make the LED flash.	

- Create a new file by clicking **File > New file**.

- Save the new file by clicking **File > Save**.

- Save the file as `gpio_led.py`.

- Enter the following code to get started:

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

- Save with **Ctrl + S** and run the code with **F5**.

- The LED should be flashing on and off. To exit the program press **Ctrl + C** on your keyboard.

