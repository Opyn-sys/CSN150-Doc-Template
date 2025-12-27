# Cybersecurity : CSN150
Project: ESP32 Wifi Access Point

## Purpose
Create an ESP32 Access Point with camera, and Document ny process. 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation and tools

##### Video 1: 

https://www.youtube.com/watch?v=k_PJLkfqDuI

##### Other Links: 
https://randomnerdtutorials.com/esp32-cam-access-point-ap-web-server/

##### AI GPTs used

ChatGPT

## Steps I followed

#### 1. Prepared the ESP32-CAM for Programming
- I connected the ESP32-CAM to a USB-to-TTL adapter and wired the required pins (5V, GND, TX, RX). I connected GPIO0 to GND to place the board into flashing mode before uploading the code.

#### 2. Opened the ESP32 Camera Web Server Example
- In the Arduino IDE, I opened the CameraWebServer example included with the ESP32 board package as the base sketch for the project.

#### 3. Configured the ESP32-CAM as a Wi-Fi Access Point
- I modified the example code to use Access Point (AP) mode instead of Station mode. I defined a custom Wi-Fi SSID and password and replaced the Wi-Fi connection logic with WiFi.softAP() so the ESP32-CAM would broadcast its own wireless network.

#### 4. Verified Camera Model and Pin Configuration
- I confirmed that the camera pin configuration matched the AI Thinker ESP32-CAM module to ensure proper camera initialization and image capture.

#### 5. Uploaded the Code to the ESP32-CAM
- I uploaded the modified sketch to the ESP32-CAM using the Arduino IDE. After the upload completed, I disconnected GPIO0 from GND and pressed the reset button to boot the device in normal mode.

#### 6. Monitored Serial Output for Confirmation
- I opened the Serial Monitor at 115200 baud to confirm successful startup. The serial output displayed the Access Point IP address, typically 192.168.4.1, indicating the AP was running correctly.

#### 7. Connected to the ESP32-CAM Wi-Fi Network
- Using my laptop, I connected to the Wi-Fi network created by the ESP32-CAM using the SSID and password defined in the code.

#### 8. Accessed the Web Server Interface
- While connected to the ESP32-CAM network, I opened a web browser and navigated to http://192.168.4.1. The ESP32-CAM web server loaded successfully.

#### 9. Verified Camera and Web Server Functionality
- I confirmed that the web interface displayed camera images correctly and that the ESP32-CAM could serve images over the local Access Point without requiring an external router.

<img width="1470" height="956" alt="Screenshot 2025-12-27 at 4 30 08 AM" src="https://github.com/user-attachments/assets/5bf2f1b2-cc74-4b0f-a7bf-adfdec2517ab" />

## Problems and Solutions
N/a  

## Final Report

In this project, I configured an ESP32-CAM to function as a standalone Wi-Fi Access Point hosting a camera web server. I began by setting up the Arduino IDE and installing the ESP32 board package through the Boards Manager. After selecting the AI Thinker ESP32-CAM board and configuring the upload settings, I prepared the hardware by wiring the ESP32-CAM to a USB-to-TTL adapter and placing the device into flashing mode using GPIO0.

I used the built-in CameraWebServer example as the foundation for the project. Instead of connecting the ESP32-CAM to an existing wireless network, I modified the code to operate in Access Point mode. I defined a custom SSID and password and replaced the station-mode Wi-Fi connection logic with WiFi.softAP(), allowing the ESP32-CAM to broadcast its own Wi-Fi network. I also verified that the camera pin configuration matched the AI Thinker module to ensure proper camera initialization.

After uploading the modified sketch, I removed the GPIO0 grounding and reset the device to boot normally. I monitored the Serial Monitor to confirm successful startup and verified that the ESP32-CAM displayed the expected Access Point IP address, typically 192.168.4.1. This confirmed that the Access Point was running correctly.

I then connected a phone and a laptop to the ESP32-CAM’s Wi-Fi network and accessed the web server through a browser. The camera interface loaded successfully, and I was able to view images served directly by the ESP32-CAM without relying on an external router or internet connection.

Through this lab, I gained hands-on experience with embedded networking, Access Point configuration, and hosting a web server on constrained hardware. The project reinforced the importance of proper board configuration, power stability, and understanding the difference between Station and Access Point modes in Wi-Fi-enabled embedded systems.
