# Clawd Mochi for ESP32-S3

Firmware for an ESP32-S3 desktop status companion with a 1.54 inch ST7789 240x240 display.

This project is tailored for a compact "Clawd Mochi" style device that can:

- show animated idle / busy / waiting / done faces
- receive Claude Code status updates over USB serial
- receive Claude Code status updates over LAN HTTP
- provide a Chinese WiFi setup page for standalone use
- return to the idle face automatically after WiFi connects

## Features

- ESP32-S3 + ST7789 240x240 display support
- WiFi AP fallback for easy network setup
- Claude Code serial protocol support
- Claude Code HTTP hook support
- local web endpoints for state control and diagnostics
- display-first UX with expressive status faces instead of text-only feedback

## Hardware

This firmware is configured for the following display wiring:

| Signal | GPIO |
| --- | --- |
| MOSI / SDA | 10 |
| SCK / SCL | 9 |
| DC | 8 |
| CS | 14 |
| RST | 18 |
| BL | 13 |

Target display:

- ST7789
- 1.54 inch
- 240x240 resolution

## Project Files

- `clawd_mochi_esp32s3.ino`: primary sketch file
- `clawd_mochi_esp32s3_wifi_idle_20260609.ino`: dated snapshot of the same firmware version
- [docs/README_zh-CN.md](./docs/README_zh-CN.md): Chinese notes and quick reference

## Build and Upload

Recommended Arduino FQBN:

```text
esp32:esp32:esp32s3:CDCOnBoot=cdc,UploadSpeed=921600,FlashSize=16M,PSRAM=opi
```

## WiFi Setup

If saved WiFi is missing or connection fails, the device starts a setup hotspot:

- SSID: `ClaWD-Mochi`
- Password: `clawd1234`
- Setup page: `http://192.168.4.1/wifi`

Once WiFi connects successfully, the device leaves the setup screen and returns directly to the idle face.

## Claude Code Integration

Supported serial commands:

- `CC:busy`
- `CC:waiting`
- `CC:idle`
- `CC:done`
- `CC:ip`

Supported HTTP endpoints:

- `/cc?state=busy|waiting|idle|done`
- `/state`
- `/wifi`

## Status Behavior

- `idle`: calm face with subtle blinking
- `busy`: focused animation
- `waiting`: request / permission face
- `done`: completion animation, then return to idle

## Notes

- This repository version was prepared on 2026-06-09 as a cleaned project snapshot.
- The older sibling local folder `clawd_mochi_esp32s3` was intentionally kept unchanged.

## License

MIT License. See [LICENSE](./LICENSE).
