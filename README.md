# 🔒 Digital Lock System — CSE211S
### Ain Shams University · Faculty of Engineering · Spring 2026

![Logic Design](https://img.shields.io/badge/Logic-Design-blue?style=flat)
![Proteus](https://img.shields.io/badge/Proteus-Simulation-orange?style=flat)
![Hardware](https://img.shields.io/badge/Hardware-Breadboard-green?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

> Course: **CSE211S — Logic Design**


---

## 📌 Project Overview

A hardware-based digital lock system designed using combinational and sequential logic components. The system accepts a password via DIP switches and grants or denies access based on whether the input matches the stored code. It features a countdown timer, lockout mechanism, and buzzer alarm for security.

---

## ⚙️ System Behavior

### Normal Operation
→ User inputs code via DIP switches
→ System compares input against stored password using an 8-bit magnitude comparator (IC 74688)
→ **Correct code:** Green LED turns on, countdown timer starts
→ **Wrong code:** Red LED stays on, attempt counter decrements

### Lockout Mechanism
→ After **3 wrong attempts**, the buzzer activates and a 30-second lockout timer begins
→ During the 30-second lockout, even the correct code is rejected
→ After timeout expires, system returns to normal input-receiving mode

### Clock Generation
→ A 555 Timer circuit generates a **1 Hz clock signal** to drive and synchronize the system's counters

---



## ⚡ Challenges & Solutions

**Challenge 1 — Simulation Constraints**
Several ICs lacked active models in the Proteus database. Solved by redesigning around ICs that had both verified simulation libraries and local availability.

**Challenge 2 — Floating Inputs (D Flip-Flop CLK)**
Push button caused undefined behavior due to floating CLK pin picking up electromagnetic noise. Solved by adding a pull-down resistor to ensure a rock-solid Logic Low when the button is not pressed.

**Challenge 3 — 7-Segment Display Flickering**
Missing current-limiting resistors between the decoder and display caused ghosting and erratic behavior. Solved by calculating and inserting the correct resistance for each segment.

**Challenge 4 — Hidden Hardware Fatigue**
Timer stopped toggling after weeks of testing — traced to a fatigued jumper wire on Pin 2 (Trigger) and Pin 6 (Threshold) of the 555 Timer. Replacing the jumper restored the circuit.


---

## 📄 Full Report

[📄 View Full Report](./Digital-Lock-Project-Report.pdf)

---

## 📫 Contact

**Hana Hassan Hamed**
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/hana-hassan-hamed)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white)](mailto:hanahassan2006@gmail.com)
