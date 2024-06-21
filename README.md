# ESP8266 RFID Reader Module Project

#### Project Overview
This project illustrates how to interface an ESP8266 microcontroller with an RFID reader module to read RFID tags or cards. The ESP8266 communicates with the MFRC522 RFID reader module via SPI (Serial Peripheral Interface) to identify and display unique identifiers (UIDs) of RFID tags detected by the reader.

#### Components Needed
- **ESP8266 Microcontroller**
- **MFRC522 RFID Reader Module**
- **Jumper Wires**

#### Block diagram


#### Circuit Setup
1. **Connecting the RFID Reader Module to ESP8266:**
   - Connect the SPI pins (MISO, MOSI, SCK) of the MFRC522 module to the corresponding SPI pins of the ESP8266 (usually labeled on the NodeMCU or other ESP8266 boards).
   - Connect the RST pin of the MFRC522 module to GPIO pin D1 on the ESP8266.
   - Connect the SS (Slave Select) pin of the MFRC522 module to GPIO pin D2 on the ESP8266.
   - Ensure a common ground (GND) connection between the ESP8266 and the RFID module.

#### Instructions
1. **Setup:**
   - Initialize serial communication at a baud rate of 9600 for debugging purposes.
   - Initialize the SPI bus using `SPI.begin()`.
   - Initialize the MFRC522 RFID reader using `mfrc522.PCD_Init()`.
   - Print "RFID reader initialized" to the Serial Monitor upon successful initialization.

2. **Operation:**
   - In the `loop()` function:
     - Continuously check if a new RFID card/tag is present using `mfrc522.PICC_IsNewCardPresent()`.
     - If a new card is detected, read its UID using `mfrc522.PICC_ReadCardSerial()`.
     - Print the UID to the Serial Monitor using the helper function `dump_byte_array()`.

3. **Helper Function:**
   - `dump_byte_array(byte *buffer, byte bufferSize)`: This function prints the contents of the UID array in hexadecimal format to the Serial Monitor.

#### Applications
- **Access Control Systems:** Authenticate users based on RFID tags/cards.
- **Inventory Management:** Track items or assets using RFID technology.
- **Identification Systems:** Identify personnel or participants in events.

#### Notes
- **SPI Communication:** Ensure correct wiring and configuration of SPI pins between ESP8266 and MFRC522 module.
- **Serial Output:** Use the Serial Monitor to monitor and debug RFID tag UID readings.
- **RFID Library:** The MFRC522 library simplifies communication with the RFID module; ensure it is correctly installed in the Arduino IDE.

---

#### Useful Links
🌐 [ProjectsLearner - ESP8266 RFID Reader Module](https://projectslearner.com/learn/esp8266-rfid-reader-module)  
📧 [Email](mailto:projectslearner@gmail.com)  
📸 [Instagram](https://www.instagram.com/projectslearner/)  
📘 [Facebook](https://www.facebook.com/projectslearner)  
▶️ [YouTube](https://www.youtube.com/@ProjectsLearner)  
📘 [LinkedIn](https://www.linkedin.com/in/projectslearner)

Created with ❤️ by ProjectsLearner