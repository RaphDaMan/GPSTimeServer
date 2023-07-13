# Stratum-1 Time Server Built From Scratch - GNSSTimeServer

<p align="center"><img src="https://github.com/Montecri/GPSTimeServer/assets/38574378/d716c6b1-41b5-4bbf-84f4-9e0a0178015a"></p> 

<p align="center"><img src="https://user-images.githubusercontent.com/38574378/117382664-69117f00-aeb5-11eb-818f-4dcee22dbfc9.gif"></p>

[![Watch the video](https://i.ytimg.com/vi/bdvNMfCw1Pw/hqdefault.jpg)](https://www.youtube.com/watch?v=bdvNMfCw1Pw)

WiFi enabled, GPS fed NTP/RDATE server based on NodeMCU Amica and Arduino framework

<b>Functionalities:</b>

- Internal RTC synched from GNSS (Global Navigation Satellite System) satellites constellation (currently GPS and BeiDou; backed by CR2032 battery)
- Dual voltage powered
- Backup battery for the whole unit (18650)
- NTP and RDATE (RFC868) protocols supported
- Wifi functionality as a client or access point
- Syslog logging
- Configuration webpage for WiFi and Syslog, saving to persistent storage (LittleFS)
- Informative display with a timestamp, satellites in view, accuracy, wifi server, IP address
- Dual function button, short press switch information on display, long press disables WiFi
- Status at a glance, with dedicated 5mm LEDs for GPS lock, PPS signal, and WiFi status, as well as visible internal leds for charging and GPS module statuses
  - Yellow led will be on or off to indicate respective WiFi status
  - Green led will blink/pulsate at different rates to indicate a lock is being acquired and stay steady green when locked
  - Red led will blink once a second once lock is acquired, in sync with the PPS signal

<b>Parts list:</b>

- Amica NodeMCU (ESP8266 / ESP-12)
- DS3231 RTC
- Neo-6m V2 or ATGM336H GPS
- 1.3" SH1106 OLED Display
- Hi-Link 5V/3W
- Mini-360 DC-DC Buck converter
- TP4056 Module
- 18650 battery holder
- Red, Green and Yellow LEDs
- Resistors (150, 100 and 150 Ohms respectivelly for above leds)
- Switch key and momentary push button
- 0.5A/230v fuse
- 10D561K varistor

<b>Check also the Dual Display PIR Enabled branch option:</b>
https://github.com/Montecri/GPSTimeServer/tree/Dual-Display

---
<p align="center"><img src="https://user-images.githubusercontent.com/38574378/132773469-08fb7b59-2f9d-4641-9665-c8d50d3904bc.png"><b>   ATTENTION   </b><img src="https://user-images.githubusercontent.com/38574378/132773469-08fb7b59-2f9d-4641-9665-c8d50d3904bc.png"></p> 

Several DS3231 modules being sold today contain a hazardous design flaw in which it supplies a voltage to the battery cradle regardless if it came with a rechargeable battery or not. If it came with a CR2032 battery (non-rechargeable) the consequence is that it will swell, explode, or worse. If it came with a LIR2032 battery (rechargeable), the module being fed with 5v will generate an unsafe charging voltage for that battery.

There are workarounds for that so you don't need to toss your module away, the most popular being removing a diode and/or resistor.

There's a long discussion on the thread below about root cause and possible fixes:

https://forum.arduino.cc/t/zs-042-ds3231-rtc-module/268862/33

---

Libraries:

-	paulstoffregen/Time@^1.6
-	makuna/RTC@^2.3.5
-	mikalhart/TinyGPSPlus@^1.0.3
-	olikraus/U8g2@^2.28.8
- arcao/Syslog@^2.0.0

Source code based on:

- http://w8bh.net/avr/clock2.pdf
- https://forum.arduino.cc/t/ntp-time-server/192816

Contributions from:

@mmarkin
@sjthespian

![sketch_bb-menor](https://user-images.githubusercontent.com/38574378/117375890-66f3f400-aea6-11eb-9389-1b9b0b01f88f.png)
![power supply - UPDATED_bb-menor](https://user-images.githubusercontent.com/38574378/231014475-e1dc9185-a66d-4c0c-b681-dbc1ae9cf767.png)


https://www.linkedin.com/pulse/iot-maker-tale-stratum-1-time-server-built-from-scratch-monteiro/
