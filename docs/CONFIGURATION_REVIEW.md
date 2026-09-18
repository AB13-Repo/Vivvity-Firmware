# Configuration Review

The following items are imported from the supplied firmware snapshot and were
not functionally changed during repository preparation.

## Homing

- `X_HOME_DIR` is `1`: X homes toward MAX.
- `Y_HOME_DIR` is `-1`: Y homes toward MIN.
- `Z_HOME_DIR` is `1`: Z homes toward MAX.

## Z2 Driver

`Z2_DRIVER_TYPE` remains disabled:

```cpp
//#define Z2_DRIVER_TYPE A4988
```

## E1 Driver

The firmware sets:

```cpp
#define EXTRUDERS 2
```

while `E1_DRIVER_TYPE` remains disabled:

```cpp
//#define E1_DRIVER_TYPE A4988
```

This should be reviewed before a formal `v1.0.0` release.

## PSU_ACTIVE_STATE

`PSU_ACTIVE_STATE` appears twice in `Marlin/Configuration.h`:

- Line 379: `#define PSU_ACTIVE_STATE true`
- Line 386: `#define PSU_ACTIVE_STATE LOW`

The local PlatformIO build treats this as a compiler warning, not a compiler
error. Because the second definition appears later in preprocessing order, the
effective value after redefinition is `LOW`.

## HOMING_BUMP_MM

`HOMING_BUMP_MM` appears in both configuration files:

- `Marlin/Configuration.h`: `{ 10, 7, 6 }`
- `Marlin/Configuration_adv.h`: `{ 5, 5, 2 }`

The local PlatformIO build treats this as a compiler warning, not a compiler
error.

## Firmware Author Metadata

`STRING_CONFIG_H_AUTHOR` remains:

```cpp
#define STRING_CONFIG_H_AUTHOR "(none, default config)"
```

This should be cleaned up only after the project owner chooses the desired
author string.
