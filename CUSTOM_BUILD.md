# WLED House Layout Custom Build

This repository is a modified build of WLED 16.0.0 for customer lighting
controllers. It keeps the normal WLED user interface and adds a native
Layout tool for mapping architectural lights on top of a house photo.

Original project: https://github.com/wled/WLED

## Modification Notice

This build has been modified from upstream WLED.

- Base project: WLED 16.0.0
- License: EUPL v1.2 or later, matching WLED
- Modified by: PermaGlow Lighting
- Modification date: 2026-05-31
- Source repository: https://github.com/Thatguy-didit/wled-house-layout

## Added Layout Features

- Adds a native WLED UI tab named Layout.
- Allows uploading a house photo.
- Allows placing individual LEDs as Single light items.
- Allows placing evenly spaced Light string runs.
- Allows selecting whole strings, or individual LEDs with Ctrl/Cmd.
- Allows creating and deleting mapper-defined architectural segments.
- Allows renumbering and reversing string direction.
- Shows live WLED colors and effects on mapped lights.
- Tracks mapped pixel counts per WLED output.
- Keeps existing WLED controls available.

## Changed Source Areas

- `wled00/data/index.htm`
  - Adds the Layout tab and toolbar button.
  - Adds Layout controls and panels.
- `wled00/data/index.css`
  - Adds native Layout UI styling.
  - Adjusts tab sizing for the fifth bottom tab.
- `wled00/data/index.js`
  - Adds Layout tool behavior.
  - Hooks Layout lights into WLED live color data.
  - Updates tab navigation for the Layout tab.
- `wled00/data/housemap.htm`
  - Standalone fallback page for the Layout tool.
- `tools/cdata.js`
  - Packages `housemap.htm` into `wled00/html_housemap.h`.
- `wled00/wled_server.cpp`
  - Serves `/housemap.htm`.

## Distributed Firmware

The current ESP32 Ethernet build output is generated at:

`build_output/release/WLED_16.0.0_ESP32_Ethernet.bin`

Build outputs are ignored by Git. Rebuild from source for release artifacts.
