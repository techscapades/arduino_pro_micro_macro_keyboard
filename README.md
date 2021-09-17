# arduino (pro) micro macro keyboard

//insert irl assembly here

A macro keyboard using Arduino (pro) micro with selectable macro profiles
and an OLED screen to indicate the profile selected. It uses a PISO shift
register 

The PCB gerber files, 3D CAD files for the housing and parts list are 
included as well. Do note that the Arduino (pro) micro that is compatible 
with the current PCB and 3D CAD is 17.9mm in width and it has either 
USB type C or micro-usb connector, the mini-USB version will not fit!

# Features:
1. Rotary encoder
2. Profile selector button
3. Reset button
4. OLED screen
5. Default 18 possible macro combinations per profile
   but it can go up to 24 for normal humans and 254 for
   geniuses who can remember that many combinations but 
   do mind the amount of available memory

# Usage:
Explained in this youtube video:


# PCB:

//insert PCB images here

The current PCB uses cherry MX or similar key switches as buttons,
feel free to use any switch you like! The 10K resistors on the side 
can either be in the SMD 2010 from factor or THT. If you're using the
SMD 2010 form factor, you have the option of soldering them either on
the top or bottom of the PCB depending on which version of the CAD 
housing you want to print.

PCB components: (all links and images attached in PDF)
1. 1x Arduino (pro) Micro
2. 1x Rotary encoder with round PCB
4. 9x Cherry MX clone keyboard switches
5. 9x Cherry MX compatible keycaps
6. 1x 128x32 OLED 
7. 1x 12mm tactile push button switch with switch cap
8. 1x DIP-16 74HC165 PISO shift register
9. 8x SMD-2010 or THT 10K resistors
10. 2x 4 pin female PCB header pins
12. *Optional but highly recommended* 1x Rotary encoder knob
13. *Optional* 1x DIP-16 socket or 2x DIP-8 sockets

# 3D Printable CAD housing

//insert CAD housing picture here

The main components of the housing are the PCB cover and the housing base.
//insert images of both here

There are 2 versions of the PCB cover, one version is when the SMD or THT
resistors are soldered to the top of the PCB, the other is when the
SMD (only) resistors are soldered to the bottom of the PCB, snapshots of
what both versions will look like are in the 'snapshots' folder. 

You have plenty of options for mounting the PCB to the housing base since I've 
made the holes slightly smaller which gives you the option to use self-tap screws 
or machine screws with nuts or machine screws with tapped holes; you can literally use 
whatever you have at hand but keep in mind that the screws I intended to use are M3 
so make sure you have the correct size.

I've opted to drill 3mm holes in the housing base and PCB cover, then use M3x20mm 
screws with plastic M3 spacers to fasten the screw from the bottom of the base
to the top of the PCB cover. Finally, I've added anti-slip pads to the bottom of
the housing base to prevent it from slipping.

//insert images here

*Optional Housing 3D printing files for extra style points*
//insert cover piece photo

The additional rotary encoder/reset button/OLED cover piece is nice but not necessary.
If you do decide to print it, you will need to:
1. Ideally tap M3 threads into the 3 holes in the PCB cover or less ideally
   heat up an M3 screw and screw into the cover piece to create the thread
2. Screw 3x M3x6mm brass spacers into the holes
3. *optional* drill 4mm holes into the cover piece if the screws dont go in right

*Optional Optional transparent acrylic cover for style points over 9000*
//insert transparent piece image here

This transparent acrylic cover will cover the OLED, I used my cutting table to make it
but you can use a laser cutter to cut it out as well. If you do decide to include this, 
replace the bottom 2 M3x6mm screws holding the cover piece to the PCB cover and replace 
it with 2x M3x10mm screws
//insert image here

# Special thanks to:
NicoHood for developing the HID library and
Henning Karlsen of Rinky-Dink Electronics for developing a 
lightweight OLED library. DroneBot workshop for providing the 
basic code to run the 74HC165 PISO shift register.



