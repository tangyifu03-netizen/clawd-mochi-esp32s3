# Release Notes - v0.2.0

Clawd Mochi Pro animation update.

## Included

- Clawd on Desk inspired status model
- procedural small-screen face animations for idle, busy, waiting, done, and error states
- richer idle behavior with look, yawn, and doze moods
- richer working behavior with thinking, typing, and ultrathink moods
- `/state` now reports the current `mood`
- Arduino-compatible project layout under `firmware/clawd_mochi_esp32s3/`
- archived v0.1.0 firmware snapshot under `archive/`

## Note

This firmware does not embed the desktop app SVG assets. The animations are lightweight procedural drawings adapted for the ESP32-S3 and ST7789 display.
