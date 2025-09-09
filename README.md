# Distorion-pedal
This is a custom built distortion-pedal for my electric guitar that incorporates elements of prototyping, analog circuit design, and debugging. 


Material List:
-Guitar input/output jacks (2)     
-TL072 Op-amp (1)    
-9 volt power supply (1)    
-BAT41 Diodes (2)    
-1MΩ Potentiometer (1)    
-100kΩ Potentiometer (1)   
-Capacitors: 1uF (1), 47nF (2), 1nF (2)    
-Resistors: 4.7kΩ, 20KΩ (4), 50kΩ (1), 100kΩ (2)    


Circut design/Schmetic
The fundemntal idea of this circut is to amplify a AC signal, then to clip the signal to generate the distrioned tone. This is done in a few stages. Firstly, the signal must go into a band pass filter to filter out 
low and high frequncys as shown here:  [stage1_input](/images/stage1_input.png).  <br>   The band pass filter passes frequncys between approximently 34hz to 8khz, allowing for normal gutair signals to pass though but attenuating possible noise.  <br> <br> After the signal passes through the band pass filter, the small ac signal (.1v-.5v typically) is then biased to 4.5 volts. This is done by creating a voltage divider that results in a voltage drop of 4.5 volts between two resistors as shown here [stage2_bias](/images/stage2_bias.png). This voltage is then used to bias the non inverting input. <br> <br> The op-amp itself is in a non inverting configuration. An entire picture of the input stages plus the op amp is shown here [stage3_opamp.png](/images/stage3_opamp.png)
The last phase of the circut is called the clipping stage as shown here [stage 4](/images/stage4_clipping.png). The first part of this is the decoupling capacitor marked as "C4". This capacitor blocks DC signals and centers the signal around 0 volts. Next the signal is connected to ground via two diodes. These diodes "cut" off voltages above .45 volts and below -.45 volts (the exact cut off voltage varys depending on the exact diode used, as well as other factors). This clipping stage is what actually gives the output the disticn't "distrion" sound.  
<br> <br> 
![whole_schematic.png](whole_schematic.png) 
<br> <br>


