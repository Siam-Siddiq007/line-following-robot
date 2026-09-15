# High-Speed Line Following Robot

An ESP32-based high-speed line following robot designed around differential drive, PID control, and look-ahead line sensing.

The goal of this project is to build a compact, lightweight and stable line follower while documenting the complete engineering process from component selection and mechanical design to embedded software, testing and optimization.

---

## Project Status

🟡 **In Development**

The robot is currently in the design and assembly stage.

### Current focus
- Mechanical chassis design
- Motor and wheel integration
- Sensor boom design
- Power system design
- ESP32 firmware
- PID control implementation

---

## Objectives

- Build a fast and stable line following robot
- Implement closed-loop PID control
- Use look-ahead sensing to anticipate upcoming curves
- Develop an adjustable sensor boom
- Optimize weight distribution and traction
- Develop the control software from scratch
- Document the complete engineering process

---

## System Architecture

```text
                    2S Li-ion Battery
                         7.4 V
                           │
                    Protection / BMS
                           │
              ┌────────────┴────────────┐
              │                         │
         Motor Power                 Logic Power
              │                         │
         6 V Buck                  LM2596 Buck
              │                         │
              ▼                         ▼
         TB6612FNG                    ESP32
          Motor Driver                  │
          │          │                  │
          ▼          ▼                  │
       N20 Motor   N20 Motor             │
          │          │                  │
          ▼          ▼                  │
      Left Wheel  Right Wheel            │
                                      ┌───┴────┐
                                      │        │
                                      ▼        ▼
                                  IR Sensor   PID
                                    Array    Control
