# P-Disko 7 Firmware (OTA Releases)

Precompiled OTA firmware distribution repository for **P-Disko 7 (`pdisko7`)** — ESP32-S3 7-inch smart weather, energy, and ambient telemetry display.

## Overview
P-Disko 7 provides a high-contrast LVGL dashboard displaying local weather station telemetry, Nordpool spot electricity pricing, custom icon packs, and ambient Wallhaven backgrounds on a 7-inch 800×480 IPS touch screen.

## Hardware Target
- **MCU**: ESP32-S3 (16 MB Flash, 8 MB Octal PSRAM)
- **Display**: 7-inch 800×480 RGB TFT (LVGL hardware-accelerated double buffering in PSRAM)

## Flashing Instructions

### 1. Network OTA Update
Upload the `.bin` image via the device web portal or `curl`:
```bash
curl -F "update=@pdisko7.bin" http://<device-ip>/update
```

### 2. Serial Flashing (`esptool.py`)
```bash
esptool.py --chip esp32s3 --port /dev/ttyACM0 --baud 921600 write_flash 0x10000 pdisko7.bin
```

## License
Distributed under the [MIT License](./LICENSE). Copyright (c) 2026 OH2FXD.
