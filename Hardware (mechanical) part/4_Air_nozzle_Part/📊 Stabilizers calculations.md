# Stabilisation concepts - historical design study

This note records the early alternatives considered for body stabilisation.

## Cold-gas thrusters

A cold-gas reaction-control concept was initially considered using the onboard compressed-air system. The concept was not selected for the integrated prototype.

## Gyroscopic actuator

A reaction-wheel / gyroscopic solution was also considered but was not selected for the current robot.

## Selected solution: ducted propellers

The physical prototype uses **six independently driven, fixed-axis, unidirectional electric ducted fans (EDFs)**.

The selected architecture provides:
- direct pitch correction through the dedicated T5-T6 pair;
- yaw correction through complementary pairs among T1-T4;
- additional body-frame lateral force directions from the same four lateral EDFs;
- fast actuation without reconfiguring the supporting ropes.

See [[EDF attitude-control system]] for the final geometry and [[Attitude_Control]] for the implemented feedback controller.
