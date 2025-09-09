# Distorion-pedal
This is a custom built distortion-pedal for my electric guitar that incorporates elements of prototyping, analog circuit design, and debugging. 


## Material List:
**Guitar input/output jacks:** (2)     
**Op-amp** TL072 (1)    
**Power Supply** 9v (1)    
**Diodes** BAT41 (2)    
**Potentiometer** 1MΩ (1), 100kΩ (1)   
**Capacitors:** 1uF (1), 47nF (2), 1nF (2)    
**Resistors:** 4.7kΩ (1), 20KΩ (4), 50kΩ (1), 100kΩ (2)    


##Circut design/Schmetic
The fundemntal idea of this circut is to amplify a AC signal, then to clip the signal to generate a distored tone. This is done in a few stages. 

##Stage 1: Input Band Pass Filter 
the AC input must first go through a band pass filter to block out both high and low frequncies. The frequnecy will "pass" (attenuate with less than -3dB) the signals that are between roughly 34hz to 8khz. This will allow for the normal gutair signal to pass through, while 
attenuating possible noise. 
[stage1_input](/images/stage1_input.png)

<br> <br> 

## Stage two, Biasing
After the signal passes through the band pass filter, the small ac signal (.1v-.5v typically) is then biased to 4.5 volts. This is done by creating a voltage divider with two equal resitors in series attached to a 9 volt battery, resulting in 4.5 volts between the two resistors. This is then attached via a resistor to the non inverting input of the op-amp. 
[stage2_bias](/images/stage2_bias.png).

 <br> <br> 
 
## Stage three, Op-Amp
The op-amp itself is configured in a inverting setup. This sets gain equal to (1+Rf/RI). RF has an adjustable potentometer, allowing for Rf to be adjusted from 4.7kΩ to 1,004.7kΩ. RI is set at 50kΩ, however the 47nF capacitor prevents the DC signal (4.5V bias) from
being amplifed with the AC signal by raising RI to infinity at f = 0hz (DC), making the gain unity. 

[stage3_opamp.png](/images/stage3_opamp.png)

## Stage four, Clipping stage
After amplifcation, the signal is first passed through a decoupling capacitor labled as "C4", this capacitor blocks DC signals and centeres the signal around 0 volts. After this, two diodes are connected to ground with opposite polaritys. This "clips" any signals that are above or below +/-.45 volts (this exact number depends on the diodes used). This clipping is what acutally creates the "distored" sound. 

[stage4_clipping](/images/stage4_clipping.png). 
<br>
<br>
<br>
Here is the full schmetaic of this pedal: 
<br> <br> 
![whole_schematic.png](/images/whole_schematic.png) 
<br> <br>


