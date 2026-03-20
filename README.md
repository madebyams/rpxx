# rpxx

A C++ driver library for the Raspberry Pi Pico (RP2040), providing hardware abstractions for common peripherals.

## Modules

| Module | Peripheral | Interface |
|--------|-----------|-----------|
| `HC-SR04` | Ultrasonic distance sensor | GPIO |
| `SSD1306` | 128x32 OLED display | I2C |
| `ST7789` | 240x320 TFT LCD display | SPI |

## Requirements

- CMake 3.30+
- ARM cross-compiler toolchain (`arm-none-eabi-g++`)
- C++17 support

The Pico SDK is fetched automatically during configuration.

## Building

Each module builds independently. The steps are the same for each:

```bash
cd <module>   # HC-SR04, SSD1306, or ST7789
mkdir build
cd build
cmake ..
cmake --build .
```

## Usage

### HC-SR04

```cpp
#include "HC-SR04.hh"

HC_SR04 sensor(trigger_pin, echo_pin);
sensor.init();

uint32_t distance_cm;
sensor.measure(&distance_cm);
```

### SSD1306

```cpp
#include "SSD1306.hh"

SSD1306 display;
display.init();
display.fill(0);
display.draw_string("Hello", 0, 0, Font_7x10, 1, 1);
display.update();
```

### ST7789

```cpp
#include "ST7789.hh"

ST7789 display;
display.init();
display.render(image_data);
```

## CI

Builds are run on GitLab CI using the `ghcr.io/anothersimplecoder/cmake:latest` Docker image. All three modules are built on each push.
