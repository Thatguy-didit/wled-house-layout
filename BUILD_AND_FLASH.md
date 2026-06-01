# Build And Flash

These notes document the build used for the ESP32 Ethernet controllers in this
custom WLED House Layout build.

## Requirements

- Visual Studio Code with PlatformIO installed
- Node.js 20 or newer
- Python and PlatformIO CLI
- USB connection to the ESP32 controller

## Build Web UI

The WLED web UI source must be converted into generated firmware headers before
compiling.

```powershell
npm ci
npm run build -- --force
```

## Compile ESP32 Ethernet Firmware

```powershell
pio run -e esp32_eth
```

The compiled binary is copied to:

```text
build_output/release/WLED_16.0.0_ESP32_Ethernet.bin
```

## Flash A Connected Controller

For the controller used during development, the serial port was `COM5`.

```powershell
pio run -e esp32_eth -t upload --upload-port COM5
```

If the controller appears on a different port, replace `COM5`.

## Release Checklist

Before flashing customer controllers from a new version:

1. Update `CUSTOM_BUILD.md` if the feature list changed.
2. Update `CUSTOMER_SOURCE_NOTICE.md` with your public repo URL.
3. Commit all source changes.
4. Tag the source commit.
5. Build from the tagged commit.
6. Save or publish the matching `.bin`.
7. Give the customer the source notice.

