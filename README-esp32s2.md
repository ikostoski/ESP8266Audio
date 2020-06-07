# Early support for ESP32-S2

It is now possible to compile the library and examples for ESP32-S2 with Arduino IDE. This however requires manual installation of 'esp32s2' branch of 'arduino-esp32' in your 'hardware' directory. See following video for explanation of the process: https://www.youtube.com/watch?v=yiYyTQDRFZI, which works as of June 2020.

In addition, due to the development nature of the build, Arduino IDE might select wrong libraries to compile. This is not specific to ESP8266Audio and will likely be solved in time. So far for me, this happened with 'SD' and 'WiFi' libraries and you might need to be remove default ones from the 'libraries' directory in Arduino installation, and/or from 'libraries' in your Arduino sketches directory. 

This setup will use gcc-8.2 toolchain and development version of esp-idf (4.2-dev), which is still work in progress and may contain many incompatible changes. Be prepared for lots of compiler warnings. This had very limited testing and your mileage may vary. 

ESP32-S2 also has some limitations such as INTERNAL_DAC and INTERNAL_PDM modes of AudioOutputI2S will not work.

Take note of the pin assignements in your sketches. Many ESP32 pins do not exist on ESP32-S2 and vice-versa.
