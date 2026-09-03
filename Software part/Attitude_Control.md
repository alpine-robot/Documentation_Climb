# Attitude control

ALPINE uses onboard IMU feedback and six fixed-axis EDFs to regulate **pitch** and **body yaw**.

The objective is to bring the pneumatic leg back towards an orientation approximately aligned with the wall normal before landing.

## Attitude estimation

The body-mounted IMU provides a quaternion representing body orientation.

Using a ZYX convention:

\[
R = R_z(\phi)R_y(\theta)R_x(\psi)
\]

where:
- \(\phi\): yaw;
- \(\theta\): pitch;
- \(\psi\): roll.

Pitch and yaw references are captured from the current body orientation before regulation is enabled. They are fixed setpoints, not time-varying trajectories.

## Pitch controller

Pitch uses T5 and T6 as a dedicated complementary pair.

The implemented structure is:
- two-threshold hysteresis;
- PD behaviour in the tested configuration (\(K_i=0\));
- active minimum EDF command;
- saturation;
- command slew-rate limit;
- sign-based selection of T5 or T6.

Only one pitch EDF normally receives the active correction, so a small secondary yaw disturbance can be introduced by rotor reaction torque.

## Yaw controller

Yaw uses the four lateral EDFs.

The controller includes:
- wrapped yaw error;
- finite-difference yaw-rate estimate;
- first-order yaw-rate filtering;
- two-threshold hysteresis;
- PD feedback;
- active minimum command;
- saturation;
- command slew-rate limit;
- deterministic pair selection.

Command sign selects:
- positive yaw: **T1 + T3**;
- negative yaw: **T2 + T4**.

## Tested controller parameters

| Parameter | Pitch | Yaw |
|---|---:|---:|
| controller update | 100 Hz | 100 Hz |
| ESC PWM frame | 50 Hz | 50 Hz |
| \(K_p\) | 1.20 | 0.90 |
| \(K_i\) | 0 | - |
| \(K_d\) | 0.05 | 0.04 |
| inner hysteresis threshold | 2° | 3° |
| outer hysteresis threshold | 5° | 11° |
| active command floor \(d_{min}\) | 0.80 | 0.55 |
| maximum command \(d_{max}\) | 1.00 | 0.70 |
| maximum command derivative | 10 s⁻¹ | 8 s⁻¹ |
| command-equivalent minimum thrust / selected EDF | 9.61 N | 5.50 N |
| command-equivalent maximum thrust / selected EDF | 14.03 N | 7.35 N |

The thrust values above are **command-equivalent values obtained through the thrust-command map**, not direct real-time thrust measurements.

## Validation status

The physical experiments verified:
- correct T1-T6 mapping;
- correct thrust directions;
- correct CW/CCW convention;
- corrective pitch selection between T5 and T6;
- corrective yaw pair selection;
- hysteretic activation;
- slew-limited command behaviour;
- safety cut-off;
- continued operation during the integrated jump sequence.

The validation is functional. Quantitative closed-loop attitude dynamics still require repeated trials and a synchronised external pose reference.

See [[EDF and attitude tests]].
