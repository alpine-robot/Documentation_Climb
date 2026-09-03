# 2026 attitude-control and integration additions

This page lists the main hardware additions introduced for the integrated 2026 ALPINE body. It complements the legacy BOM spreadsheet; prices are intentionally left to the purchasing records.

| Component | Description | Quantity |
|---|---|---:|
| QX-Motor QF2611PRO 50 mm EDF | selected fixed-axis ducted propeller, 6S configuration | 6 |
| Electronic speed controller | one independent ESC per EDF | 6 |
| INR21700-45D cells | cells used to build two 6S2P propulsion packs | 24 |
| 6S2P propulsion battery pack | three EDF branches supplied by each pack | 2 |
| ESP32-S3 body controller | attitude control, ESC PWM, pneumatic servos, host interface and telemetry | 1 |
| Movella IMU | body attitude and rope-direction sensing | 2 |

## Notes

- The integrated body mass after the propulsion, battery, support and protection additions is approximately 10 kg.
- The selected EDF maximum catalogue operating point is 14.03 N static thrust per EDF.
- The ESC model and detailed purchased-part references should be taken from the project purchasing records rather than inferred from the thesis.
- Mechanical EDF supports, wiring, connectors and protection structures are part of the integrated system but are not itemised here because the final dissertation does not provide a complete purchase-level quantity/cost table.

See [[EDF attitude-control system]] and [[Body propulsion electronics]].
