# Jump execution pipeline

The physical ALPINE experiment links the planner outputs to the winches, pneumatic leg and onboard attitude controller.

![Pre-jump, jump and landing](../0_Images/Andrea_Dalla_Villa_2026/fig3_9_jump_sequence.png)

## Runtime sequence

```text
Bring-up -> Homing -> Pre-jump positioning -> Jump -> Landing / post-jump hold
```

Pitch and yaw regulation remain active through the complete sequence.

After landing, the current rope coordinates are stored and the winches hold the newly reached suspended configuration. The tested system does **not** automatically return to the original take-off configuration.

## Planner interface

For a jump, the high-level planner provides:
- desired pneumatic-leg force \(f_{leg}\);
- thrust duration \(T_{th}\);
- desired left rope-force profile;
- desired right rope-force profile.

The desired pneumatic impulse is:

\[
J_{des}=f_{leg}T_{th}.
\]

This is converted to an inlet-valve command using the experimentally identified pneumatic map.

The attitude controller follows a separate onboard IMU-feedback path and is not replaced by the planner during the manoeuvre.

## Transition to jump force control

Before the brakes are released and the winches enter the jump force/torque-control phase, a finite holding command supports the suspended body and keeps the ropes tensioned.

Once the jump mode is established:
- the pneumatic leg is actuated;
- both winches follow the jump rope-force references;
- the attitude controller continues to correct pitch and yaw.

Smooth changes in rope-force commands reduce abrupt motor-torque steps during the pneumatic push.

## End of jump

At the end of the timed sequence:
- pneumatic actuation ends / vents;
- the current rope coordinates are retained;
- the winches hold the reached suspended state.

Abort and stop commands provide separate safe behaviours.

## What was validated

The integrated experiment demonstrated simultaneous operation of:
- attitude regulation;
- winch control;
- pneumatic actuation;
- telemetry;
- body-pose reconstruction.

The jump was **operator triggered**. Automatic touchdown detection and planner-driven consecutive physical jumps were not validated.
