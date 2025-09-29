# JAM-pedal
Documentation for LUNA, an analog Tremolo Guitar effect pedal


![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/portrait.JPG "LUNA Tremolo Pedal")

The tremolo features rate, depth and gain control. With most tremolo effects, overall volume loss is inevitable, so a gain knob is necessary to maintain consistency in your signal chain.

There are two selectable waveshapes that source the tremolo, namely Square and Triangular. The rate knob allows you to sweep frequency of the Low Frequency Oscillator (LFO) that drives the effect from ~0.5Hz to ~16Hz.

The depth control gives you flexibility with how intense the effect is. If you don't want full volume drop ~-3dB, you can reduce the effect all the way up to no volume drop, allowing you full control over how you would like your guitar to sound.

![alt text](https://github.com/aryeh-bloom/JAM-pedal/blob/main/spice_schematic.png "LTSpice Circuit")

Above is the LTSpice diagram of the circuit. The pedal is designed to run on a single-rail 9V supply. Vref is ~-4.5V.
Due to the limited parts available in LTSpice, I had to get creative with how to model some of the components that my design uses. The basis of the effect is a [homemade optocoupler] (https://sound-au.com/project200.htm) built from an LED, a photoresistor (or LDR), and some heat shrink tubing. Using an optocoupler allowed me to completely isolate the LFO design from the guitar signal processing stage. I achieved similar behavior in LTSpice by modeling a shunt resistor (named LDR) to change resistivity according to the LED (named LDRa) output current.

It is also important to note that the potentiometers are implemented in LTSpice as resistors, as there is no native potentiometer component. 

Lastly, the two nodes, named "Triangle Out" and "Square Out" respectively, are (as you may have guessed) the waveshape outputs of the oscillator. The C2 capacitor charges up linearly until it reaches the opamp comparator trigger threshold, sending the opamp to rail, which then causes the capacitor to discharge linearly, sending it to the other rail. The 'rail-to-rail' signal (found in the noninverting terminal of the opamp) produces the square shape, while the 'capacitor charging' signal (found in the inverting terminal) produces the triangle shape. 
In LTSpice, these outputs have been modeled as floating wires into the depth control potentiometer, due to the fact that LTSpice does not natively have a SPDT switch to select between the two waveshapes. 
