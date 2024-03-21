![image](https://github.com/vasanthkumarch/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/36288975/739cc470-48c8-4873-a730-6319b4afc602)
###  DATE: 21.03.24

###  NAME: B.SANDHIYA SREE
###  ROLL NO :212223220093
###  DEPARTMENT:INFORMATION TECHNOLOGY
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
int enable=2;
int input1=3;
int input2=4;
void setup()
{
  pinMode(enable, OUTPUT);
    pinMode(input1, OUTPUT);
    pinMode(input2, OUTPUT);
  
}

void loop()
{
  analogWrite(enable, 50);
   delay(1000);
  digitalWrite(input1, HIGH);
  digitalWrite(input2, LOW);
  delay(5000); 
   digitalWrite(input1, LOW);
   digitalWrite(input2, HIGH);
  delay(7000);
}

### OUTPUT
![Screenshot 2024-03-21 113630](https://github.com/Sandhniya/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151395890/96398363-a987-4cd8-82cb-c230b6986a48)

![Screenshot 2024-03-21 113646](https://github.com/Sandhniya/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151395890/652b60d6-ba11-4001-a57f-e2d87c622aba)



### GRAPH AND TABULATION 
![Screenshot 2024-03-21 113542](https://github.com/Sandhniya/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151395890/eec093f8-c908-4615-90a2-713db6040504)
![Screenshot 2024-03-21 113550](https://github.com/Sandhniya/Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino/assets/151395890/644f3b49-50b4-482e-9aa9-abad9d2c09c0)



### RESULTS AND DISCUSSION
Hence DC motor speed control using aurdino is worked sucessfully.

