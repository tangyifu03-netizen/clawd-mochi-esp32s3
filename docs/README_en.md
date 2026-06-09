# Clawd Mochi for ESP32-S3

## Features

- ESP32-S3 + ST7789 240x240 display support
- expressive animated face states
- WiFi AP fallback for easy setup
- Claude Code serial protocol support
- Claude Code HTTP hook support
- local web endpoints for control and diagnostics

## Hardware

Configured display wiring:

| Signal | GPIO |
| --- | --- |
| MOSI / SDA | 10 |
| SCK / SCL | 9 |
| DC | 8 |
| CS | 14 |
| RST | 18 |
| BL | 13 |

Display target:

- ST7789
- 1.54 inch
- 240x240 resolution

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

After a successful WiFi connection, the device leaves the setup screen and returns to the idle face.

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
- `waiting`: permission / request face
- `done`: completion animation, then return to idle

## Notes

- `clawd_mochi_esp32s3.ino` should be treated as the primary entry sketch.
- `clawd_mochi_esp32s3_wifi_idle_20260609.ino` is kept as a dated snapshot for archival clarity.
