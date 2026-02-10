# 🧪 Automatic Pipetting Station (Budget-Friendly Lab Automation)

## 📌 Overview

The **Automatic Pipetting Station** is a low-cost, automated liquid handling system developed for laboratory workflows such as reagent dispensing, mixing, and serial dilution.  
The system integrates **embedded motion control**, **computer vision**, and an **interactive touchscreen-based user interface** to provide a reliable, safe, and flexible automation platform.

The objective of this project is to deliver a **cost-effective alternative to commercial pipetting robots** while maintaining precision, repeatability, and operational safety.

---

## 🛠 System Architecture

### 🔹 Hardware Components

**ESP32**
- Controls 3-axis motion system (X, Y, Z)
- Handles pipette actuation for aspiration and dispensing
- Executes low-level motion and timing-critical operations

**Raspberry Pi 5**
- Acts as the main system controller
- Hosts the graphical user interface and high-level logic
- Interfaces with ESP32 and vision subsystem
- Connected to a 10-inch touchscreen display

**3-Axis Motion System**
- Cartesian X, Y, Z configuration
- Pipette mounted on the Z-axis for vertical liquid handling
- Designed for repeatable and precise positioning

**Camera Module**
- Used for vision-based labware presence verification
- Enables safety checks before protocol execution

---

## 💻 Software Stack

- **Python** – High-level control and orchestration
- **PyQt5** – Touch-optimized graphical user interface
- **Multi-threading**
  - Parallel execution of UI, motion commands, and vision processing
  - Ensures responsive user interaction during operation
- **OpenCV**
  - Camera integration
  - Labware presence detection and validation
- **ESP32 Firmware**
  - Axis motion control
  - Pipette aspiration and dispense logic
  - Communication interface with Raspberry Pi

---

## 🖥 User Interface (UI)

- Touch-friendly PyQt5-based interface
- Calibration screen to compensate for mechanical and positional offsets
- Real-time status updates during machine operation
- Pop-up alerts for missing or incorrectly placed labware

> ⚠️ Current calibration logic is hardcoded; future revisions will include dynamic and user-guided calibration routines.

---

## ⚙️ Working Principle

1. The user launches the main application (`main.py`)
2. The system initiates a **camera-based labware presence check**
3. If required labware is missing or misplaced:
   - A UI pop-up notifies the user
   - Execution is paused
4. Once all labware is correctly detected, the automated sequence begins:
   - Pipette tip is picked from the tip box
   - The system moves to the reagent container
   - **60 µL** of liquid is aspirated
   - Liquid is dispensed equally into **three wells**
   - The process repeats for subsequent wells
   - The used tip is ejected into the ejection box
   - A new tip is picked and the cycle continues

---

## 🔬 Supported Operations

- Automated liquid aspiration and dispensing
- Pipette tip pickup and ejection
- Mixing operations
- Serial dilution workflows
- Vision-based labware presence detection
- Expandable architecture for custom protocols

---

## 🧠 Safety & Reliability Features

- Mandatory labware presence verification before execution
- Automatic pause and resume functionality
- Reduction of failed runs due to missing labware
- Minimization of reagent wastage
- Enhanced operational safety and repeatability

---

## 🚧 Future Enhancements

- Dynamic and user-guided calibration
- Custom protocol editor
- Volume-adaptive dispensing
- Advanced error handling and recovery
- Detailed experiment logging (local or cloud-based)
- Support for additional labware types and layouts
