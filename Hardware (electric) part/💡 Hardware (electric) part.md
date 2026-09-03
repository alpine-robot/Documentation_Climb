## Abstract

This section documents the electrical architecture of the winches and the ALPINE body.

The current integrated body includes six independently controlled EDF branches, two 6S2P lithium-ion packs, an ESP32-S3 body controller, two Movella IMUs, pneumatic servos and the existing body electronics.

See the BOM in [[🧾 BOM climbing robots]] for component-level information.

---

## Winch system

![[Screenshot from 2025-08-26 16-11-01.png]]

The winch electronics include the local embedded controller, ODrive Pro, motor, brake actuation and encoder interface.

## ALPINE body

![[Screenshot from 2025-08-26 16-09-46.png]]

For the current propulsion and body-control architecture see [[Body propulsion electronics]].

## Communication

![[Screenshot from 2025-08-26 16-13-05.png]]

The 2026 experimental system uses a host-to-body serial connection for body commands and telemetry. ESP-NOW was used during earlier rapid prototyping. A robust wired CAN link is proposed as future work.
