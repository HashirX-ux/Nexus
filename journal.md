# Project Journal

**Project Name:** Nexus  
**Start Date:** 2026-07-07  
**Status:** In Progress

## Overview
Nexus is a wireless 3x4 macropad built to optimize your workflow. It uses a nice!nano for Bluetooth LE. It features 12 hot-swap keys illuminated by a vibrant per-key RGB lighting array. A tactile EC11 rotary encoder and an OLED screen offer precise macro control. Powered by ZMK firmware, it brings seamless multi-device pairing anywhere you go.

## Recent Entries

### 2026-07-07 - First Journal Entry

**What I did today:**

I amn gonna start researching about my Macropad built for productivity named Nexus for it's components and elemensts. Since I have never created a macropad, It's gonna take a while.. 

<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/c92d8ec6-ea53-4997-9dda-cd15de4c6364" />

Since I am making a productivity macropad, I need to use such MCU that supports wireless bluetooth capability. From My research I think nicenano-v2 would be best for my macropad 

<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/dd204836-b0dd-4d4f-a3cd-0fa7c93889fa" />
<br>
> So I have summarized all the necessary components for a macropad. 
<br>
1- MCU -> nicenano!-v2 (It acts as the brain of the macropad and controls most all the operations)
<br>
2- Diodes(1N4148)
<br>
3- Mechanical Switches -> Gonna use Kalih or Gateron Switches and probably will consider Cherry MX)
<br>
USB-C(Gonna make it wired also) 
<br>
4- Capacitors and Resistors for Maintainance for powersupply

