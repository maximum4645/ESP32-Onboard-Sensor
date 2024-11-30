# Overview
This project uses an ESP32 as a web server to collect data from BMP280, MPU6050, and SHT4x sensors, provide it in JSON format through a "/sensor" API endpoint, and dynamically display it on a real-time webpage using JavaScript.<br/>

The ESP32 uses FreeRTOS to run three concurrent threads:
<br/>
1.update_sensor_data: Reads data from the sensors every 10 seconds and updates global variables.
<br/>
2.print_local_time: Retrieves and prints the local time every second, updating the current_time variable used in the "/sensor" JSON response.
<br/>
3.update_with_NTP: Syncs the local time with an NTP server every minute.<br/>

**youtube**: https://youtu.be/n_eKqIBGxCw?si=hSastkBCULhc7ygm<br/><br/>

![p3](https://github.com/user-attachments/assets/3e3a1e67-bdc6-456d-9ac9-ba6e8d5024df)

# Folder Structure
project-3/
<br/>
├── data/
<br/>
│   └── index.html
<br/>
├── src/
<br/>
│   └── main.cpp
<br/><br/>

# Technologies
- ESP32 SPIFFS
- BMP280, MPU6050, SHT4x sensors
- HTTP + JSON API

# To run
1.Connect the sensors (BMP280, MPU6050, SHT4x) to the ESP32 via I2C.
<br/>
2.Upload main.cpp and the index.html file (via SPIFFS) using Arduino IDE or PlatformIO.
<br/>
3.Access the ESP32's IP address in your browser to view the live webpage.
