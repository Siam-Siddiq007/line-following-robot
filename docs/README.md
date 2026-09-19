# Engineering Documentation Index

Detailed mathematical derivations and system architecture documentation:

1. **[Control System & Adaptive Speed](./control-system.md):** Mathematical derivation of the Proportional-Derivative (PD) control loop, derivative filter formulation, and dynamic speed scaling logic.
2. **[16-Sensor Array Geometry](./sensor-array.md):** Spatial weighting scheme, 74HC4051 analog multiplexing timeline, and multi-sample noise floor mitigation.

---

## Core Engineering Decisions

* **ADC1 Pin Isolation:** All analog sensor signals are routed exclusively to ESP32 ADC1 pins (`GPIO 34`, `GPIO 35`) to eliminate ADC2 conflict locks caused by Wi-Fi/Bluetooth drivers.
* **Derivative Anti-Spike Filter:** Dynamic sampling reduces single-cycle noise spikes from turning into high derivative braking output on sharp bends.
