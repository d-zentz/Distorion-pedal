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
low and high frequncys. The band pass filter passes frequncys between approximently 34hz to 8khz, allowing for normal gutair signals to pass though but attenuating possible noise. 
