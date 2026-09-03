# Experimental validation

The 2026 campaign progressed from actuator characterisation to subsystem tests and finally to an integrated physical jump.

The results are intentionally reported as **functional validation** unless an external quantitative reference was available.

## Validation map

| Subsystem | Validation status |
|---|---|
| six-EDF installation and mapping | verified on the physical robot |
| EDF thrust-command relation | manufacturer-derived map; six operating points bench confirmed |
| pitch correction | functionally verified |
| yaw correction | functionally verified |
| yaw pair switching | verified at 0.20, 0.50, 1.00 and 2.00 Hz command switching |
| EDF safety behaviour | verified |
| pneumatic inlet-angle response | characterised on 5.2 kg prototype at approximately 3.6 bar |
| inverse impulse-to-valve map | checked on the same 5.2 kg calibration configuration |
| left/right rope-position control | verified with separate +0.30 m step tests |
| body-pose reconstruction / RViz | qualitative consistency check |
| complete physical jump sequence | integrated functional validation |
| absolute trajectory accuracy | not measured |
| direct rope tension | not measured |
| automatic landing detection | not validated |
| planner-driven consecutive physical jumps | not validated |

## Result pages

- [[EDF and attitude tests]]
- [[Pneumatic actuator tests]]
- [[Winch and odometry tests]]
- [[Integrated jump test]]

## Current limitations

Quantitative attitude and pose validation still requires:
- a synchronised external pose reference;
- repeated controlled trials.

Rope tension should be measured directly with load cells before the motor-torque-derived force estimate is treated quantitatively.

The installed aerodynamic force and pitch/yaw coupling have not yet been measured directly on the assembled robot.
## Accompanying video

Physical attitude-control, odometry and integrated-jump material is available in the [ALPINE accompanying video](https://youtu.be/uGnkgwyiz4E?si=PzA2LDuUBlqPTcRI).
