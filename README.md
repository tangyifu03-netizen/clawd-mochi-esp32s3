# Clawd Mochi ESP32-S3 Firmware

ESP32-S3 firmware for a 1.54 inch ST7789 240x240 display board used as a Clawd Mochi status device.

This build supports:

- ESP32-S3 + ST7789 1.54 inch 240x240 display
- USB serial control from Claude Code
- LAN HTTP control from Claude Code hooks
- Chinese WiFi setup page at `http://192.168.4.1/wifi`
- Automatic return to idle face after WiFi connects

## Hardware

Display wiring used by this firmware:

- MOSI / SDA -> GPIO 10
- SCK / SCL -> GPIO 9
- DC -> GPIO 8
- CS -> GPIO 14
- RST -> GPIO 18
- BL -> GPIO 13

## Build / Upload

Arduino FQBN:

```text
esp32:esp32:esp32s3:CDCOnBoot=cdc,UploadSpeed=921600,FlashSize=16M,PSRAM=opi
```

Main sketch files in this folder:

- `clawd_mochi_esp32s3.ino`
- `clawd_mochi_esp32s3_wifi_idle_20260609.ino`

## WiFi Setup

When WiFi is not configured or connection fails:

- device AP: `ClaWD-Mochi`
- password: `clawd1234`
- setup page: `http://192.168.4.1/wifi`

After successful WiFi connection, the screen leaves setup info and returns directly to the idle face.

## Claude Code Integration

Supported state commands:

- serial: `CC:busy`, `CC:waiting`, `CC:idle`, `CC:done`, `CC:ip`
- HTTP: `/cc?state=busy|waiting|idle|done`
- state query: `/state`
- wifi page: `/wifi`

## Notes

- This folder is the organized GitHub upload version created on 2026-06-09.
- The older sibling folder `clawd_mochi_esp32s3` was kept unchanged.
