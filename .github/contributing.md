# Contributing

This repository contains project-specific firmware derived from Marlin 2.0.9.7.
Issues and pull requests here are for this independent firmware repository, not
for the official MarlinFirmware organization.

Before proposing functional firmware changes:

- Compare against the upstream baseline with `git diff upstream-2.0.9.7..main`.
- Build with `pio run -e mega2560`.
- Document any change to motion, homing, endstop, thermal, power, fan, servo, or
  pin behavior.
- Preserve Marlin copyright headers and GPL licensing.

General Marlin issues should be directed to the official Marlin project.