<br>
> I am gonna add some customs also for my macropad.
<br> 
1- OLED Display (Gonna show its battery percentage and connected devices) 
<br>
2- RGB lights(WS2812B) for Asthetics ifykyk
<br>
3- Rotary Encoder(EC11) No idea Why I am adding this (asthetics)
<br> 
<br>
Now I am gonna start researching about all the components one by one.. <br>
1- nicenano!<br>
Since nicenano has two versions I am gonna research about the latest one and use that.. <br>
Gonna use the official nicenano documentation for research about nicenan<br>
https://nicekeyboards.com/docs/nice-nano/<br>
This is how the nicenano pinouts look like: <br>
<img width="1143" height="769" alt="image" src="https://github.com/user-attachments/assets/dc2c1f22-19a7-4527-88d7-5fce4af68154" />
<br>
<br> 
So I gotta use ZMK firmware for my macropad since its wireless via bluetooth capability.. <br>
The Schematic looks intimidating but it's simple .. I guess<br>
<img width="1220" height="753" alt="image" src="https://github.com/user-attachments/assets/1e21c9e7-f54f-4fe3-bd53-e7b4149902f0" />
<br>
<br>
Now I am gonna read some datasheets of the Diode (1N4148) specifically designed for macrpads and keybaords.. <br>
So these are the Diodes I am gonna be using<br>
<img width="1165" height="766" alt="image" src="https://github.com/user-attachments/assets/decdaf9b-7335-436c-9630-85f0572f6c47" />
<br> 
These diodes are really efficient for keebs and pads :D 
<br>
<br>
Now I am gonna research about the USB-C device that I am gonna use in my macropad cuase I wanna make my prodcutivity macroapd boht wired and wireless sor for wired capability I am gonna have to use USB-C<br>
<img width="801" height="525" alt="image" src="https://github.com/user-attachments/assets/18322748-b7d4-4a4d-bfff-fd65d3bbc1a9" />
Gonna use USB 2.0 as it provides 480 mps and takes 5V with 500mA
<img width="1119" height="559" alt="image" src="https://github.com/user-attachments/assets/4fd78748-73cf-4e6a-bef1-e8d8ea1f820e" />
<br> 
Best Guide to Study USB-C:<br> 
https://www.ti.com/lit/eb/slyy228/slyy228.pdf?ts=1759892558029
<br>
Looks Like I am cooked :((
<img width="313" height="580" alt="image" src="https://github.com/user-attachments/assets/25e43fd6-6c39-4b26-8855-9b21de5d169c" />
Now I think I have gained enough info about USB-C, Moving to the next componentttttttttt.
<br>
<br>
Now I am gonna start Researching about the capacitors and the resistors that are required for macropad and are essential for the Power Management accross the PCB<br>
Found a New component to research about: 
<img width="1280" height="695" alt="image" src="https://github.com/user-attachments/assets/f7212ff8-13c4-4fc9-a217-878d114db894" />
So bascially a crystal tells how fast the chip processes but I don't really have to build it since it comes pre-built with nicenano!-v2 chip so Im save :D:
<img width="1280" height="679" alt="image" src="https://github.com/user-attachments/assets/087d0d21-26cb-4090-8855-de3aa72a6ce1" />
<br>
<br>
Now I am gonna research about Capacitors that are needed in my macropad:<br>
Guess I don't need any caps at all except I think for my RGB lights.. 
<img width="668" height="220" alt="image" src="https://github.com/user-attachments/assets/6b81a049-0ae2-4cf5-94ed-47b6cf714e22" />
<br>
<br>
I do have to also add a RESET button on my schematic for my nicenano! to go bootloader mode for my ZMK configuration: 
<img width="596" height="300" alt="image" src="https://github.com/user-attachments/assets/042947e2-6cb0-4fbf-ab41-e1a08d6ef0b5" />
<br>
I also need some decoupling caps that are gonna stablise the power supply across the circuit: 
<img width="845" height="604" alt="image" src="https://github.com/user-attachments/assets/065d9483-65f8-483a-b7a9-f04a1c6cfcc1" />
Fair Enough.. So I gotta maintain the power supply by at least adding one or more decoupling or bypass caps so that power accorss my Circuit stabilised in high and low voltages: 
<img width="1252" height="938" alt="image" src="https://github.com/user-attachments/assets/62eba0c9-9000-4087-b2c0-f18d714bd843" />
<br>
Interesting.. 
<img width="1209" height="397" alt="image" src="https://github.com/user-attachments/assets/1899def5-2314-4e6d-91fe-4053cd4f6a8d" />
<br>
Learned about a new concept called "impedance". Basically it refers to opposition a component or circuit offers to the AC: 
<img width="897" height="128" alt="image" src="https://github.com/user-attachments/assets/28fb897f-9b7f-4c1b-bea7-7e0645a4dc39" />
<br> 
Best Wbsites I have visited to study about Decoupling capacitors and value of 100nF and why is it important and what significance this specific value holds.. : 
<br>
https://pcbsync.com/100nf-capacitor/
<br>
https://learn.sparkfun.com/tutorials/capacitors/application-examples
<br>
<br> 
Now I am gonna start researching about the resistors that I need for my macropad:<br>
Looks like I don't really need the resisotrs for my macropad: 
<img width="1280" height="895" alt="image" src="https://github.com/user-attachments/assets/ac9e9768-e35c-487c-990f-0c4995e6f68b" />
<br>
But I think I do need them for my RGB lights for the key switches.. 
<img width="1280" height="787" alt="image" src="https://github.com/user-attachments/assets/64104622-7db5-4a7d-9a57-56be968ac55b" />
<br>
So the common resistors are 220 ohm and common caps are 100nF
<br>
nicenano! v2 gives the output login of 3.3V and take 5V from the USB input So i gotta be carefull before adding some resistors as they can limit the cuurent that is required by the RBG lights as they require much higher voltage(around 5V) so I only need to add like 1 resistors for every 2 RGB light to stablise the connection 
<br>
I also need a bulk Capacitor according to the lights I am gonna use which are RBG WS2812B
<img width="1280" height="845" alt="image" src="https://github.com/user-attachments/assets/8a250b00-f2c4-4d53-bdda-21048b9c6153" />
<br>
This is gonna store the voltage when the line surges or drops.. Interesting: 
<img width="1280" height="746" alt="image" src="https://github.com/user-attachments/assets/ca761cef-8dcf-46eb-8bdb-187afebd3420" />
<br>
THANK GODDD!!! IM SAVED.. I thought I would also need to build a voltage regulator for my macropad but I think I don't have to now :D
<img width="1280" height="746" alt="image" src="https://github.com/user-attachments/assets/07f73de0-6c8e-4d21-a315-f21be29b67de" />
<br>
So the 330 ohms is the one I am targetting: 
<img width="861" height="346" alt="image" src="https://github.com/user-attachments/assets/460c52d2-5c7f-4dc0-b401-5357ee74edc7" />
<br>
<br> 
Now I am gonna research about the Rotary encoder I am gonna use for the macropad:<br>
So there are two rotary encoders am I am considering to use on of them.. One is PEC11R and the other encoder is EC11. I have researched and most of the resources recommend using the EC11 for a DIY- macropad cause it's the most industry standard and commonly used for macropads..
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/aa83f025-bdfe-4004-9d70-befebb22676e" />
<br>
So this is the EC11 Rotary encoder: 
<img width="513" height="464" alt="image" src="https://github.com/user-attachments/assets/bf4f9768-20b5-4f03-baa8-2093cda6c182" />
<br>
So the EC11 Rotary Encoder uses DC voltage of 3.3V which is perfect for my nicenano!-v2 MCU :D
<img width="1280" height="800" alt="image" src="https://github.com/user-attachments/assets/952033df-83b5-465a-9848-235f9204eec7" />
<br>
<br> 
Now I am gonna start working on the KeySwitches of ny macropad:<br>
One of the best Guides I have read for the key  switches
https://www.theremingoat.com/blog/beginners-guide
<br>
So this is the Cherry MX switch. Looks pretty fine to me as it also metions that this key switch makes that "click" sound when you clikc it so I guess it's pretty cool :D
<img width="779" height="783" alt="image" src="https://github.com/user-attachments/assets/1726e908-4fa0-49a8-bc13-ea4937ba0186" />
<br>
It seems pretty tempting to use Cherry MX keys.
<img width="889" height="498" alt="image" src="https://github.com/user-attachments/assets/17e42081-38cf-44eb-8cbd-87d12f759894" />
<br>
Although Cherry MX keys looks a really good and reasonable choice, I am still gona search gonna search for more good and those "clicky" sound keys as I am reallt OBSSESED with them.. 
<br>
I think Kalih switches are also a really great Option to use but I gotta do a a liitle more research but I think i am considering to use Kailh swutches for my Macropad cause I think they look a little bit more beautifull than cheryy for some reason especially the kailh red switch is really attractive to use to I think I am gonna consider to use Kailh Switches and I have planned to use 12-key switches for my macropad and the matrix I am gonna use will be 3 x 4 :D
<br>
<br> 
Now I am gonna research about the battery that I am gonna use in my DIY-Macropad and for that I am gonna use nicenano! official documentation cause the have specified which battery to use to the Microcontroller.. 
<br>
https://nicekeyboards.com/docs/nice-nano/
<br>
Since I am also using the LED lights which is gonna take more power so I can't use the battery given in this documentation: 
<img width="951" height="414" alt="image" src="https://github.com/user-attachments/assets/5fd4a0ae-7cde-4315-b2a9-afed9157702e" />
<br>
Hence I am gonna use a 1500mAh battery for my DIY- Macropad. that is gonna help me maintain the electricty in the macropad when The bluetooth wireless capability is turned on .. 
<br>
This guide is really helpfull as it really helped to understand How schematics work and How I should design my own custom PCB and macropad :D. I didn't read it full though but gonna read it cuz its describes how pcb works and how to design their schematics :D<br>
https://github.com/ruiqimao/keyboard-pcb-guide#schematics
<br>
I researched about pull-up resistors and seems like I don't to place any external pullup resistors case nicenano! is TOOO GOATED!!!!!!!!. You can literally configure the power supply from the ZMK :D<br>
Here is the resource I used to read about the pullup resistors and it's really goated... :D<br>
https://learn.sparkfun.com/tutorials/pull-up-resistors<br> 
<br>
<br>
Since It's my firt time bulding a macropad so I am gonna read some of the guides on how to build that form absolute 00000000...
<br>
Found another guide on how to build a macropad form scratch. LET'S READDD<br>
https://medium.com/@timowielink/how-to-build-a-macropad-d5a154311c4c
<br>
The difference is I am gonna use a nicenano!-v2 microcontroller instead of ESP-32 MCU so I think there will be places Where I am gonna get stuck on This guide but let's hope for the best. :D
<br>
<br> 
Shoot.. I forgot to research about the OLED I am gonna use on my macropad. Lemme get that real quick:
<br>
I researched about which OLED to use and I came accross an OLED Which was also by nicenano! called niceview! and it seems pretty interesting since I have the same Microcontroller and as well as its OLED screen which it perfectlly suits.
<br>
https://nicekeyboards.com/docs/nice-view/pinout-schematic
<br>
This is the device I am planning to use as my OLED :D
<img width="740" height="850" alt="image" src="https://github.com/user-attachments/assets/9ec44fca-232a-47b0-b887-f6d7364735fe" />
<br>
And this is the schematic of the niceview!: 
<img width="1202" height="625" alt="image" src="https://github.com/user-attachments/assets/cbc058ca-d8c2-43be-b09c-0df8f501ca70" />
<br>
This guy built a Macropad and open sources it:<br>
https://github.com/imchipwood/dumbpad
<br>
Found about these low profile switches .. Don't know what do they even do..
<img width="1218" height="735" alt="image" src="https://github.com/user-attachments/assets/b21c05ed-1498-4f29-80e9-f5f9597cb0b9" />
<br>
12C devices are quite interesting :D
<img width="886" height="340" alt="image" src="https://github.com/user-attachments/assets/49943d9b-fe4d-4654-80d3-0911100e5d35" />
<br>
A really good guide reguarding OLED and 12 protocol explanation..
<br>
https://blog.tinkercademy.com/deep-dive-into-the-i2c-oled-413fee46ada1
<br>
Ok I might consider using an OLED of 0.96": 
<img width="722" height="397" alt="image" src="https://github.com/user-attachments/assets/b1c6985b-8b78-422a-942a-3dabd69fe67f" />
<br>
I am gonna search for some routing tips and I think I have found a great website for that.
<br>
https://www.pcbway.com/blog/PCB_Design_Layout/Common_Rules_for_PCB_Routing_29d86598.html
<br>
Didn't knew that greater loop would cause more heat and radiation during the routing of the PCB..
<img width="1110" height="868" alt="image" src="https://github.com/user-attachments/assets/cad690b7-f772-4a65-9033-6bff5e99ef23" />
<br>
So i gotta make smaller loops in my routing so that I coukd avoid ekectromagnetic interference and unwanted noise.. 
<img width="1090" height="264" alt="image" src="https://github.com/user-attachments/assets/45cf2fb9-b0f2-49b1-a932-316d32e2d5fc" />
<br>
I've found that de coupling capacitors help in reducing the electromagnetic interferance by maintaining the noise to signal ratio in the PCB so it's really a good practice to add bunch of those :D
and certainly 100nF is the best capacitor for balancing the pwoer in the PCB 
<br>
I also wanna learn about the 3D case design so I found an incredibally helpfull resouce to help me with that.. 
<br>
https://www.makerluis.com/step-by-step-guide-parametric-macro-pad-on-fusion-360/
<br>
I also found a video of this incredble Guy and he bascially gave a full tutorial on how one can design their own custom macropad case which is really helpfull. Hats off to this guy gng..
<br>
https://youtu.be/egOOHS-34-c?si=lpAW9fYHbgnp78mD
<br>
I think fusion 360 is currently the best 3d case software out there cause I have researched a lot on the 3d case for the macropad and Its showing me a fusion 360 tutorial every single time.. 
<br>
I Found the official hackclub's guide on designing a hackapad (Don't even know what that is) 
<br>
https://hackpad-v2-backup.pages.dev/guide#bottom
<br>
Since I am building a wired and wireless macropad I am gonna be using ZMK firmware for my macropad even though I have no idea what that even is in the first place So gonna research aobout it.. Wish me luck.. gang..
<br>
The ZMK docomentation is really helpfull for this :D
<br>
https://zmk.dev/docs/hardware
<br>
This guide is also really helpgull. Currently reading it ....
<br>
https://medium.com/@Myphis/zmk-firmware-unleashing-the-power-of-keyboard-customization-ed9fa9f8468e
<br>
So according to my summary QMK is for wired keyboards and ZMK is usually for wireless keyboards but ZMK can also be used for wired keyboards by having microcontrollers such as RP2040 wtc which I am not using for sure.. 

### 2026-10-08 - Second Journal Entry

**WHat I did Today:**
So Today I am gonna create the schematic of my Nexus aka macropad and its gonna be fun hopefully and I have already Researched about all the components that I need to build the schematic and Now I have to just make the schematic and then I'll be done with the schematic part. I am gonna build me schematic on KiCad.. 
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/3ae0c8e4-d65a-4cae-88ae-1148a80d8c06" />
<br>
I have created a keyboard type matrix for the macropad with a 3 x 4 matrix as I described earlier ny using a keyboard design guide from the resource https://www.nextpcb.com/blog/how-to-design-mechanical-keyboard-pcbs-with-kicad.. Looks cool to me. 
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/491050bf-41d6-4e37-a1d1-9f10fdeb6745" />
<br>
<br>
Now I am gonna start building the USB-C 2.0 16P schematic on the KiCad and it has a complete guide om how to set it up on the ncienano! official webiste and documentation so I am gonna read that real quick.. 
<br>
https://nicekeyboards.com/docs/nice-nano/pinout-schematic
<br>
I still can't figure out the function of the CC1 and CC2 pins of the USB-C 2.0 :((
<img width="1012" height="502" alt="image" src="https://github.com/user-attachments/assets/daafda54-2858-4306-97f6-9187631b868f" />
<br>
Guess I am done with the USB-C configuration and Now I am gonna move to my next component..
<img width="901" height="755" alt="image" src="https://github.com/user-attachments/assets/8e3e9b22-7350-4374-8049-e2fb6a73b6c1" />
<br>
<br>
Now with that being said I have somehow confiured my rotary encoder and have connected it to my Microcontroller and Now what it is gonna do is send signals to my macropad whenther it is getting pulled clockwise and will tell the microcontroller which in this case is nicenano! v2 to react in accordance to those signals 
<img width="478" height="240" alt="image" src="https://github.com/user-attachments/assets/5aab1e75-8d15-4958-9c47-51744d9859b7" />
<br>
<br>
Now I am gonna add a RESET switch and what it will gonna do is to make the Microcontroller, which in this case is nicenano, enter in a bootloader mode so that you can Literally drag and frop your ZMK firmware file in the USB device of the microcontrolle which will show up when it enters in the boot loader mode.. 
<br>
<img width="391" height="229" alt="image" src="https://github.com/user-attachments/assets/f7f95ee7-bc0a-4f84-b2df-3b546c0c55af" />
<br>
Just Found another helpfull resource for the Reset button guide :D
<br>
https://binaryupdates.com/switch-with-8051-microcontroller/
<br>
<br>
So Instead of using the classis 0.96" OLED, I used 0.91" OLED cause I couldn't find the symbol of the OLED 0.96" anywhere so I had to use OLED 0.91 but it's completely fine cause I guess 0.91" is more common among these DIY-macropads and I also cinfigured it in KiCad amd it's pretty simple :D
<img width="644" height="583" alt="image" src="https://github.com/user-attachments/assets/9f4ad03a-61b2-49fb-90a1-3aa0e77c773b" />
<br>
I have aslo creatd 2 decoupling caps for power management and they bascially manage the input power and high voltages that comes in the boara and these actually play a really vital role on the board :D
<img width="686" height="679" alt="image" src="https://github.com/user-attachments/assets/94b926ff-7eec-4228-bbc2-a0ff7cee6c58" />
<br>
Now I am gonna add power management by thr battery cause my macropad is also wireless and as well as wired so I have researched and read what kind of battery Do I need form the nicenano"s official documentationa and its lithiu-Ion battery with 3.7V:
<br>
https://nicekeyboards.com/docs/nice-nano/
<br>
I think this is the battery that I need to store my power.. 
<img width="988" height="583" alt="image" src="https://github.com/user-attachments/assets/b429b571-f955-415b-877f-5091a1ea83b0" />
<br>
So I have used Conn_01x02 for my lithium battery and I also have set the capacity to 15500mAh which I think is decent for a macropad and I think it will makes my macropad atleast long lasting than those stupid Iphones(Saying that cause I can't afford one) 
<img width="856" height="326" alt="image" src="https://github.com/user-attachments/assets/6cd1b0de-c434-47d8-b877-a59fe039c19a" />
<br>
For charging the battery I have used MCP73183-2-MC charger which is industry standard for Lithium-Ion batteries and It's also really easy to setup in the editing software which for me is KiCad :D
<img width="867" height="547" alt="image" src="https://github.com/user-attachments/assets/080f54fc-fc78-498c-a39d-26861bd2f63d" />
<br>
Nicenano! is super underated. I doon't even need a power regualtor to maintain my LED lights !!!!!!!!!!!!
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/0b524623-81c6-41fb-8fcf-a5eb2106848a" />
<br>
Since my microcontroller which in this case is nicenano! outputs only 3.3V and my LEDs need like 5V of ouput voltage so I am gonna use a component which i found out which is 74AHCT123. This components bassically increases the voltage of the output 3.3 and makes it 5V and so its is really clear for my LEDs and I am gonna use this component: D
<img width="351" height="357" alt="image" src="https://github.com/user-attachments/assets/57ccbe99-1de1-46ee-a675-fa1edb4d538e" />
<br>
I also need to place a decoupling cap for my LED for it to be stable :D.. 
<img width="466" height="686" alt="image" src="https://github.com/user-attachments/assets/b3cac68c-7744-4018-ba5e-d08778b686d0" />
<br>
<br> 
Now I am gonna start Configuring out my MAIN BRAIN!!!! not literally I am talking about nicenano. I am gonna add all the new pins in the nicenano and then gonna configure it out.. 
<img width="529" height="748" alt="image" src="https://github.com/user-attachments/assets/5519d6bc-6bd0-4bf3-9082-4250ea3e9ece" />
<br>
I also gotta add the key matrix on my nicenano! chip.. 
<img width="746" height="656" alt="image" src="https://github.com/user-attachments/assets/aa329b38-99a6-4f3d-908a-02e5db9582df" />
<br>
Its kinda hard but I am still figuring it out.. 
<br>
Now I am gonna add some RGB Lights for my macropad keys but I gotta find how can I do that and study the function of the each pin of the LED so that I can easily connect it to my keys :D..
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/529e0291-a238-48e0-879a-cf8df4e91794" />
So this is how an LED is designed gng.. I think I am learning some great great stufffffff.. its just an LED brooo. anyways..
<img width="1278" height="1024" alt="image" src="https://github.com/user-attachments/assets/1d26198d-0e9e-462b-a455-64869e893c75" />
<br>
Done with the first Row gng. Now I gotta do 3 more rows so that it matches my matrix of 3 x 4. Then I'll have an LED for each of my key in the macropad and its gonna be dunn :D
<img width="1280" height="652" alt="image" src="https://github.com/user-attachments/assets/fdb15be4-d89b-459e-9bf4-868978f4b26b" />
<br>
Donw with 2 ROWSSS
<img width="1280" height="765" alt="image" src="https://github.com/user-attachments/assets/90d10518-3742-4724-bec7-1d1beac523ac" />
<br>
So I have made thhe RGB key matrix and it looks really good to me :D. Now what's gonna happen is my keys of the macropad will have their own RBG lightining for them to shine.. YAYAYAYA
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/dd2cacca-bf8e-4f73-8a75-a35c8afc8ff7" />
<br>
So I have also planned to add a buzzer so that it can also make those clicky sounds to make the macropad more satisfyign and addictive to use. SO I am GONNA MAKE YOU AN ADDICT HAHAHAHA
<img width="989" height="477" alt="image" src="https://github.com/user-attachments/assets/d6b60f10-71ff-4bc0-9284-ba09ce58f3c7" />
<br>
So Now I am gonna configure my whole schematic and make it look a more good and managable.. 
<br>
After Debugging SOO many erors running ERC like a madman, I finaly have 0 ERRORS!!!!!!!!!!!!!!!!!!
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/95da2ffb-ff20-4ed6-aed0-fdc7c820dd8a" />
<br>
I still have 4 warnings but they dont matter gng.. hopefully
<img width="345" height="186" alt="image" src="https://github.com/user-attachments/assets/cd521a2f-32b2-4c2f-b0e1-e47e97d7c811" />
<br>
Gonna start arranging ts gng.. Wish me luck ...
<img width="1280" height="1010" alt="image" src="https://github.com/user-attachments/assets/91743dbc-0c29-4f21-9cc2-5529b2df4d9a" />
<br>
LOOKS SOOO CLEAN... YAYYAYAYAY
<img width="1279" height="1024" alt="image" src="https://github.com/user-attachments/assets/04a2ee10-ad0f-4226-ad2e-8a6467cd4bd1" />
<br>
It Even Looks more clean since I have named every Single component in the schematic.. 
<img width="1280" height="1024" alt="image" src="https://github.com/user-attachments/assets/7afae4f7-5e52-46c7-a064-2f04b2e97ede" />
<br>
GUYSSS ... After 11 DEVASTATING HRS.. I HAVE FINALYYY COMPLETED MY SCHEMATIC!!!!!!!!!!! YAYAYAYAYAYA
<img width="1280" height="981" alt="image" src="https://github.com/user-attachments/assets/c1ba7300-9b2f-4b4f-8da9-fe31e3a0881a" />
<img width="1280" height="988" alt="image" src="https://github.com/user-attachments/assets/38b783ad-4250-4780-bdb2-e2094186b278" />















