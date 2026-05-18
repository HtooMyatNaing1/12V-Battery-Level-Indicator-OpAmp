# 🔋 12V Battery Level Indicator Using Op-Amps

## 📌 Project Overview

This project implements a 12V battery level indicator using operational amplifiers configured as comparators.  
Three voltage thresholds are defined to indicate battery status using Red, Yellow, and Green LEDs.

The system is designed entirely using basic analog components — no microcontrollers or digital logic.

---

## ⚙️ Components Used

- 3 × LM741 Operational Amplifiers (used as comparators)
- Zener Diode (Voltage Reference)
- Resistor Voltage Divider Network
- 3 × LEDs (Red, Yellow, Green)
- 12V DC Source
- 1kΩ LED Current Limiting Resistors
- Supporting resistors for threshold generation

---

## 🧠 Working Principle

1. The battery voltage is scaled down using a resistor voltage divider.
2. A Zener diode provides a stable reference voltage.
3. Three comparators compare the scaled battery voltage with different reference thresholds.
4. Each comparator activates an LED when its threshold is exceeded.

This design uses **cumulative threshold detection**, meaning LEDs turn on progressively as voltage increases.

---

## 🔬 Threshold Behavior

| Battery Voltage | LED Status |
|-----------------|------------|
| ≥ 12V           | Green + Yellow + Red |
| 11V             | Yellow + Red |
| 10V             | Red |
| < 10V           | No LED |

---

## 📐 Voltage Scaling Calculation

The battery voltage is scaled using a voltage divider:

V_scaled = V_battery × (R2 / (R1 + R2))

For example:

If R1 = 1.5kΩ and R2 = 1kΩ,

V_scaled = V_battery × (1k / 2.5k)  
V_scaled = V_battery × 0.4

This ensures safe input levels for the op-amps.

---

## 🏗 Design Considerations

- Zener diode provides stable reference voltage.
- Comparator thresholds are set using a resistor ladder network.
- 1kΩ resistors are used to limit LED current (~10mA).
- Designed for a 12V lead-acid battery system.
- Tested under multiple input voltage conditions in simulation.

---

## ⚠️ Limitations

- LM741 is not ideal for single-supply operation.
- No hysteresis implemented (possible flickering near thresholds).
- Designed primarily for academic and simulation purposes.
- Cumulative indication instead of exclusive LED behavior.

---

## 🚀 Possible Improvements

- Replace LM741 with LM339 comparator IC.
- Add hysteresis (Schmitt trigger configuration).
- Convert to ADC-based microcontroller monitoring.
- Implement exclusive LED indication logic.
- Design a PCB layout version.

---

## 💡 What I Learned

- Practical use of operational amplifiers as comparators
- Designing stable voltage references using Zener diodes
- Multi-threshold voltage detection systems
- Analog circuit debugging and voltage tracing
- Understanding cumulative vs exclusive indication systems

---

## 📷 Project Files

- `schematic.png` — Circuit schematic
- `simulation/` — Simulation files
- `images/` — Output test results
- `calculations.pdf` — Design calculations

---

## 📚 Project Type

Analog Electronics  
Comparator-Based Threshold Detection  
Hardware Design (No Microcontroller)

---
