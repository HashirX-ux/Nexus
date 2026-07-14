# Nexus

[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](./LICENSE)
[![Status](https://img.shields.io/badge/status-in%20progress-orange?style=flat-square)]()
[![MCU](https://img.shields.io/badge/MCU-nice!nano%20V2-black?style=flat-square)]()
[![Firmware](https://img.shields.io/badge/firmware-ZMK-00599C?style=flat-square)]()
[![Wireless](https://img.shields.io/badge/wireless-BLE-blueviolet?style=flat-square)]()

> A wireless 3x4 macropad i'm building to speed up my workflow. Hot-swap switches, per-key RGB, an OLED screen for status, and a rotary encoder for macros. Works wired or wireless.

---

## What is it?

Nexus is a custom 3x4 (12 key) macropad i designed mainly for shortcuts and repetitive commands i was tired of typing out. Built around a nice!nano v2 so it can do bluetooth LE, with USB-C as a backup if the battery dies or i just don't feel like pairing it again. 12 hot swap sockets, per key RGB underneath, an EC11 rotary encoder, and a little OLED that shows battery % and what its connected to.

(quick note to future me: the tagline used to say QMK somewhere, thats wrong, QMK doesnt really do BLE on this board properly so i switched to ZMK. fix that if you see it anywhere else)

## Why build it

Because reaching over to a full keyboard just to hit a macro or shortcut combo got annoying. If i build the layout, lighting and firmware myself it actually fits how i work instead of some generic layout someone else made.

---

## Status

Research + design phase mostly done, now just cleaning stuff up. Schematic and routing still need some touch ups here and there. Full build log with all the component reasoning is in [journal.md](./journal.md) if you wanna see why i picked what i picked (spoiler: half of it was just "this was in stock on lcsc").

- [x] Component research (MCU, diodes, switches, USB-C, passives)
- [x] Schematic design
- [x] PCB routing
- [x] PCB fabrication
- [x] Firmware pin mapping
- [x] Assembly
- [x] Case design

---

## Planned Specs

| Component | Choice |
|---|---|
| Layout | 3x4, 12 keys |
| MCU | nice!nano v2 (nRF52840) |
| Connectivity | Bluetooth LE (wireless) + USB-C (wired) |
| Switches | Hot-swap, MX-compatible (Kailh / Gateron / Cherry MX) |
| Matrix diodes | 1N4148 |
| RGB | Per-key, WS2812B |
| Encoder | EC11 rotary encoder |
| Display | OLED - battery % + connected device |
| Firmware | ZMK |
| USB | USB-C, USB 2.0 (480Mbps, 5V/500mA) |

---



```
```

Tried to keep this organized roughly the way hack club's [hardware codex shipping guide](https://codex.hackclub.com/shipping/101/) recommends - source files seperate from the manufacturing stuff so its easier for someone else to just grab and rebuild.

> If you dont wanna open kicad just to look at the board, theres a KiCanvas link so you can view it in browser:
> [![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?github=https://github.com/HashirX-ux/Nexus/tree/main/pcb)

---

## Build log

Most of the actual thinking (datasheets i looked at, why i swapped parts, dumb mistakes i made along the way) is in [journal.md](./journal.md). Genuinely recommend reading it if your building something similar, its more useful than just staring at the BOM.

---

## Roadmap

1. finalize schematic (matrix wiring, rgb data line, oled i2c, encoder pins, reset button)
2. route + order the pcb
3. build/test zmk firmware against actual pin assignments (not just what i think they are)
4. design + print the case
5. assemble, flash, pair, hope it works first try

---

## How to build

### 1. order the PCB

1. go to [JLCPCB](https://jlcpcb.com)
2. upload [`Gerber.zip`](./Gerber.zip)
3. settings: 2 layer, FR-4, 1.6mm, HASL (or ENIG if your feeling fancy)
4. order the parts seperately with [`Nexus-BOM.csv`](./Nexus-BOM.csv) as your shopping list - digikey, lcsc, aliexpress all work fine

### 2. print the case

1. open [`cad/`](./cad) - print the `.stl` as is, or crack open the `.f3d` in fusion if you wanna change dimensions
2. 0.2mm layer height, ~20% infill is plenty, its just sitting on a desk not getting thrown around
3. test fit the plate BEFORE you solder anything, learned that one the hard way

### 3. assemble

1. solder the nice!nano v2 diodes resistors and other supprt parts per the [`pcb/`](./pcb) schematic
2. solder in the hot swap sockets, then just press the switches in, no soldering needed there
3. wire the oled, encoder and rgb chain per the pin notes in [`journal.md`](./journal.md)
4. seat the finished pcb intothe case

### 4. flash it

1. follow the zmk build steps in [`firmware/`](./firmware) (shield config + keymap)
2. double tap reset on the nice!nano to drop into UF2 bootloader mode
3. drag the compiled `.uf2` onto the drive that shows up
4. pair over bluetooth, or just plg it in over usb-c if you want wired

### 5. done

flip it over, look at the rgb for a bit, start binding macros. if somethings broken check [`journal.md`](./journal.md) first, saves time vs trying to figure it out from scratch again.

---

## BOM

ful parts list + links in [`Nexus-BOM.csv`](./Nexus-BOM.csv)

---

## Credits

- [ZMK Firmware](https://zmk.dev/)
- [nice!nano](https://nicekeyboards.com/nice-nano/)
- [nice!nano docs](https://nicekeyboards.com/docs/nice-nano/) - pinout + hardware ref, used this constantly

Built by **Hashir**

---

## License

MIT, see [LICENSE](./LICENSE)
