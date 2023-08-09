# hat
## Acknowledgements

I would like to express my gratitude to the developers of the `RPI.GPIO` library, which played a crucial role in the development of this project. `RPI.GPIO` is a Python library that enables easy access to the GPIO pins on a Raspberry Pi. Its intuitive interface and extensive documentation significantly contributed to the success of this project.

- Project: [RPI.GPIO](https://pypi.org/project/RPi.GPIO/)
- Repository: [GitHub Repository](https://github.com/Tieske/rpi-gpio)
- Documentation: [RPI.GPIO Documentation](https://sourceforge.net/p/raspberry-gpio-python/wiki/Home/)

Thank you to the `RPI.GPIO` team for their dedication to creating a robust and reliable library that empowers developers to interact with the GPIO pins on the Raspberry Pi effectively.

## Note

It's important to note that the Py thon Package Index states the following:

```
Note that this module is unsuitable for real-time or timing critical applications. This is because you can not predict when Python will be busy garbage collecting. It also runs under the Linux kernel which is not suitable for real time applications - it is multitasking O/S and another process may be given priority over the CPU, causing jitter in your program. If you are after true real-time performance and predictability, buy yourself an Arduino http://www.arduino.cc !

Note that the current release does not support SPI, I2C, hardware PWM or serial functionality on the RPi yet. This is planned for the near future - watch this space! One-wire functionality is also planned.

Although hardware PWM is not available yet, software PWM is available to use on all channels.
```


