# 🤖 Robotic Arm Torque Calculation and Servo Motor Selection

## 🧮 1. Torque Calculation for Each Joint

### ✅ Arm Specs:
- Link 1 length: 15 cm (0.15 m)
- Link 2 length: 10 cm (0.10 m)
- Payload: 1 kg (then recalculated for 2 kg)

---

### ⚙️ Case 1: Lifting a *1 kg* payload

#### 🔹 Joint 2 (only lifts the payload):
\[
Torque = Mass × Gravity × Distance  
= 1 × 9.81 × 0.1 = *0.981 Nm*
\]

#### 🔹 Joint 1 (at the base, lifts entire arm and payload):
- Payload torque: \( 1 × 9.81 × 0.25 = 2.4525 Nm \)  
- Arm weight (assumed 0.3 kg at 0.075 m): \( 0.3 × 9.81 × 0.075 = 0.2207 Nm \)  
- *Total torque = 2.4525 + 0.2207 = 2.6732 Nm*

---

### ⚙️ Case 2: Lifting a *2 kg* payload

#### 🔹 Joint 2:
\[
Torque = 2 × 9.81 × 0.1 = *1.962 Nm*
\]

#### 🔹 Joint 1:
- Payload torque: \( 2 × 9.81 × 0.25 = 4.905 Nm \)  
- Arm torque remains the same: 0.2207 Nm  
- *Total torque = 4.905 + 0.2207 = 5.1257 Nm*

---

## 🔧 2. Suitable Servo Motor Selection

| Joint         | Required Torque | Recommended Servo           | Notes                      |
|---------------|------------------|------------------------------|-----------------------------|
| Joint 2 (1 kg) | ~0.98 Nm         | 30 kg·cm Servo (~3 Nm)       | Adequate with margin        |
| Joint 1 (1 kg) | ~2.67 Nm         | 40 kg·cm Servo (~4 Nm)       | Acceptable margin           |
| Joint 2 (2 kg) | ~1.96 Nm         | ≥2 Nm Servo or gear support  | Gear recommended if reused  |
| Joint 1 (2 kg) | ~5.13 Nm         | ≥5 Nm Servo or gear support  | Stronger servo or gearbox   |

Suggested links:
- [30kg·cm Servo – ATO](https://www.ato.com/30kg-cm-rc-servo-motor)
- [40kg·cm Servo – ATO](https://www.ato.com/40kg-cm-rc-servo-motor)

---

## ❓ 3. Can the Same Motors Be Used for 2 kg Payload?

✅ *Yes — but only with gear reduction*

- Gearboxes increase output torque while reducing speed.
- Example: A 3 Nm motor can achieve ~5 Nm with a 2:1 or 3:1 reduction gear.

---

## ⚠️ 4. Drawbacks of Using Gears

| Drawback              | Explanation                               |
|-----------------------|-------------------------------------------|
| 🔥 Increased heat      | Motors work harder with higher load       |
| 🐢 Slower motion       | More torque = less speed                  |
| ⚡️ Higher power usage | More current drawn from power supply      |
| 🛠️ Gear wear           | Especially plastic gears under high load |
| ⚖️ Heavier arm         | Gearboxes add to total system weight      |

---

## 💡 5. Alternative Design Solutions

- Use stronger servo motors from the beginning
- Shorten the arm links to reduce torque
- Use lightweight materials for arm structure
- Integrate compact gearbox systems (e.g., planetary gears)
- Balance the arm using counterweights

---

📌 Calculations are based on the torque formula:

Torque = Mass × Gravity × Distance

Servo selection was made accordingly, ensuring safe operation within margin.
