**# Break-Failure-Indicator-Circuit-by-using-555-Timer-IC**

![image](https://user-images.githubusercontent.com/71811374/174326440-147492e9-162c-4404-8968-9e5d607e7e17.png)


Automobiles have been the primary mode of transportation for most of us and we depend on them for our day to day commute. Unfortunately there are lots of mishaps that could occur while driving an automobile and Brake Failures are one such case. Of course accidents cannot be avoided sometimes but they can sure be prevented by taking some preventive measures. In this project we will build a Circuit that can be attached to our Vehicles which will monitor the brake of our vehicle and provide us an audio-visual feedback if the brake fails.

Automobiles have been the primary mode of transportation for most of us and we depend on them for our day to day commute. Unfortunately there are lots of mishaps that could occur while driving an automobile and Brake Failures are one such case. Of course accidents cannot be avoided sometimes but they can sure be prevented by taking some preventive measures. In this project we will build a Circuit that can be attached to our Vehicles which will monitor the brake of our vehicle and provide us an audio-visual feedback if the brake fails.

Most economical vehicles depend on wire braking mechanism to apply brakes on the vehicle. This mechanism involves a Brake wire which runs from the brake lever to the braking mechanism set-up of the vehicle. It is this wire that gets pulled when we apply brakes to stop our vehicle. After a long use and tear these wires might get worn out and get cut at one point of time which eventually will cause a brake failure. So we will build a circuit that will monitor the continuity of this wire, the circuit will glow a green colour LED if everything is fine, but is the wire fails the circuit will blink a red colour LED also will beep a buzzer to alert the rider. Let us see how we can build this project...

**Materials Required:**
Breadboard
555 Timer IC
BC557 PNP Transistor
Red and Green Colour LED
1uf and 0.1uf Capacitor
1K and 440K resistors
Connecting wires
Buzzer

**Circuit Diagram and Explanation:**
The circuit diagram for this brake failure indicator project is shown below
![image](https://user-images.githubusercontent.com/71811374/174325647-48d519d1-52de-4e2d-b9a4-2e08f83cd784.png)

As you can see this brake failure indicator circuit is very simple and can be easily built on a breadboard. The main components in this project are the 555 Timer and the BC557 PNP transistor. The 555 Timer operates in Astable mode to produce clock pulse and the BC557 PNP Transistor monitors the Brake wire and decides which led should glow.

**555 Timers in Astable Mode:**
The Astable mode in a 555 timer is mainly used for Blinking LEDs or to do some periodic Turn On and Turn off actions. In this project we have configures the Timer to work with 0.3Sec on time and 0.3sec Off time. The value of the resistors R1, R2 and capacitor C1 decides the on and off time of the Pulse produced. The formulas for calculating the same is given below.

T1 = 0.693(R1+R2).C1

T2 = 0.693*R2*C1

T = T1+T2

F = 1/T

Duty Cycle = T1/(T1+T2)

In our case the value for R1 = 1000ohm and R2=440000ohm and C1=0.000001F. So using these formulae we can calculate our values to be

![image](https://user-images.githubusercontent.com/71811374/174325901-bb1d1de7-889d-4daf-b995-712297ca2d56.png)

So the output of the pulse should remain turned on for 0.305Sec and turned off for 0.304 seconds which is almost the same when analyzed on the graph below which was obtained with help of a Digital Storage oscilloscope.

![image](https://user-images.githubusercontent.com/71811374/174326024-31bcb135-abad-4fe0-a935-276c4ac33402.png)

The BS557 PNP transistor controls the LEDs and buzzer. When the Brake wire is in proper condition the base of this transistor is provided with 5V through a current limiting (R4) Resistor. This also drives the Green LED light and disconnects the Buzzer and Red LED from ground thus keeping it turned off. 

When the break wire is cut the base of the BC557 is also cut and thus the Green LED is turned off and the Buzzer and Red LED are connected to ground. Since the positive end of Buzzer and LED is connected to the 3rd pin of 555 timers which is wired in Astable mode operation, they blink/beep based on the duration set by the above calculation.

**Working of This Brake Failure Circuit:**
Once the connection is made power the circuit, make sure the Brake cable (here I have used a normal green wire to represent the brake cable) is connected across the +5V and base of BC557 through a resistor as shown in the circuit.

If everything works as expected you should see the Green LED turned on and the Buzzer and Red Light Turned Off. Now, cut/remove the brake cable the Red LED and the Buzzer should start flashing as shown in the video below.
