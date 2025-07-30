# JAM-pedal
Documentation for analog/digital JAM guitar pedal design process
![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/jam%20pedal.png "Image of end design functionality")

The goal is to have 1 analog circuit, namely a tremolo, powered by a simple LFO

There will also be 2 digital circuits (an echo and a delay) that will be controlled by a raspberry pi zero
The footswitch on the right will swap between the two analog/digital architectures, and the hand switch underneath the control dials will swap between each of their two respective effects, with a three way switch capable of outputting both effects simultaneously. 

![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/LFO%20Design.png "LFO Implementation")

This LFO provides stable Square, Triangle and Sine wave outputs to allow the user to fine tune their tone to their needs and desires.
Vcc = 9V, Vref = 4.5V, GND = 0V, SinOffset = 4.75V
