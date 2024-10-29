Targeting System
Abstract:
 The purpose of this project is designing a targeting system by using BASYS 3 FPGA board
and Vivado VHDL.
Design Specification Plan:
Equipments:
1- BASYS 3
 It is the most important part of the project. It is an FPGA board that make user
able to design projects. It is coded by VHDL in this project and provide working with
servos and displaying image on monitor via VGA cable.
2- SG90 Servo Motor
 Servo motor works with 20 ms (50 Hz) signal and by generating 1-2 ms duty cycle it
can be rotated as it is desired. Also, it needs 4,8- 5V DC to work.
3- VGA Cable
 This provides connection between monitor and BASYS 3 to displaying desired image
(in this project word “FIRE”)
4- Monitor
Image is displayed on this device.
5- 3 piece of LDR sensors (Light sensors)
Light sensors gives input ‘1’ when the quantity of light is reduced. The sensitivity can
be adjusted via screwdriver. It need 3.3V to work.
6- Glove
Light sensors is attached to glove to control fire process better.
7- Jumper Cables
It provides connection between components.
8- Weapon model
It is attached to servo to construct more accurate and pleasant model.
9- Voltage Generator
It provides 5V DC to servo motor.
In this project, servo motor controlled via BASYS 3 and weapon model is attached to servo
motor. Subsequently, the direction of weapon is controlled by BASYS 3, which is coded by
VHDL. Seven switch of the BASYS 3 control the servo and when weapon’s aim is adjusted, it
is fired by three piece of LDR sensors, attached to the glove. When the luminous flux
(quantity of light) on all LDR sensors decrease, weapon open fire imaginatively. To show that
weapon open fire, when fire director is given by the light sensors, “FIRE” word appears on
monitor’s screen, which is connected to the BASYS 3 via VGA cable.
Project Design Methodology:
 Project consist of two phase. The first phase is displaying the “FIRE” word on the screen.
In order to perform this, 2 modules are created by VHDL in the name of “draw” and
“colourgenerator”. “colourgenerator” module is created due to scanning the monitor. It
scans the monitor from up to down and right to left by counters. Also, it restricts the limit of
the monitor so that we can give a color and shape appropriately. After giving monitor a solid
black screen, the shape and color have been given by “draw” module. “draw” module writes
the ”FIRE” word by using color (it has been chosen as red in this project). By coloring
between the bits using AND and OR gates, “FIRE” word is created on screen. Also, in “draw”
module it is coded that “when the all sensors on glove is closed, generates the word “FIRE””.
 The second phase is working with servo motor. To adjust the servo motor, three modules is
created. Servo motor requires 20 ms pulse signal with 1-2 ms duty cycle. In order to provide
that in first module “pulseconverter”, 50 MHz signal that BASYS 3 generates is converted to
64 kHz signal. This module is made for generating 1-2 ms duty cycle. After that, “servoo”
module is created and generating 20 ms signal with 1-2 ms cycle according to switches is
programmed. These two module is unified in module “servo_pwm_clk64kHz”. This module,
“draw” module, “colourgenerator” module is unified in “topmodule”.
As it can be seen, submodule 3 consist of two modules “pulseconverter” and “servoo” and
output of “pulseconverter” (64 kHz pulse signal) is used as an input by “servoo”. It is
demonstrated in figure 7 and figure 8, this submodule, generates the clock signal and duty
cycle by counters temporary registers. Also, it provides user to generate desired duty cycle
via switches on BASYS 3.
Results:
 After designing the coding part of the project, model is constructed. All components are
attached with jumpers and all of them is attached to BASYS 3 via PMODs. 
 All results are accurate and expected in design plan. Servo motor is rotated as the user
wants. 128 combination of rotation is tested by opening and closing switches on BASYS 3
and acquired accurate results. Dısplaying the “FIRE” word is accomplished as it can be seen
in figure 16.
Conclusion:
 The purpose of the project was designing a targeting system by using BASYS 3 and VHDL
language. Several and crucial circuit elements are researched and acquired. Working with
servo and controlling it by using BASYS3 and VHDL is accomplished. Displaying an image on
monitor by using VGA cable is accomplished and VGA output of BASYS3 is researched. VHDL
skills are improved and how to design counters, registers, multiplexers are learned.
Generating the desired clock signal by any FPGA board by using VHDL is learned.
