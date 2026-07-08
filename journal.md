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











