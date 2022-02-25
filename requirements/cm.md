# Capture Module (CM) Requirements

* CM should capture signals with 6kHz sampling frequency.
* CM should send a pack of samples 2 times per second for ICM via UART
* CM should use 3 GPIO outputs as a bus to log up to 8 error flags (0000=no error, 1000=error 1, 1001=error 2, 1010=error 3, 1011=error 4, 1100=error 5, 1101=error 6, 1110=error 7, 1111=error 8).
* CM should use 1 GPIO input with external interruption support to receive commands for start/stop recording (0->1=start, 1->0=stop).
* CM should use 1 GPIO input with external interruption support to receive reset commands (0->1=reset).
* CM should use 1 GPIO input with external interruption support to receive sleep/wakeup commands (0->1=wakeup, 1->0=sleep).
