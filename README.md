# Wireless Robot Controlled by MPU6050 (Transmitter & Receiver)

This project creates a wirelessly controlled robot using two Arduino boards:
- A **transmitter** that reads tilt angles from an MPU6050 sensor
- A **receiver** that controls two DC motors based on tilt data via nRF24L01+

---

## 🧰 Hardware Used

- 2 × Arduino Uno
- 1 × MPU6050 (Gyro/Accelerometer)
- 2 × nRF24L01+ modules
- 1 × L298N motor driver module
- 2 × DC motors (Left & Right)
- Power source, jumper wires, capacitors

---

## 📡 System Overview

**Transmitter:**
- Reads `ax`, `ay` from MPU6050
- Maps values to a range
- Sends data via nRF24L01

**Receiver:**
- Receives `data[0]` and `data[1]`
- Moves motors forward, backward, left, or right based on tilt
- Stops when centered

---

## 🔌 Wiring Overview

### Transmitter:
- MPU6050 to A4 (SDA), A5 (SCL), VCC, GND
- nRF24L01 to D9 (CE), D10 (CSN), plus SPI (D11, D12, D13)

### Receiver:
- nRF24L01 to D9 (CE), D10 (CSN), SPI
- L298N:
  - IN1: D2
  - IN2: D4
  - IN3: D7
  - IN4: D6
  - enbA: D3 (PWM)
  - enbB: D5 (PWM)

---

## 📦 Libraries Used

- `RF24`
- `I2Cdev`
- `MPU6050`
- `Wire`
- `SPI`

Install them via Arduino Library Manager or GitHub.

---

## 📝 Notes

- Use capacitors (10µF+) across VCC and GND on nRF24L01 for stability
- Tune motor speed using `RightSpd` and `LeftSpd` variables
- Keep both Arduinos powered independently

---

## 📷 Optional

Attach wiring images or a short demo video link here.

