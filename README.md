# Power-Supply

The objective of this project was to design and make a DC power supply that will convert AC supply of 220V, using a step-down transformer, into a variable DC output from 1V-30V. The low AC voltage is converted to pulsating DC voltage using bridge rectifier. The pulsating DC voltage thus obtained contains ripples in form of AC voltage. To remove these ripples a filter is needed which filters out the ripples from the DC voltage. A capacitor is placed in parallel to the output such that the capacitor (because of its impedance) allows high frequency AC signals to pass through get bypassed to ground and low frequency or DC signal is blocked. Thus the capacitor acts as a low pass filter. The output produced from a capacitor filter is the unregulated DC voltage. To produce a regulated DC voltage a regulator is used which develops a constant DC voltage, while the output voltage was to be varied using a variable resistor. A filter capacitor was also used so that the rectified pulsating DC output would attain a nearly constant voltage ¬¬before passing through the regulator, onto the load. 

## PROBLEM STATEMENT
 Design and implement an inverter circuit to meet the following load specifications. 
•	Current = 1 A 
•	Voltage= 220 V 
•	Sine wave having frequency = 50 Hz 
•	THD = 10% 
•	Overcharging protection of battery 
•	Design with minimal complexity is preferred 

## PROJECT OBJECTIVES
This project has 3 objectives which serve as a guideline to achieve the desired result. The objectives are:
1.	To design a regulated power supply that will give a variable output of 1V-30V.
2.	To design the power supply such that it will give 1A current at output
3.	To design a regulated power supply that will have a 10% ripple factor

## Block Diagram
![image](https://github.com/user-attachments/assets/04b7de0e-3c1a-4906-be57-f07cd5551288)

## EQUIPMENT USED:
•	LM317 Voltage Regulator
•	Full wave bridge rectifier
•	Filter Capacitor (4.7mF)
•	220-ohm resistor
•	5K variable resistor
•	12-0-12 transformer
•	AC source
•	Digital Voltmeter
•	Metal box
•	Knobs
•	Switch
•	Volume control

## Design Procedure
![image](https://github.com/user-attachments/assets/7a77cbf4-63d2-49bd-8201-f0f109086681)
### BLOCK 1: TRANSFORMER
230V AC is converted into 24V AC using a step-down transformer. 24V output of stepdown transformer is an RMS value and its peak value is given by the product of square root of two with RMS value, which is approximately 34V.

Calculations for primary and secondary coil for 12-0-12 transformer:
V(primary)= 230 V(rms)= 325.269V (pp)
V(secondary)= 24V (rms)= 33.94V (pp)
(Vpri^2)/(Vsec^2)= (Lpri)/ (Lsec)
100/1= Lpri/Lsec
i.e. primary inductance value= 100, secondary inductance value= 1

### BLOCK 2: FULL-WAVE RECTIFIER 
The output at the load with this bridge wave rectifier is pulsating in nature, i.e. it contains pulses, but for producing a pure DC requires additional filter like capacitor. voltage drop across the diodes is: (2*0.7V) = 1.4V;  therefore, the peak voltage at the output of this rectifier circuit is 32V (34-1.4) approx.

### BLOCK 3: FILTER CAPACITOR
The filtering stage of a power supply circuit smoothes out the ripples in the rectified DC to produce a smooth direct current that’s suitable for even the most sensitive of circuits.
Capacitor Calculations are as follows:
Vin= 33.94-1.4= 32.54V
r= Vr(pp)/Vdc --------- 1
Vdc= 0.63Vm
=0.63(32.54)
=20.5V
Using eq1
(r) x (Vdc)= Vr(pp)
20.5 x 0.1= 2.05= Vr(pp)
Now,
Vr(pp)= (1/fRlC) Vm
           = (32.54)/ (100 x 32.54 x 2.05)  
           =4.8mF 
Thus, a Polar capacitor of 4.8m or 4800uF has been used.

### BLOCK 4: VOLTAGE REGULATOR (LM317)
our requirement is to have a voltage of 1V-30V at 1A with positive polarity of the output voltage. For this reason, we need a regulator which can provide an output voltage up to 30V. An ideal and efficient choice would be the regulator IC LM317 that has minimum output voltage 1.2V and maximum output voltage up to 37V. Our next requirement is to calculate the input voltage requirement for the regulator. For a regulator, the minimum input voltage should be the output voltage added by a value of three. In that case, here to have a maximum voltage of 30V, we need a minimum input voltage of 33V. 
The 5K variable resistor is connected with the Adjust pin of the LM317. The resistor is used to vary the output voltage. 

Calculation for value of variable resistor are as follows:
Vdc= 1.25 x (1+ R1/R2)
Given that Vdc= 30V and R2= 220 ohm
30= 1.25 x (1+ R1/R2)
R1= 23 x 220= 5060 ohm (calculated)
R1= 5000 ohm (used)

## HARDWARE IMPLEMENTATION
![image](https://github.com/user-attachments/assets/9d4a3125-2080-43b7-b3ce-170baa4726aa)
![image](https://github.com/user-attachments/assets/f73c341f-985c-4544-af26-8d8b0a8a0176)
![image](https://github.com/user-attachments/assets/a39f62ff-4f9c-41c5-99b6-585a5a364fa3)

## CONCLUSION
We can conclude this project report with the observations that a minimum output voltage of 1.2V and a maximum output voltage of 30.9V. Ripple factor obtained was 8%. 
![image](https://github.com/user-attachments/assets/2e021b73-ac5f-458a-a313-f3de68b050b1)



