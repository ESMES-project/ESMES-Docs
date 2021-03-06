# Abstract hardware & firmware requirements
* ESMES will consist of two modules: a capture module (CM) with an STM32 microcontroller, and an interface and communication module (ICM) with an ESP32 SoC.
  * The capture module (CM) will be responsible for recording the voltage and current signals. 
  * The interface and communication module (ICM) will be responsible for controlling the human-machine interface, communicating with a configuration device via bluetooth and hosting a web service through which external computers will be able to obtain the signals via the internet.
  * Modules must communicate over a serial communication protocol.

## Capture Module (CM)

* CM should record voltage and alternating current signals with as little noise as possible.
* CM should have at least 6 channels: one channel for each main's voltage, and 2 channels for each main's current (one for bigger and other for smaller power limits).
* CM channels should have software adjustable gain.
* CM should capture signals with 6kHz sampling frequency.
* CM should send a pack of samples 2 times per second for ICM via UART
* CM should use 3 GPIO outputs as a bus to log up to 8 error flags (0000=no error, 1000=error 1, 1001=error 2, 1010=error 3, 1011=error 4, 1100=error 5, 1101=error 6, 1110=error 7, 1111=error 8).
* CM should use 1 GPIO input with external interruption support to receive commands for start/stop recording (0->1=start, 1->0=stop).
* CM should use 1 GPIO input with external interruption support to receive reset commands (0->1=reset).
* CM should use 1 GPIO input with external interruption support to receive sleep/wakeup commands (0->1=wakeup, 1->0=sleep).

## Interface and Communication Module (ICM)

* ICM should store the recorded signals in case of connection drops.
* ICM should connect to the user's wifi and will host a web server.
* ICM should store wifi SSID and PASSWORD in the flash memory.
* ICM should store CM configurations in the flash memory to configure CM on reseting.

## Power Supply

* The embedded system will be powered by mains power, but will have a backup battery in case the power goes out.
