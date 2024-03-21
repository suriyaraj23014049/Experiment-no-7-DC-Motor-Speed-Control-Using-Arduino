![image](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/36288975/739cc470-48c8-4873-a730-6319b4afc602)
###  DATE: 21-03-2024

###  NAME: SURIYA RAJ K
###  ROLL NO : 212223040216
###  DEPARTMENT: CSE
# Experiment-no-6-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

### PROGRAM 
```
int enable = 6;
int input1 = 3;
int input2 = 4;
void setup()
{
  pinMode(enable, OUTPUT);
  pinMode(input1, OUTPUT);
  pinMode(input2, OUTPUT);
}

void loop()
{
  analogWrite(enable, 80);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, LOW);
  digitalWrite(input2, HIGH);
  delay(5000); // Wait for 1000 millisecond(s)
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000);
}
```

### OUTPUT


![image](https://github.com/suriyaraj23014049/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151116233/4f739909-6c16-4e2a-a88c-c1a1f48f36ac)


### SCHEMATIC VIEW

![image](https://github.com/suriyaraj23014049/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151116233/d976eeb4-e57d-4488-af03-426ec23ef949)



### GRAPH AND TABULATION 

![WhatsApp Image 2024-03-21 at 11 46 40_266cee9e](https://github.com/suriyaraj23014049/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151116233/a93b5e83-2333-4247-8f37-31924f7f356d)


![WhatsApp Image 2024-03-21 at 11 46 40_43b0de96](https://github.com/suriyaraj23014049/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151116233/da10980f-47ae-4d06-8b18-9f53832d46d0)





### RESULTS AND DISCUSSION 

Thus the program to control the speed and the direction of a DC motor using L293D driver ic( H- bridge) is been implemented.

