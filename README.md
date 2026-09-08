# PDISKO7 Firmware OTA

## OTA update (normal)

Download latest firmware: [pdisko7.bin](pdisko7.bin)

The device updates itself over the air and picks the correct partition slot; just use the built-in OTA update in the web interface. Do NOT flash `pdisko7.bin` manually at offset 0 - it is app-only and will not boot without a bootloader/partition table.

## Manual flash (full image)

If you want to flash the device yourself with a serial flasher, use the merged full-flash image:

Download: [pdisko7.merged.bin](pdisko7.merged.bin)

- Use a tool such as https://esptool.spacehuhn.com/ ("Fully erase" then flash)
- Offset: `0x0000`
- Size: 16MB (full flash), includes bootloader + partition table + app

**Warning:** this image contains an empty FAT filesystem. Flashing it erases your configuration, background images, and wallhaven cache (device will run with defaults).