# Abstract hardware requirements
## Modules
* ESMES will consist of two modules: a capture module (CM) with an STM32 microcontroller, and an interface and communication module (ICM) with an ESP32 SoC.
  * The capture module (CM) will be responsible for recording the voltage and current signals. 
  * The interface and communication module (ICM) will be responsible for controlling the human-machine interface, communicating with a configuration device via bluetooth and hosting a web service through which external computers will be able to obtain the signals via the internet.
  * Modules must communicate over a serial communication protocol.
* The embedded system will be powered by mains power, but will have a backup battery in case the power goes out.
* The interface and communication module must store the recorded signals in case of connection drops.
* The interface and communication module must connect to the user's wifi and will host a web server.
* The capture module must record voltage and alternating current signals with as little noise as possible.
* The capture module's sampling frequency must be sufficient to record 25 harmonics from the 60Hz grid.
