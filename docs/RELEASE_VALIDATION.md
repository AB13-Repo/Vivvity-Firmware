# Release Validation

Validation date:
2026-09-18

Repository:
https://github.com/AB13-Repo/Vivvity-Firmware

Baseline:
Marlin 2.0.9.7 at 743d3100fa7b7cb00d2456652e2604f0c63c16f3

## Local Build

Command:

```bash
python -m platformio run -e mega2560
```

Observed environment:

- Python: 3.12.10
- PlatformIO Core: 6.1.19
- PlatformIO platform: atmelavr 3.4.0
- Framework: Arduino
- Board: megaatmega2560

Observed result:

- Status: PASS
- RAM: 2895 bytes / 8192 bytes, 35.3%
- Flash: 73890 bytes / 253952 bytes, 29.1%

Observed warnings:

- `PSU_ACTIVE_STATE` is redefined in `Marlin/Configuration.h`.
- `HOMING_BUMP_MM` is redefined between `Marlin/Configuration.h` and `Marlin/Configuration_adv.h`.
- Marlin warns that the configuration provides no method to acquire user feedback.
- PlatformIO reported that Core 6.1.19 is obsolete and that 6.2.0 is available.

## Secret Scan

Secret scan status is recorded during final pre-push validation.
