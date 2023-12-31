

# Hat 
Hat is a repository for a LED strip controller with custom software and hardware

## Acknowledgements

I would like to express my gratitude to the developers of the `RPI.GPIO` library, which played a crucial role in the development of this project. `RPI.GPIO` is a Python library that enables easy access to the GPIO pins on a Raspberry Pi. Its intuitive interface and extensive documentation significantly contributed to the success of this project.

- Project: [RPI.GPIO](https://pypi.org/project/RPi.GPIO/)
- Repository: [GitHub Repository](https://github.com/Tieske/rpi-gpio)
- Documentation: [RPI.GPIO Documentation](https://sourceforge.net/p/raspberry-gpio-python/wiki/Home/)

Thank you to the `RPI.GPIO` team for their dedication to creating a robust and reliable library that empowers developers to interact with the GPIO pins on the Raspberry Pi effectively.

## Note

It's important to note that the Py thon Package Index states the following:

```
Note that this module is unsuitable for real-time or timing critical applications. 
This is because you can not predict when Python will be busy garbage collecting. 
It also runs under the Linux kernel which is not suitable for real time applications - 
it is multitasking O/S and another process may be given priority over the CPU, causing jitter in your program. 
If you are after true real-time performance and predictability, buy yourself an Arduino http://www.arduino.cc !

Note that the current release does not support SPI, I2C, hardware PWM or serial functionality on the RPi yet. 
This is planned for the near future - watch this space! One-wire functionality is also planned.

Although hardware PWM is not available yet, software PWM is available to use on all channels.
```

Software PWM:
- Pros:
    - Flexibility: You can use any available GPIO pin for software PWM, making it suitable for cases where specific hardware PWM channels are not available.
    - No Hardware Dependencies: Software PWM doesn't rely on specific hardware capabilities, so it can be used on a wider range of platforms.
- Cons:
    - Timing Variability: As mentioned in the documentation, software PWM may not be suitable for timing-critical applications due to the unpredictability of when Python's garbage collection and other processes might impact timing accuracy.
    - Potential Jitter: The Linux operating system's multitasking nature can lead to jitter in the timing of software PWM, causing variations in PWM signal accuracy.

Hardware PWM:
- Pros:
    - Precision: Hardware PWM is generally more accurate and consistent than software PWM because it's generated by dedicated hardware components.
    - Reliability: Hardware PWM is not affected by Python's garbage collection or other processes, providing more predictable timing.
    - Higher Frequencies: Hardware PWM can often generate higher-frequency signals than software PWM.
- Cons:
    - Limited Channels: Hardware PWM is limited by the number of available hardware PWM channels. If you need to control multiple devices using PWM, you may run out of available channels.
    - Hardware Dependencies: Hardware PWM requires specific hardware capabilities, and if those capabilities are not available or not fully supported (as indicated in the documentation), you won't be able to use hardware PWM.

Currently, the Raspberry Pi(3B+) has two dedicated hardware PWM channels: PWM0 and PWM1
- GPIO12:	PWM0
- GPIO18:	PWM0
- GPIO13:	PWM1
- GPIO19:	PWM1

There are major differences between hardware and software PWM which inhibit this project's ability to implement a hardware PWM approach. Since there are only two channels available for PWM and the RGB strip used has three PWM channels (R,G,B), we are forced to use software PWM. 
