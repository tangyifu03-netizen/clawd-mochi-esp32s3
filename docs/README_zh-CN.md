# Clawd Mochi ESP32-S3 固件说明

这个目录是整理后的 GitHub 发布版本。

## 功能

- 适配 ESP32-S3 + ST7789 1.54 寸 240x240 屏幕
- 支持 Claude Code 通过 USB 串口联动
- 支持 Claude Code 通过局域网 HTTP 联动
- 提供中文 WiFi 配网页
- 配网成功后自动回到待机表情

## 接线

- MOSI / SDA -> GPIO 10
- SCK / SCL -> GPIO 9
- DC -> GPIO 8
- CS -> GPIO 14
- RST -> GPIO 18
- BL -> GPIO 13

## 烧录参数

```text
esp32:esp32:esp32s3:CDCOnBoot=cdc,UploadSpeed=921600,FlashSize=16M,PSRAM=opi
```

## 配网

未连接成功时会开启热点：

- 热点名：`ClaWD-Mochi`
- 密码：`clawd1234`
- 页面：`http://192.168.4.1/wifi`

## 文件说明

- `clawd_mochi_esp32s3.ino`：主固件文件
- `clawd_mochi_esp32s3_wifi_idle_20260609.ino`：同版本日期快照
