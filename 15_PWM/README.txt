HOW TO RUN LOGIC ANALYSER
Tutorial from: https://learn.sparkfun.com/tutorials/using-the-usb-logic-analyzer-with-sigrok-pulseview
1) download pulse-NIGHTLY-64bit static release (https://sigrok.org/wiki/Windows#Windows_installers)
2) connect analyzer
3) In zadig install driver for unknown device #1 WinUSB
4) add analyzer to pulse width by clicking on the list from the left of the setting icon
5) click usb -> fx2lafw driver and search -> 8-channel analyzer
4) Look for the pins in CubeMX, connect them, run it

OPTIONS HOW TO ACHIEVE 50% duty cycle
APB2 clock: 80Mhz
Prescaler 1600
Counter period 1000
Pulse 500

OPTION2 (from the book):
*used in 15_PWM
APB2 clock: 84Mhz
Prescaler 655
Counter period 1960
Pulse 980

result measuer using pulse view and logical analyser
-calculations slide 13 Week 8 (NOT EXACTLY PRECISE ON DECIMAL POINTS)
-7.95ms on
-15.9ms total time