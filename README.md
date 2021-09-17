# arduino_pro_micro_macro_keyboard

A macro keyboard using Arduino (pro) micro with selectable macro profiles
and an OLED screen to indicate the profile selected. It uses a PISO shift
register 

The PCB gerber files, 3D CAD files for the housing and parts list are 
included as well. Do note that the Arduino (pro) micro that is compatible 
with the current PCB and 3D CAD is 17.9mm in width and it has either 
USB type C or micro-usb connector, the mini-USB version will not fit!

# Features:
1. Rotary encoder knob
2. Profile selector button
3. Reset button
4. OLED screen
5. Default 18 possible macro combinations per profile
   but it can go up to 24 for normal humans and 254 for
   geniuses who can remember that many combinations but 
   do mind the amount of available memory

# PCB:
The current PCB uses cherry MX or similar key switches as buttons,
feel free to use any switch you like! The 10K resistors on the side 
can either be in the SMD 2010 from factor or THT. If you're using the
SMD 2010 form factor, you have the option of soldering them either on
the top or bottom of the PCB depending on which version of the housing
you want to print.

# Special thanks to:
NicoHood for developing the HID library and
Henning Karlsen of Rinky-Dink Electronics for developing a 
lightweight OLED library. DroneBot workshop for providing the 
basic code to run the 74HC165 PISO shift register.



