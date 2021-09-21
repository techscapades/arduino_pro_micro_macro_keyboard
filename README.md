# arduino (pro) micro macro keyboard

![Best rendering (3)](https://user-images.githubusercontent.com/76870663/133833800-85e0ed2d-d4ae-48e4-a4c3-c7bc171ead55.png)


A macro keyboard using Arduino (pro) micro with selectable macro profiles
and an OLED screen to indicate the profile selected. It uses a PISO shift
register to determine what key is pressed instead of a diodes and resistors.
It uses Cherry MX switches or clones of it to really capture that keyboard feel.
It can do a lot more than simulate key presses though, it can replicate a mouse, 
launch programmes and much more! I've left an easter egg in profile 5 :).

I built this macro keyboard because I was spending way too much time with
repetitive keystrokes, I also needed a quick way to trigger media functions without 
needing to switch windows. The ones in the market were way too expensive
and finally, after looking up many designs of people who've built their own
macro keyboards and finding only a few with a display, none of them could meet my
criteria, thus I had to build my own. 

I decided to implement an OLED display that's compact and instead of a diode-resistor
configuration I've decided to go with a shift register instead, simply because
the complexity of the PCB is brought way down with fewer components to fail
and its a lot easier to replace a socketed dip-16 IC than it is to desolder
a diode and the number of GPIO pins I save using a shift register allows for future
expansion.

Apart from the code and required libraries, the PCB gerber files, 3D CAD files 
for the housing, parts list and snapshots of the different skews are included 
as well. Do note that the Arduino (pro) micro that is compatible 
with the current PCB and 3D CAD is 17.9mm in width and it has either 
USB type C or micro-usb connector, the mini-USB version will not fit!

# Features:
1. OLED display
2. Profile selector button
3. Reset button
4. Rotary encoder
5. By default there are 18 possible macro combinations per profile
   but it can go up to 22 for normal humans and 254 for
   geniuses who can remember that many combinations, but 
   do mind the amount of available memory

##### Blown up view of components:
![Blown up view with labelled parts _1](https://user-images.githubusercontent.com/76870663/133823503-fe2c02ee-ff41-4271-988d-6cbe7a4aba0b.png)


# Code and usage:
1. Ensure you have the Arduino IDE installed
2. Download and unzip 'required libraries.zip' and 'arduino_micro_shift_register_piso_rot_enc_psbtn_OLED_V3.zip'
files. 
3. Go to the 'libraries' folder in your arduino installation and paste the 2 subfolders inside the 'required libraries'
folder into the 'libraries' folder in your arduino installation. 
4. Then open the arduino_micro_shift_register_piso_rot_enc_psbtn_OLED_V3.ino file.

How to modify the code to suit you is explained in this youtube video:
https://www.youtube.com/watch?v=DriOpHgIRV4

Dont hesitate to drop me a message if you need additional clarification,
I'll get back to you as soon as I am able to.

# PCB:

##### Top:
![topPCB](https://user-images.githubusercontent.com/76870663/133747172-58dd6b49-5fd8-4458-9180-8375bdfa83fc.PNG)

##### Bottom:
![btmPCB](https://user-images.githubusercontent.com/76870663/133747183-221e5132-7f5a-4eae-aa7a-4d27b3652546.PNG)

The current PCB uses cherry MX or similar key switches as buttons,
feel free to use any switch you like! The 10K resistors on the side 
can either be in the SMD 2010 from factor or THT. If you're using the
SMD 2010 form factor resistor, you have the option of soldering them either on
the top or bottom of the PCB depending on which version of the CAD 
housing you want to print. If you want to see how both skews look, scroll
down to the next section or open 'comparison.png' in the snapshot folder.

I used JLCPCB.com to make the PCB, they're pretty fast and reliable, hence the 
"JLCJLCJLCJLC" on the bottom side. I put that there because I wanted the ugly 
order number to be hidden from view, if you do use JLCPCB.com to make the
PCB, upload the entire "PCB_Gerber.zip" file and make sure under "Remove Order Number" 
you select 'Specify a location', its at no extra cost.

![jlcpcb remove order number](https://user-images.githubusercontent.com/76870663/133786011-6cd00bef-3afd-4ec0-a69d-d0eb82e8677c.PNG)


##### PCB components: (all links available in 'parts list pdf.pdf' file)
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

##### IMPORTANT NOTE: YOU NEED TO SOLDER THE COMPONENTS IN A CERTAIN ORDER!
Soldering order as follows: 
1. Solder the SMD or THT resistors 
2. Solder the 12mm tactile switch to the top of the PCB
3. Solder the DIP-16 socket or 74HC165 directly to the PCB with the 
   identifying indented notch on Pin 1 pointing towards the left where the
   "O" on the PCB is
   
   ![PISO orientation](https://user-images.githubusercontent.com/76870663/133743000-68bef616-6126-4ed6-a268-ae768a9edbbb.jpg)

4. Solder the Arduino (pro) Micro to the bottom of the PCB
5. *Optional* snip off the Micro's pins that extend from the top of the PCB
6. Solder the 2x 4pin female PCB header pins for the OLED
7. Solder all the Cherry MX or clone key switches
8. From the bottom of the Rotary encoder, remove the extra black plastic 
   holding the male header pins and attach a piece of tape to the bottom 
   of the rotary encoder covering the resistors etc.. This is done to 
   stabilise the rotary encoder. I used the tip of a wire cutter to remove it.
   ![rotary encoder](https://user-images.githubusercontent.com/76870663/133743059-7414ecbf-2354-4741-af97-59057a1d5861.jpg)

   One tip to ensure the encoder is level, is to dab a little soder on
   1 pin and then holding the soldering iron to the pin with the soder
   on it and straightning the encoder. Its a little tricky but take your time
   
9. Solder the rotary encoder to the top of the PCB
10. Finally, remove the extra black plastic holding the male header pins
    of the OLED display and snip about 2mm off the bottom and put some 
    double sided tape on the bottom right side of the OLED. Place the OLED
    display in the 4 pin female PCB header pins to test the height and ensure
    its sitting level and it's right side rests on the other 4 pin female PCB header.
    ![OLED with tape](https://user-images.githubusercontent.com/76870663/133743126-afad81fb-9c8a-4c64-97a9-471e8f578c06.jpg)


Congratulations, you're done! If you have a multimeter, I recommend that after
every step of soldering, you go into continuity test mode and check that your 
connections are solid and you haven't shorted or connected any pins together 
or you'll be in for a bad time. I also recommend ensuring all your cherry MX 
or clone key switches work before soldering them on to the PCB. 

If you've never done a continuity test before, you hold one probe to one pad 
or pin and then the other to the part it's supposed to be connected to, 
either a PCB trace or a neighbouring pin. If the multimeter buzzes, a connection
is made, whether or not thats a good or bad thing will depend on whether a
connection is supposed to be or not to be made. 

# 3D Printable CAD housing

![top](https://user-images.githubusercontent.com/76870663/133743212-94336877-8aea-47c0-ba61-f0fcef568430.jpg)

The main components of the housing are the PCB cover and the housing base.
You can choose to laser cut the PCB cover if you want. 
Raw CAD files are in: 3D CAD files folder > raw step files. 
STL files are in: 3D CAD files folder > stl files.


There are 2 versions of the PCB cover, one version is when the SMD or THT
resistors are soldered to the top of the PCB, the other is when the
SMD (only) resistors are soldered to the bottom of the PCB, snapshots of
what both versions will look like are in the 'snapshots' folder. I decided to
solder my SMD resistors to the top of the PCB as I quite like the look of it.

![comparison](https://user-images.githubusercontent.com/76870663/133802271-422d9830-7a59-47fb-8ac0-c105209ace5a.png)



##### Mounting options
You have plenty of options for mounting the PCB to the housing base since I've 
made the holes slightly smaller which gives you the option to use self-tap screws 
or machine screws with nuts or machine screws with tapped holes; you can literally use 
whatever you have at hand but keep in mind that the screws I intended to use are M3 
so make sure you have the correct size.

I've opted to drill 3mm holes in the housing base and PCB cover, then used M3x20mm 
screws with plastic M3 spacers to fasten the screw from the bottom of the base
to the top of the PCB cover. Finally, I've added anti-slip pads to the bottom of
the housing base to prevent it from slipping.
![spacer on top](https://user-images.githubusercontent.com/76870663/133743559-5d0273db-4318-4f8a-bff7-8865eb46164d.jpg)
![screwed from btm](https://user-images.githubusercontent.com/76870663/133743538-b4765846-7aea-4449-977e-98ccd37b51cb.jpg)
![btm](https://user-images.githubusercontent.com/76870663/133743384-ae5d4253-643d-42cc-ab7f-80addf39dc2b.jpg)


## *Optional- Cover piece for extra style points*
![cover piece](https://user-images.githubusercontent.com/76870663/133743341-77e2853a-af4c-4b08-b9e1-0098dc504f5f.jpg)
![cover piece alone](https://user-images.githubusercontent.com/76870663/133743348-bb87dc2f-7787-4d66-9914-806b5c352703.jpg)


The additional rotary encoder/reset button/OLED cover piece is nice but not necessary.
If you do decide to 3D print or laser cut it, you will need to:
1. Ideally tap M3 threads into the 3 holes in the PCB cover or less ideally
   heat up an M3 screw and screw into the cover piece to create the thread
2. Screw 3x M3x6mm brass spacers into the holes
![spacer on pcb cover](https://user-images.githubusercontent.com/76870663/133743668-c0b9c0dd-6af3-4ed8-be22-b2bc398a15db.jpg)


3. *optional* drill 4mm holes into the cover piece if the screws dont go in right


## *Optional Optional- Transparent acrylic OLED cover for style points over 9000*

![transparent piece](https://user-images.githubusercontent.com/76870663/133743489-49b7076f-709e-4aaf-9005-3c991c47e674.jpg)


This transparent acrylic cover will cover the OLED, I used my cutting table to make it
but you can use a laser cutter to cut it out as well. The thickness of the clear acrylic should
be from 1 to 3mm, the thinner it is the better. If you do decide to include this, replace the 
bottom 2 M3x6mm screws holding the cover piece to the PCB cover and replace it with 2x M3x10mm screws


![transparent piece on assem](https://user-images.githubusercontent.com/76870663/133743481-73602a66-7da9-410e-b588-e2e9209e35b4.jpg)


# Special thanks to:
NicoHood for developing the HID library and
Henning Karlsen of Rinky-Dink Electronics for developing a 
lightweight OLED library. DroneBot workshop for providing the 
basic code to run the 74HC165 PISO shift register. Their 
libraries are included in the ZIP file. 



