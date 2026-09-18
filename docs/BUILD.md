# Build

Use PlatformIO from the repository root.

Primary build command:

```bash
pio run -e mega2560
```

Upload command:

```bash
pio run -e mega2560 -t upload
```

No COM port is configured in this repository. PlatformIO will auto-detect an
upload port or use one supplied by the operator.

The AVR PlatformIO environment is defined in `ini/avr.ini` with:

- Platform: atmelavr@~3.4
- Board: megaatmega2560
- Framework: Arduino
