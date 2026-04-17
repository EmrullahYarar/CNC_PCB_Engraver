# CNC_PCB_Engraver
Simplest DIY CNC engraver for double sided PCBs. The base of project uses grblHAL and the system is built on ink printer case. The system works with master and slave stm32 controller for open and closed loop motor control mechaniscms.

Z_axis:
  Z axis is custom made 3d printed linear guide rail. Nema17 is used to control and A4988 step driver is used. The Z_Axis is controlled by master stm32.

X&Y_Axis:
  These two axis are the printers local axis. They converted to a close loop system. The system uses printers encoders sensors. The close loop is controlled by slave stm32. Slave taking the step, dir datas from master(grblHAL) then drives two DC(rs445) motor with two BTS7960 motor driver. It comapares the steps of master and encoder strips then drives motor. Also, if the steps missed it gives error.

Spindle:
  The spindle motor is 1/10 rc car 4 pole dc 3650mm 2300kv motor. It driven with a ESC by the master stm32. The arming is done from the gSender program. The speed can be adjusted. For engraving ER8 and V-bits are used.

Power Supply:  
  The power supply is a desktop computer PSU. For the logic level type-c connection is used. All stm32 and logic level works with 3.3 V. The 12V comes from the PSU and feeds the 3 axis motors. All ground points are connected. 

All the other features are supported from grblHAL, X,Y and Z calibration works. Z mapping works.

Only the axis are tested and calibrated. Project is ongoing.
