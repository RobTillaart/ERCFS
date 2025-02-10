
[![Arduino CI](https://github.com/RobTillaart/ERCFS/workflows/Arduino%20CI/badge.svg)](https://github.com/marketplace/actions/arduino_ci)
[![Arduino-lint](https://github.com/RobTillaart/ERCFS/actions/workflows/arduino-lint.yml/badge.svg)](https://github.com/RobTillaart/ERCFS/actions/workflows/arduino-lint.yml)
[![JSON check](https://github.com/RobTillaart/ERCFS/actions/workflows/jsoncheck.yml/badge.svg)](https://github.com/RobTillaart/ERCFS/actions/workflows/jsoncheck.yml)
[![GitHub issues](https://img.shields.io/github/issues/RobTillaart/ERCFS.svg)](https://github.com/RobTillaart/ERCFS/issues)

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/RobTillaart/ERCFS/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/RobTillaart/ERCFS.svg?maxAge=3600)](https://github.com/RobTillaart/ERCFS/releases)
[![PlatformIO Registry](https://badges.registry.platformio.org/packages/robtillaart/library/ERCFS.svg)](https://registry.platformio.org/libraries/robtillaart/ERCFS)


# ERCFS

Arduino library for SPI based ERCFS rotary encoder.


### Description

**Experimental**

**Warning:** This library is not tested with hardware yet. 
So use with care, feedback welcome.

ECRFS is a library for the **ERCF 1 05SPI 360 Z** rotation encoder.
This devices decodes 360.0° in 16384 steps which implies an accuracy
of about 0.022°.
The angle is calculated every 350 μs, so 2850 times per second.

As the device can handle up to 800 rpm = 75 milliseconds per rotation.
To have a fair indication of rpm and direction one has to sample 
4 times so roughly once every 20 ms.


Feedback as always, is welcome. Please open an issue.


### Related

- https://github.com/RobTillaart/Angle
- https://github.com/RobTillaart/AngleConvertor
- https://github.com/RobTillaart/AverageAngle
- https://github.com/RobTillaart/runningAngle
- https://github.com/RobTillaart/AS5600 magnetic rotation meter.
- https://github.com/RobTillaart/ERCFS this library
- https://p3america.com/ercf-1-05spi-360-z/ home of datasheet.


### Please report your experiences.

If you have a ERCFS device, please let me know your experiences
with the sensor and this (or other) library.


## Interface

```cpp
#include "ERCFS.h"
```

### Constructor

- **ERCFS(uint8_t select, __SPI_CLASS__ \* mySPI = &SPI)** HARDWARE SPI
- **ERCFS(uint8_t select, uint8_t dataIn, uint8_t dataOut, uint8_t clock)** SOFTWARE SPI
- **bool begin()** initializes the communication.

### Read

- **uint16_t getRawValue()** returns a value from 0..16383
- **float getAngle()** returns an angle from 0..360.0°
- **void setOffset(float offset = 0)** set an offset for the angle.
- **float getOffset()** returns the current offset.
- **uint32_t lastRead()** timestamp in milliseconds since start.

### Debugging

- **bool usesHWSPI()**


## Future

#### Must

- improve documentation
- test with hardware

#### Should

- add examples

#### Could


#### Wont


## Support

If you appreciate my libraries, you can support the development and maintenance.
Improve the quality of the libraries by providing issues and Pull Requests, or
donate through PayPal or GitHub sponsors.

Thank you,

