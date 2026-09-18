# Safety

This firmware controls motors, heaters, fans, servos, and power-control I/O.
Review the configuration against the physical hardware before operation.

Minimum validation before machine use:

- Confirm X, Y, and Z homing directions.
- Confirm all endstop pins and active states.
- Confirm RAMPS MOSFET and fan wiring.
- Confirm heater outputs and thermistor assignments.
- Confirm PSU relay polarity and fail-safe behavior.
- Confirm emergency stop and power removal behavior.
- Confirm maximum travel limits before high-speed motion.
- Confirm thermal runaway protection behavior using safe test conditions.

This firmware is not documented as clinically approved. It is research
laboratory automation firmware and requires project-specific hardware review.
