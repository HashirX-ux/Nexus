# Nexus

[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](./LICENSE)
[![Status](https://img.shields.io/badge/status-in%20progress-orange?style=flat-square)]()
[![MCU](https://img.shields.io/badge/MCU-nice!nano%20V2-black?style=flat-square)]()
[![Firmware](https://img.shields.io/badge/firmware-ZMK-00599C?style=flat-square)]()
[![Wireless](https://img.shields.io/badge/wireless-BLE-blueviolet?style=flat-square)]()

> A wireless 3x4 mechanical macropad built to speed up your workflow. Hot-swap switches, per-key RGB, an OLED status screen, and a rotary encoder for macro control — wired or wireless.

---

## What is it?

Nexus is a custom 3x4 (12-key) macropad designed for productivity, shortcuts, and macros. It's built around a nice!nano v2 for wireless Bluetooth LE connectivity, with USB-C wired support as a fallback. It features 12 hot-swap key sockets under a per-key RGB array, plus a tactile EC11 rotary encoder and an OLED display for at-a-glance macro and connection status.

> **Note:** The original project tagline mentions QMK, but based on the build log the firmware direction is ZMK (needed for the nice!nano's BLE wireless support — QMK's BLE support doesn't target this board). Worth updating that tagline once you settle on a final direction.

## Why build it?

A dedicated macropad means shortcuts, macros, and repetitive commands live on their own set of keys — no reaching for a full keyboard's modifier combos. Building it from scratch means the layout, lighting, and firmware are all shaped around your own workflow.

---

## Status

This project is in the **research and design phase**. Component selection is done; PCB schematic and routing are still in progress. See [`journal.md`](./journal.md) for the full build log, including component research and reasoning for each part choice.

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
| Display | OLED — battery % and connected device status |
| Firmware | ZMK |
| USB | USB-C, USB 2.0 (480 Mbps, 5V/500mA) |

---

## Repository Structure

```
Nexus/
├── cad/          # Fusion 360 case files (.f3d / .step)
├── pcb/          # KiCad source: .kicad_pro, .kicad_sch, .kicad_pcb
├── firmware/     # ZMK shield + keymap
├── Gerber.zip    # Manufacturing files for JLCPCB
├── Nexus-BOM.csv # Bill of materials (parts + links)
├── journal.md    # Full build log / component research
└── README.md
```

Organized per Hack Club's [Hardware Codex shipping guide](https://codex.hackclub.com/shipping/101/) — source files and manufacturing files are kept separate so the project's easy to replicate.

> Want to inspect the PCB without opening KiCad? View it directly in the browser via KiCanvas:
> [![View PCB on KiCanvas](https://hack.club/pcb-badge)](https://kicanvas.org/?github=https://github.com/HashirX-ux/Nexus/tree/main/pcb)

---

## Build Log

The full day-by-day research process — component tradeoffs, datasheets referenced, and lessons learned along the way — lives in [`journal.md`](./journal.md). It's worth a read if you're building something similar and want the reasoning behind each part choice, not just the final BOM.

---

## Roadmap

1. Finalize schematic (matrix wiring, RGB data line, OLED I2C, encoder pins, reset button).
2. Route and order the PCB.
3. Build and test ZMK firmware against the real pin assignments.
4. Design and print/order the case.
5. Assemble, flash, and pair.

---

## How to Build

### 1. Order the PCB

1. Go to [JLCPCB](https://jlcpcb.com)
2. Upload [`Gerber.zip`](./Gerber.zip)
3. Settings: 2-layer, FR-4, 1.6mm, HASL or ENIG
4. Order your parts separately using [`Nexus-BOM.csv`](./Nexus-BOM.csv) as your shopping list (DigiKey / LCSC / AliExpress all work)

### 2. Print the case

1. Open [`cad/`](./cad) — either print the `.stl` directly, or open the `.f3d` in Fusion 360 if you want to tweak dimensions first
2. Print settings: 0.2mm layer height, ~20% infill is plenty for a desk macropad
3. Test-fit the plate before soldering anything — easier to reprint now than after

### 3. Assemble

1. Solder the nice!nano v2, diodes, resistors, and support components per the [`pcb/`](./pcb) schematic
2. Solder in the hot-swap sockets, then press-fit your switches — no soldering needed for those
3. Wire up the OLED, rotary encoder, and RGB chain per the pin assignments in [`journal.md`](./journal.md)
4. Seat the assembled PCB into the printed case

### 4. Flash the firmware

1. Follow the ZMK build instructions in [`firmware/`](./firmware) (shield config + keymap)
2. Double-tap the reset button to drop the nice!nano into UF2 bootloader mode
3. Drag and drop the compiled `.uf2` firmware file onto the drive that appears
4. Pair over Bluetooth, or plug in via USB-C for wired mode

### 5. You're done

Flip it over, admire the per-key RGB, and start binding macros. If something's off, [`journal.md`](./journal.md) has the full reasoning behind every part choice — it's usually faster to check there than to re-derive it from scratch.

---

## BOM

See [`Nexus-BOM.csv`](./Nexus-BOM.csv) for full component list with links.

---

## Credits

- [ZMK Firmware](https://zmk.dev/) — open-source keyboard firmware
- [nice!nano](https://nicekeyboards.com/nice-nano/) — nRF52840 BLE module
- [nice!nano documentation](https://nicekeyboards.com/docs/nice-nano/) — pinout and hardware reference

Built by **Hashir**.

---

## License

Released under the [MIT License](./LICENSE).
