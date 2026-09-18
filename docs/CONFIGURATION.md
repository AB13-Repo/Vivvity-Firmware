# Configuration

This firmware is based on Marlin 2.0.9.7 and configured for PlatformIO
environment `mega2560`.

## Controller

- MCU: ATmega2560
- Board definition: BOARD_RAMPS_14_EEB
- Baud rate: 250000
- EEPROM settings: enabled

## Motion

- Workspace: X 419 mm, Y 270 mm, Z 248 mm
- Steps/mm: X 80, Y 80, Z 400, E 500
- Maximum feedrate: X 300, Y 300, Z 15, E 25
- Maximum acceleration: X 3000, Y 3000, Z 300, E 10000
- Z jerk: 1.0

## Homing

- X_HOME_DIR: 1, homes to MAX
- Y_HOME_DIR: -1, homes to MIN
- Z_HOME_DIR: 1, homes to MAX
- Homing feedrate: X 80 mm/s, Y 80 mm/s, Z 30 mm/s
- Homing bump distance in `Configuration.h`: `{ 10, 7, 6 }`
- Homing bump distance in `Configuration_adv.h`: `{ 5, 5, 2 }`

## Thermal

- TEMP_SENSOR_0: 1
- TEMP_SENSOR_1: 1
- TEMP_SENSOR_BED: 1
- HEATER_0_MAXTEMP: 113 C
- Extruder auto-fan threshold: 90 C

## Auxiliary I/O

- PSU control: enabled
- PSU pin: 57
- Servo count: 2
- SERVO0_PIN: 11
- E0 auto-fan pin: 9
- M42 direct pin control: enabled
- Pins debugging: enabled
