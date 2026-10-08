# Fan_Controller
## About The Project
This is a custom PCB fabricated in KiCad for a custom 3 Hole Fan Powered by USB-C. It serves as a step into custom non-guided PCB's.

<img width="758" height="757" alt="image" src="https://github.com/user-attachments/assets/7c65bea1-d150-4715-ab4d-59da49c89de8" />
This is the PCB containing 2 layers. The top left is the USB-C, and the Top right is the output pins.
<img width="968" height="614" alt="image" src="https://github.com/user-attachments/assets/18b4eebb-8218-4aa4-9560-75c692df8707" />
This is the schematic. The top left is the USB-C Receptacle, Top right is ch224k, or voltage negotiator. The bottom left is the main component that is in control of PWM, which routes through the LM7085-TO220 5v Regulator, and the bottom right is circuit wide filtering and bulk capacitors.

### Built With
Kicad

## Framework
### Input
- USB-C receptacle
The board uses a ch224k connected to the CC lines of a USB-C to negotiate 12V for the board. The two pieces are next to each other in order to minimize heat loss. There is also a polyfuse connected to the usb-C which all of the board connects to in order to prevent short circuits.
<img width="825" height="437" alt="image" src="https://github.com/user-attachments/assets/0d155388-7467-4185-9d7e-702f4859f529" />

### Body
- PWM Control
This uses a NE555 timer, and a potentiometer to control the PWM pin. Testing of the fan determined that after 80% pwm, the blower shut off, therefore a resistor was added into the pwm circuit to prevent this. The potentiometer was added with the resistor to change resistance, hence the pwm. PWM values are adjustable by changing the 3.3 KOHM resistor to increasing or decreasing amounts.
<img width="682" height="731" alt="image" src="https://github.com/user-attachments/assets/02fe5fb1-9eda-45be-9c34-004d9350f45e" />

### Output
- 3 Pin Connector
Pin 1 - Power
  This contained the 12v Power line after the fuse. It contained the power for all, and had traces as short as possible to minimize heat loss. It is the highest pin on the board
Pin 2 - Control/PWM
  This was the main controller of the board. This fan only turned on when this pin was set to high, and hance had a standard voltage below that of the power, ranging somewhere near ~2 Volts at 50% PWM. This is directly linked to the OUT pin of the NE555P with a 1k Resistor to prevent greater current flow. 
Pin 3 - GND
  This was a common ground shared by all.
<img width="612" height="432" alt="image" src="https://github.com/user-attachments/assets/db164ba0-a856-4f79-9f23-93addf0c08b0" />

## Usage
This is a prototype based on previous documentation of NE555 PWM circuits. This has several different applications, primarily in PC fan usages, and standard electric components. These use no specialty components, using basic components in order to minimize cost for greater production.
<img width="681" height="691" alt="image" src="https://github.com/user-attachments/assets/6c37a0df-1192-4e52-976f-a61bb2dbca29" />
3d View of PCB.
