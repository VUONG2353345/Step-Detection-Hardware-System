# 🚶 Step Detection Hardware System

## 📖 Overview
The Step Detection System is an ankle-worn, multi-sensor hardware project designed to accurately detect and log human walking steps. By fusing kinetic data from a Force Sensitive Resistor (FSR) and inertial data from an MPU-6050 (accelerometer and gyroscope), the system utilizes a Finite State Machine to track real-time gait phases. This approach effectively eliminates false step counts caused by random leg movements or sitting foot-taps.

## ✨ Key Features
* **Multi-Sensor Fusion Algorithm:** Combines ground reaction force (FSR) and 3D motion tracking (MPU-6050) to strictly validate physical steps.
* **4-Phase Gait State Machine:** Implements a strict sequential logic classifying walking into 4 phases: Flat, Lift, Swing, and Strike.
* **Smart SD Card Data Logging:** Efficiently records raw sensor data into `.csv` files at 20ms intervals using a Keep-Open mechanism and automatic buffering to prevent data loss.
* **Real-time Wireless Transmission:** Streams step counts, current phase, and operational duration to a mobile interface via Bluetooth (HC-06) at 100ms intervals.
* **Hardware UI Controls:** Features a debounced push-button for changing system states (Start/Pause/Stop) and LED indicators (Green/Yellow/Red) for visual feedback.

## 🛠 Tech Stack
* **Hardware Components:** Arduino Nano, MPU-6050 (6-axis IMU), Force Sensing Resistor (FSR), HC-06 Bluetooth Module, MicroSD Card Reader, MT3608 Boost Converter, TP4056 Charger.
* **Software/Languages:** C/C++ (Arduino Framework).
* **Key Libraries:** `Adafruit_MPU6050`, `SD`, `SoftwareSerial`, `Wire`, `SPI`.

## 📸 Demo / System Architecture
*(Kéo thả tấm ảnh Sơ đồ khối (Block Diagram), Sơ đồ nguyên lý (Schematic) hoặc ảnh chụp mạch PCB thực tế vào đây nhé)*

## ⚙️ How to Run / Setup

1. **Clone this repository:**
```bash
git clone [https://github.com/VUONG2353345/Step-Detection-Hardware-System.git](https://github.com/VUONG2353345/Step-Detection-Hardware-System.git)
```

2. **Hardware Setup:**
Connect the sensors to the Arduino Nano according to the pin definitions in the code:
* FSR Pin -> `A0`
* MPU-6050 -> `I2C Pins (A4/A5)`
* HC-06 TX/RX -> `Pins 2/3`
* SD Card CS -> `Pin 10`

3. **Software Setup:**
* Open the `.ino` file using the **Arduino IDE**.
* Install the required libraries via the Library Manager: `Adafruit MPU6050`, `Adafruit Unified Sensor`.
* Select **Arduino Nano** as the target board and upload the code.

4. **Monitor Data:**
Open the Serial Monitor (Baud rate: 9600) or connect via a Bluetooth Terminal app on your phone to view real-time step reports.

## 📁 Project Structure
* `Step_Detection.ino`: Main Arduino source code containing setup, sensor reading, state machine logic, and data logging.
* `/schematics`: Contains hardware block diagrams, schematics, and PCB layouts designed in Altium/Proteus.
