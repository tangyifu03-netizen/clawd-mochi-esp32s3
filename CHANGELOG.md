# Changelog

All notable changes to this project will be documented in this file.

## v0.2.0 - 2026-06-10

- added Clawd on Desk inspired state model for the firmware animation layer
- added procedural small-screen faces for idle look, yawn, doze, thinking, typing, ultrathink, notification, happy, and error states
- added `error`, `typing`, `ultrathink`, `permission`, and `notify` aliases to the Claude state handler
- added current `mood` to the `/state` endpoint
- moved the primary sketch into `firmware/clawd_mochi_esp32s3/` for a cleaner Arduino-compatible project layout
- archived the previous v0.1.0 firmware snapshot under `archive/`

## v0.1.0 - 2026-06-09

- initial organized ESP32-S3 firmware release
- ST7789 1.54 inch 240x240 display support
- Claude Code USB serial integration
- Claude Code LAN HTTP integration
- Chinese WiFi setup page
- automatic return to idle face after successful WiFi connection
- repository cleanup with bilingual documentation and MIT license
