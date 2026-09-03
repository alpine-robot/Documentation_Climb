# Firmware overview

The physical ALPINE platform uses distributed embedded control rather than placing every fast loop on the host computer.

## Body ESP32-S3

The body controller:
- reads the two Movella IMUs;
- computes body pitch and yaw from the body-mounted IMU quaternion;
- runs pitch/yaw attitude feedback at 100 Hz;
- generates six ESC command references;
- controls the pneumatic servos;
- parses host commands;
- publishes body telemetry.

The current host-body connection is serial. ESP-NOW was used in an earlier rapid-prototyping stage.

## Winch controllers

Each winch subsystem interfaces with:
- the ODrive Pro;
- the winch motor;
- the brake;
- the synchronous rope-measurement encoder.

The rope-position controller runs locally at 50 Hz and uses encoder feedback updated at 200 Hz.

## Main runtime rule

Each physical actuator must have one active command owner.

The high-level jump sequence therefore changes winch control mode in a controlled way instead of allowing the position controller and jump torque/force command to compete.

The body attitude controller remains active independently through the manoeuvre.

## ESC interface

Each EDF has an independent ESC channel.

- servo-style PWM frame: 50 Hz;
- 1000 µs: stop/minimum command;
- controller update: 100 Hz;
- external interface: requested EDF thrust in newtons;
- internal interface: thrust-to-command map followed by PWM generation.

The thrust-command relation is feed-forward: no EDF thrust sensor closes the loop.

## Safety

The implemented control chain includes:
- ESC arming at minimum pulse;
- EDF command saturation;
- controller active floors and command slew limits;
- attitude safety cut-off;
- abort/stop handling in the integrated sequence.

For the tested attitude-control parameters see [[Attitude_Control]].
