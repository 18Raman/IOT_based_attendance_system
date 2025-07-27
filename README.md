# 🛠️ IoT-based RFID Attendance System using NodeMCU ESP8266

This project is an Internet of Things (IoT)-based RFID attendance system that utilizes the **NodeMCU ESP8266 microcontroller** and **RFID RC522 module** to log attendance data to **Google Sheets** in real-time. This solution is ideal for institutions looking for a contactless, secure, and cloud-based attendance system.

---

## 🚀 Features

- 📶 Wi-Fi-based logging using ESP8266
- 🕹️ RFID card reader/writer (MFRC522)
- 🔒 Secure data authentication with MIFARE cards
- 📡 Real-time data sync with Google Sheets via Google Apps Script
- 🔊 Buzzer feedback for user interaction
- 📈 Expandable to include timestamps and dashboard integration

---

## 🧩 Tech Stack

- **Microcontroller:** NodeMCU ESP8266
- **RFID Module:** MFRC522
- **Language:** C++ (Arduino)
- **Communication:** SPI, HTTP
- **Cloud Integration:** Google Apps Script + Google Sheets
- **IDE:** Arduino IDE

---

## 🖥️ Working Principle

1. **Card Writing**  
   Write user information (e.g., name or ID) to RFID card block using MFRC522 module.

2. **Card Reading & Authentication**  
   When a user scans their RFID card, the system authenticates and reads the block data.

3. **Data Upload**  
   The data is sent to a Google Sheet through an HTTPS GET request using a custom Apps Script endpoint.

4. **Confirmation**  
   A buzzer gives feedback on successful scan and data upload.

---

## 📸 Circuit Diagram

> 📷 *(Attach a circuit diagram image here or embed one from `/assets/circuit_diagram.png`)*  
- **D3 (RST)**: Connected to RC522 RST  
- **D4 (SS)**: Connected to RC522 SDA  
- **D2**: Connected to Buzzer  
- **3.3V / GND**: Power supply to RC522 and NodeMCU

---

## 🧪 How to Run

### 🧰 Hardware Required
- NodeMCU ESP8266
- MFRC522 RFID Reader
- RFID Cards/Tags
- Buzzer
- Jumper wires
- Breadboard

### 📦 Software Required
- Arduino IDE
- MFRC522 Library
- ESP8266 Board Package
- WiFi Credentials (for your network)

### 🔧 Steps

1. **Card Writing (Setup):**
   - Flash `write_card.ino` to NodeMCU
   - Write user data to RFID block (e.g., block 2)

2. **Google Sheet Setup:**
   - Create a Google Apps Script to receive GET requests
   - Deploy as web app and note the URL

3. **Attendance Logging:**
   - Flash `attendance_logger.ino` to NodeMCU
   - System reads RFID card, sends data to the Apps Script URL
