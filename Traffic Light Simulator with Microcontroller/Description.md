# 🚦 Traffic Control System using Tiva C Microcontroller

**Course**: ECE 132  
**Institution**: Lehigh University  
**Contributors**:  
- David Okeh 
- Owen Funk  
**Department**: Electrical and Computer Engineering  

---

## 📘 Abstract

This project presents the implementation of a traffic control system designed for a two-way intersection using the **Tiva C microcontroller**, **infrared sensors**, **LED indicators**, and **interrupt-driven logic**. The system automates traffic light management and integrates a **pedestrian override function** for safe crossing.

---

## 🎯 Project Objective

Design and implement an intelligent intersection system capable of:
- Managing flow based on the number of cars waiting
- Allowing safe pedestrian crossings using an override button
- Operating reliably with minimal power consumption using interrupts

---

## 🔌 Hardware Components

- **Tiva C Series Microcontroller**  
- **4 LEDs** (2 green, 2 red)  
- **2 IR Distance Sensors** for vehicle detection  
- **Pushbutton** (pedestrian override)  
- **Resistors** for current limiting  
- **Breadboards** (modular design for each traffic direction)

### 📐 Wiring Overview

- Two breadboards represent the two roads in the intersection  
- Each board contains two LEDs and one IR sensor  
- GPIO pins are used to manage LEDs and receive sensor/button input  
- Power is supplied by the microcontroller  

![Wiring Schematic](#)  
![Layout Diagram](#)

---

## 💻 Software Design

### 🔁 Logic Flow

- **Interrupt-based architecture**: Improves power efficiency  
- **IR sensor interrupts**: Count vehicles and trigger flow logic  
- **Pedestrian button interrupt**: Turns both lights red for 20 seconds  
- **Main loop**:
  - Monitors car counts
  - Switches lights based on count thresholds or timer
  - Default timer triggers toggling every ~60 seconds

### 🧠 Decision-Making

- Both car counts and time-based conditions affect light toggling  
- Designed to prioritize avoiding traffic build-up on busier roads  
- Car counts are tracked whether light is red or green, to ensure responsiveness  

---

## 🧪 Testing Procedure

### Test Scenarios Covered:

1. **Car count threshold triggers toggle**
2. **Pedestrian override correctly activates red lights**
3. **Timer-based toggle occurs after ~1 minute of inactivity**
4. **Simultaneous inputs from both directions are processed**
5. **Interrupts debounce correctly to avoid false readings**
6. **Realistic mixed traffic flow conditions evaluated**
7. **Debugging via Code Composer Studio to monitor logic in real-time**

![Test Bench](#)

---

## ✅ Results

- The system fulfilled all original design requirements
- Successfully handled both active and idle traffic conditions
- Efficient and reliable IR-based vehicle detection
- Timer fallback provided robust operation during low traffic
- Pedestrian override worked consistently across multiple trials

---

## 📌 Future Improvements

- **Add Yellow Light Phase** for more realistic transitions  
- **Expand to Two-Way Streets** by duplicating hardware  
- **Better Vehicle Detection Accuracy** using multiple sensors  
- **Logging Capabilities** to monitor usage statistics and traffic patterns  
- **Integrate LCD or 7-segment display** for status output  

---

## 🧠 Key Learnings

- Implementing **hardware/software integration** with microcontrollers  
- Designing **interrupt-driven systems** for efficiency  
- Balancing real-world constraints with system logic  
- Testing edge cases and iteratively debugging using embedded tools  

---

## 📝 Conclusion

This project successfully simulated a smart traffic light system using accessible components and embedded programming. The use of interrupts, IR sensors, and decision logic allowed the system to operate autonomously and responsively, with potential for real-world scalability and integration into urban IoT frameworks.
