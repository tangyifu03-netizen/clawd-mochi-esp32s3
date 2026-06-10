# Clawd Mochi for ESP32-S3

Firmware for an ESP32-S3 desktop status companion with a 1.54 inch ST7789 240x240 display.

[English Documentation](./docs/README_en.md) | [中文说明](./docs/README_zh-CN.md)

## Overview

This project is built for a compact Clawd Mochi style device that can:

- display animated idle, busy, waiting, and done faces
- receive Claude Code status updates over USB serial
- receive Claude Code status updates over LAN HTTP
- provide a Chinese WiFi setup page for standalone use
- return to the idle face automatically after WiFi connects

## Repository Layout

- `firmware/clawd_mochi_esp32s3/clawd_mochi_esp32s3.ino`: primary Arduino sketch
- `archive/clawd_mochi_esp32s3_v0.1.0.ino`: archived v0.1.0 firmware snapshot
- [docs/README_en.md](./docs/README_en.md): full English documentation
- [docs/README_zh-CN.md](./docs/README_zh-CN.md): full Chinese documentation
- [CHANGELOG.md](./CHANGELOG.md): project history

## Current Version

`v0.2.0`

## License

MIT License. See [LICENSE](./LICENSE).
