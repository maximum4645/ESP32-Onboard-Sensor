In this project, an ESP32 functions as a web server, serving a webpage displaying its onboard sensor data in real-time.
The ESP32 reads data from BMP280, MPU6050, and SHT4x sensors and provides the data via an API endpoint, "/sensor", in JSON format.
<br/>
The webpage hosted on the ESP32 fetches and displays the sensor data dynamically using JavaScript.
<br/><br/>
The ESP32 uses FreeRTOS to run three concurrent threads:
<br/>
1.update_sensor_data: Reads data from the sensors every 10 seconds and updates global variables.
<br/>
2.print_local_time: Retrieves and prints the local time every second, updating the current_time variable used in the "/sensor" JSON response.
<br/>
3.update_with_NTP: Syncs the local time with an NTP server every minute.
<br/><br/>
To run:
<br/>
1.Connect the sensors (BMP280, MPU6050, SHT4x) to the ESP32 via I2C.
<br/>
2.Upload main.cpp and the index.html file (via SPIFFS) using Arduino IDE or PlatformIO.
<br/>
3.Access the ESP32's IP address in your browser to view the live webpage.
<br/><br/>
Folder Structure:
<br/>
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
Technologies:
<br/>
ESP32 SPIFFS
<br/>
BMP280, MPU6050, SHT4x sensors
<br/>
HTTP + JSON API

