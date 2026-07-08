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








