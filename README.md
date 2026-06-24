# Biometric Fingerprint Access Control System



https://github.com/user-attachments/assets/1d6d2333-7021-4c5f-860f-755ca27ffc26



A standalone biometric security system built as an **IoT Club Project**. It uses an optical fingerprint sensor to store, delete, and verify user fingerprints, providing real-time visual feedback on a direct-wired 16x2 parallel LCD screen. 

Instead of using an I2C adapter, this project interfaces directly with the 16-pin LCD configuration using a 4-bit parallel data bus.

---

## 🚀 Features
* **Real-time Scanning:** Constantly checks for registered fingers and triggers "ACCESS GRANTED" or "ACCESS DENIED" instantly.
* **On-Board Admin Controls:** Easily enroll or delete fingerprint IDs (1–127) directly via the Arduino Serial Monitor.
* **Dual Feedback:** Displays status updates simultaneously on both the hardware LCD screen and the software Serial logs.

---

## 🛠️ Hardware Components
* **Microcontroller:** Arduino Uno (or compatible)
* **Biometric Sensor:** AS608 / R307 Optical Fingerprint Sensor
* **Display:** 16x2 Character LCD (Blue Backlight, standard 16-pin parallel interface)
* **Prototyping Gear:** Breadboard, jumper wires, and a 10k Potentiometer (for LCD contrast adjusting).

---

## 📌 Pin Mapping

Because this setup bypasses an I2C breakout board, the connections use a standard 4-bit data architecture to save Arduino digital pins.

### 1. Fingerprint Sensor Connection
| Sensor Pin | Arduino Pin | Description |
|---|---|---|
| **VCC** | 5V | Power |
| **TX** | Pin 10 | Software Serial RX |
| **RX** | Pin 9 | Software Serial TX |
| **GND** | GND | Ground |

### 2. 16x2 LCD Connection (Parallel Mode)
| LCD Pin | Connected To | Description |
|---|---|---|
| **Pin 1 (VSS)** | GND | Ground |
| **Pin 2 (VDD)** | 5V | Power |
| **Pin 3 (VO)** | Potentiometer wiper | Contrast Control |
| **Pin 4 (RS)** | **Pin 12** | Register Select |
| **Pin 5 (RW)** | GND | Read/Write Select |
| **Pin 6 (E)** | **Pin 11** | Enable Signal |
| **Pins 7-10** | *Unused* | Data Bits 0-3 |
| **Pin 11 (D4)** | **Pin 5** | Data Bit 4 |
| **Pin 12 (D5)** | **Pin 4** | Data Bit 5 |
| **Pin 13 (D6)** | **Pin 3** | Data Bit 6 |
| **Pin 14 (D7)** | **Pin 2** | Data Bit 7 |
| **Pin 15 (A)** | 5V (via 220Ω resistor) | Backlight Anode |
| **Pin 16 (K)** | GND | Backlight Cathode |

### 3. Push-Button Configurations (Active LOW with Internal Pullups)
| Hardware Button | Arduino Pin | Action Description |
|---|---|---|
| **Enroll Button** | **Pin 6** | Opens Enrollment Mode / Confirms Selections |
| **Delete Button** | **Pin 7** | Opens Deletion Mode / Acts as Cancel |
| **UP Button** | **Pin 8** | Increments local ID selections (1 - 127) |
| **DOWN Button** | **Pin 13** | Decrements local ID selections (1 - 127) |

---

## 💻 How To Run

1. **Clone the Repository:**
```bash
   git clone [https://github.com/HakeemMoazam/fingerprint-auth-system.git](https://github.com/HakeemMoazam/fingerprint-auth-system.git)
   cd fingerprint-auth-system
