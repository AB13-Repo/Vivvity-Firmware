# Vivvity - Marlin Firmware

Custom Marlin 2.0.9.7-based firmware configured for a research
laboratory automation platform.

Base firmware: Marlin 2.0.9.7

Target controller:
Arduino Mega 2560 + RAMPS 1.4

Build target:
PlatformIO mega2560

License:
GNU GPL, preserving the licensing and copyright notices of the upstream
Marlin project.

## Overview

This repository contains project-specific firmware derived from the Marlin
Firmware project. The firmware is configured for ATmega2560 / RAMPS 1.4
hardware used in a laboratory automation motion-control context.

The repository is independent from the official Marlin repository. Official
Marlin is tracked as an upstream source for audit and comparison only.

## Upstream Marlin

- Upstream project: MarlinFirmware/Marlin
- Upstream release: 2.0.9.7
- Upstream commit: 743d3100fa7b7cb00d2456652e2604f0c63c16f3
- Local baseline tag: upstream-2.0.9.7

Run this command to inspect project-specific changes:

```bash
git diff upstream-2.0.9.7..main
```

## Hardware Target

- MCU: ATmega2560
- Controller: Arduino Mega 2560
- Expansion board: RAMPS 1.4
- Marlin motherboard: BOARD_RAMPS_14_EEB
- Stepper driver family configured in firmware: A4988
- Serial baud rate: 250000

Only hardware confirmed in the firmware configuration is documented here.

## Firmware Architecture

The firmware keeps the Marlin 2.0.9.7 source layout. Project-specific changes
are concentrated in configuration, RAMPS pin behavior, and one commented
planner-origin experiment retained from the supplied firmware snapshot.

## Motion Configuration

Configured workspace:

- X: 419 mm
- Y: 270 mm
- Z: 248 mm

Configured steps per millimeter:

- X: 80
- Y: 80
- Z: 400
- E: 500

Configured maximum feedrate:

- X: 300 mm/s
- Y: 300 mm/s
- Z: 15 mm/s
- E: 25 mm/s

Configured maximum acceleration:

- X: 3000
- Y: 3000
- Z: 300
- E: 10000

## Homing and Endstops

Configured homing directions:

- X homes to MAX
- Y homes to MIN
- Z homes to MAX

The configuration also enables X/Y/Z max plugs and uses inverted endstop logic.
These values are imported from the supplied firmware and should be reviewed on
the physical machine before operation.

## Auxiliary I/O

- PSU control is enabled.
- PSU pin is configured as 57.
- Servo count is configured as 2.
- SERVO0_PIN is configured as 11.
- E0 auto-fan pin is configured as 9.
- Controller fan support is enabled with controller fan pin 8.
- Direct pin control and pins debugging are enabled.

## Thermal Control

- TEMP_SENSOR_0: 1
- TEMP_SENSOR_1: 1
- TEMP_SENSOR_BED: 1
- HEATER_0_MAXTEMP: 113 C
- E0 auto-fan threshold: 90 C

Thermal settings are project-specific and must be validated against the actual
sensors, heaters, and safety requirements of the hardware.

## Building the Firmware

Install PlatformIO, then run:

```bash
pio run -e mega2560
```

The repository is configured with:

```ini
default_envs = mega2560
```

## Flashing

Connect the Arduino Mega 2560 by USB, then run:

```bash
pio run -e mega2560 -t upload
```

No serial port is hard-coded in this repository.

## Repository Structure

- `Marlin/` - Marlin firmware source and project configuration
- `buildroot/` - Marlin build support files
- `config/` - Marlin configuration package reference
- `docs/` - project documentation and import audit records
- `ini/` - PlatformIO environment definitions
- `platformio.ini` - PlatformIO project entry point
- `UPSTREAM.md` - upstream attribution and baseline information

## Safety

This firmware controls motion, heaters, fans, and auxiliary I/O. Verify pin
assignments, endstop polarity, homing direction, thermal behavior, emergency
stop behavior, and power-control behavior on the actual hardware before routine
use. Do not operate unattended until the configuration has been reviewed and
validated.

## Citation

Citation metadata is provided in `CITATION.cff`.

## License

This repository is derived from Marlin Firmware and retains the GNU GPL license
and upstream copyright notices. See `LICENSE` for the full license text.
