# Software installation

You'll need to make sure you have the following packages installed to proceed with the worksheet:

- GPIO Zero

You'll need to be online to install software.

First, update and upgrade your system. Enter the following commands into the terminal:

```bash
sudo apt-get update
sudo apt-get upgrade
```

Now install the software you'll need:

```bash
sudo apt-get install python3-gpiozero
```

Check that you have everything you need by entering the following commands:

```bash
python3 -c "import gpiozero"
```

This should bring you back to the command prompt with no errors. If you get an error saying `No module named gpiozero`, then check you entered the commands above correctly.
