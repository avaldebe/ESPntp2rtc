# ESPntc2rtc

Update/setup an RTC module from a [NTP][] service using with ESP8266 module.

- Hardware
  - [WEMOS D1 mini][d1_mini]
  - 64x48 [OLED shield][oled_shield]
  - Optional
    - [proto][proto] + [base][base2] shields, or [large base][base3] shield
    - [battery shield][battery]
  - TBD
    - I2C bus connectors & pinout
    - enclosure
- Software
  - arduino framework
  - core/HAL ESP8266/ESP32 time library (see #4)
  - [RTClib library][RTClib]
  - strip down RTC library (see #2)
  - manage wifi keys (optional)
    - [JSON library][ArduinoJson] + SPIFFS
    - [WiFiManager library][WiFiManager]

## Get libs in PlatformIO
```bash
pio lib install RTClib
```

## Compile in PlatformIO CLI
```bash
# set wifi credentials
export WIFI_SSID=myWIFIssid WIFI_PASS=myWIFIpass

# compile & upload for d1_mini (esp8266)
pio run -e d1_mini
pio run -e d1_mini -t upload

# compile & upload for mhetesp32minikit (esp32)
pio run -e mhetesp32minikit
pio run -e mhetesp32minikit -t upload
```

[d1_mini]: https://wiki.wemos.cc/products:d1:d1_mini
[oled_shield]: https://wiki.wemos.cc/products:d1_mini_shields:oled_shield
[battery]: https://wiki.wemos.cc/products:d1_mini_shields:battery_shield
[proto]: https://wiki.wemos.cc/products:d1_mini_shields:protoboard_shield
[base2]: https://wiki.wemos.cc/products:d1_mini_shields:dual_base
[base3]: https://wiki.wemos.cc/products:d1_mini_shields:tripler_base

[RTClib]: https://github.com/adafruit/RTClib
[OLEDlib]: https://github.com/squix78/esp8266-oled-ssd1306
[WiFiManager]: https://github.com/tzapu/WiFiManager.git
[ArduinoJson]: https://github.com/bblanchon/ArduinoJson.git

[NTP]: https://en.wikipedia.org/wiki/Network_Time_Protocol
[epoch]: https://en.wikipedia.org/wiki/Unix_time
