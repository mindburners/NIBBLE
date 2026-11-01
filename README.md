# Mindburner NIBBLE — Firmware

NIBBLE is an 8-voice chiptune MIDI synthesiser module (NES, Game Boy and C64 sounds) with chip drums, 1-bit speech, a wave editor and a song sequencer, built around the ESP32. This repo hosts the firmware and a one-click browser-based installer — no Arduino IDE required.

## Install or update firmware

👉 **[Open the installer](https://mindburners.github.io/NIBBLE/)**

1. Connect NIBBLE to your computer with a USB **data** cable
2. Open the link above in **Chrome**, **Edge**, or **Opera**
3. Click **Connect**, choose the correct serial port, then click **Install**

Updating keeps your saved patches, drawn waves, sequencer patterns and songs, MIDI channel, tuning and master level.

> ⚠️ Not supported in Safari or Firefox (no Web Serial support).

## Documentation

- [User manual (PDF)](NIBBLE_User_Manual.pdf)
- [Quick start guide (PDF)](NIBBLE_Quick_Start.pdf)

## What's in this repo

| File | Purpose |
|---|---|
| `index.html` | The installer page |
| `changelog.txt` | Version history, newest first. The page reads its version and What's New list from here |
| `manifest.json` | Backup installer manifest (the page builds its own from `changelog.txt`) |
| `bootloader.bin`, `partitions.bin`, `firmware.bin` | The compiled firmware |
| `logo.png` | Branding shown on the installer page |
| `*.pdf` | User manual and quick start guide |

## Releasing an update

1. In Arduino IDE: **Sketch → Export Compiled Binary**
2. Rename the three exported files to `bootloader.bin`, `partitions.bin`, `firmware.bin`
3. Drag them into this repo, overwriting the existing files
4. Add a new line at the **top** of `changelog.txt`, e.g. `0.9.8 - what changed`
5. Commit

The page reads its version and What's New list from `changelog.txt`, and builds the installer
from it too, so `index.html` and `manifest.json` never need editing.

New manuals: upload them with the same file names (`NIBBLE_User_Manual.pdf`, `NIBBLE_Quick_Start.pdf`)
and commit. All links stay the same.

## Hardware

- ESP32-WROOM-32E
- PCM5102A stereo I2S DAC
- ST7735 160×128 SPI colour TFT
- 4 buttons and rotary encoder, DIN MIDI in / thru

---
Mindburner — Alan G. Watkins
