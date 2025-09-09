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
The op-amp itself is configured in a inverting setup. This sets gain equal to (1+Rf/RI). RF has an adjustable potentometer, allowing for Rf to be adjusted from 4.7kΩ to


The op-amp itself is in a non inverting configuration. An entire picture of the input stages plus the op amp is shown here 



The last phase of the circut is called the clipping stage as shown here [stage4_clipping](/images/stage4_clipping.png). The first part of this is the decoupling capacitor marked as "C4". This capacitor blocks DC signals and centers the signal around 0 volts.


Next the signal is connected to ground via two diodes. These diodes "cut" off voltages above .45 volts and below -.45 volts (the exact cut off voltage varys depending on the exact diode used, as well as other factors). This clipping stage is what actually gives the output the disticn't "distrion" sound.  

[stage3_opamp.png](/images/stage3_opamp.png)

<br> <br> 
![whole_schematic.png](/images/whole_schematic.png) 
<br> <br>


