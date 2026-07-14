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
├── LICENSE
├── README.md
└── journal.md   # Build log: component research, decisions, reasoning
```

As the project progresses, this will likely grow to include:
```
├── pcb/         # KiCad schematic + PCB files
├── firmware/    # ZMK shield config, keymap, overlay
├── cad/         # Case design files
└── BOM.csv      # Bill of materials
```

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

## Credits

- [ZMK Firmware](https://zmk.dev/) — open-source keyboard firmware
- [nice!nano](https://nicekeyboards.com/nice-nano/) — nRF52840 BLE module
- [nice!nano documentation](https://nicekeyboards.com/docs/nice-nano/) — pinout and hardware reference

Built by **Hashir**.

---

## License

Released under the [MIT License](./LICENSE).
