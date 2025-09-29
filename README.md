# JAM-pedal
Documentation for LUNA, an analog Tremolo Guitar effect pedal
![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/jam%20pedal.png "Image of end design functionality")

The tremolo features rate, depth and gain control. With most tremolo effects, overall volume loss is inevitable, so a gain knob is necessary to maintain consistency in your signal chain.

There are two selectable waveshapes that source the tremolo, namely Square and Triangular. The rate knob allows you to sweep frequency of the Low Frequency Oscillator (LFO) that drives the effect from ~0.5Hz to ~16Hz.

The depth control gives you flexibility with how intense the effect is. If you don't want full volume drop ~-3dB, you can reduce the effect all the way up to no volume drop, allowing you full control over how you would like your guitar to sound.

There will also be 2 digital circuits (an echo and a delay) that will be controlled by a raspberry pi zero
The footswitch on the right will swap between the two analog/digital architectures, and the hand switch underneath the control dials will swap between each of their two respective effects, with a three way switch capable of outputting both effects simultaneously. 

![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/LFO%20Design.png "LFO Implementation")

This LFO provides stable Square, Triangle and Sine wave outputs to allow the user to fine tune their tone to their needs and desires.
Vcc = 9V, Vref = 4.5V, GND = 0V, SinOffset = 4.75V
