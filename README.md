# ekf-robot-localization

EKF sensor fusion for mobile robot localization, fusing a BNO055 IMU and Lidar over a 10×10m square path with a single known landmark.

## What it does
- **Prediction** — non-holonomic motion model driven by IMU acceleration and yaw rate
- **Correction** — Lidar landmark observations transformed into global-frame position estimates
- **Comparison** — full-rate vs. half-rate corrections: ~same accuracy (0.181m vs. 0.176m mean error), but 135% more position uncertainty at half-rate

## Key results
| Correction rate | Mean error | RMS error | Position uncertainty (σ²) |
|---|---|---|---|
| Every step | 0.181 m | 0.219 m | 0.044 m² |
| Every other step | 0.176 m | 0.218 m | 0.10 m² |

## Stack
Python · NumPy · BNO055 IMU · Lidar

## Report
See Sensor Fusion for Mobile Robot Localization pdf for full EKF design, coordinate transforms, and noise tuning.
