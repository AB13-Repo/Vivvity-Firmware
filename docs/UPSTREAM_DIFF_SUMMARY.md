# Upstream Diff Summary

Upstream version:
Marlin 2.0.9.7

Upstream commit SHA:
743d3100fa7b7cb00d2456652e2604f0c63c16f3

Local baseline tag:
upstream-2.0.9.7

## Modified Files

Compared with official Marlin 2.0.9.7, the supplied firmware snapshot modifies:

- `Marlin/Configuration.h`
- `Marlin/Configuration_adv.h`
- `Marlin/src/module/planner.cpp`
- `Marlin/src/pins/ramps/pins_RAMPS.h`

## Configuration Changes

Confirmed configuration changes include:

- Motherboard changed to `BOARD_RAMPS_14_EEB`.
- Extruder count changed to `2`.
- PSU control enabled with `PSU_PIN 57`.
- `TEMP_SENSOR_1` and `TEMP_SENSOR_BED` enabled as type `1`.
- `HEATER_0_MAXTEMP` changed to `113`.
- Cold extrusion prevention changed to `false` and minimum extrusion temperature to `0`.
- X/Y/Z endstop inversion set to `true`.
- X and Z homing changed to MAX; Y remains MIN.
- Workspace changed to X 419 mm, Y 270 mm, Z 248 mm.
- Z feedrate, acceleration, and jerk values changed.
- EEPROM settings enabled.
- Servo support enabled with two servos and `SERVO0_PIN 11`.
- Controller fan enabled on pin 8.
- E0 auto-fan pin changed to 9.
- Direct pin control and pins debugging enabled.

## Source-Code Changes

`Marlin/src/module/planner.cpp` contains a commented-out custom origin-shift
function. It is not compiled because it remains inside a block comment.

## Pin Changes

`Marlin/src/pins/ramps/pins_RAMPS.h` comments out the `FAN_PIN` assignment for
the `FET_ORDER_EEB` branch, changing the RAMPS fan-pin behavior relative to
upstream Marlin 2.0.9.7.

## Build Configuration Changes

No project-specific build environment file changes are present relative to
official Marlin 2.0.9.7. The upstream `mega2560` PlatformIO environment is used.
