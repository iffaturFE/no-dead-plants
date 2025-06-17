Smart Irrigation System with pH and Moisture Sensor and Email Alert 🌱✨
# no-dead-plants


Project Description:

This Smart Irrigation System is designed to:

-> Monitor soil moisture and pH in real-time.

-> Activate irrigation when soil moisture drops below a set threshold.

-> Send email alerts if soil pH falls outside a desirable range.

This project is powered by ESP32 with WiFi for connectivity, making it convenient and flexible for your garden or greenhouse.


Features:

-> Automated Irrigation — Water is turned on when the soil is too dry.

-> pH Alert — An email notification is sent if pH drops or climbs above the desirable range.

-> Real-Time Measurements — pH and soil moisture are constantly measured.

-> WiFi Connection — Easily connect to your home router for alerts.

-> Customizable Thresholds — Adjust soil moisture and pH alerts to suit your growing conditions.



Hardware Requirements:

-> ESP32 or ESP8266 board

-> Soil Moisture Sensor (with analog output)

-> pH Sensor (with analog output)

-> Relay Module (for Water Pump control)

-> Small Water Pump (5V or 12V)

-> 5V Power Supply for ESP32/Relay/Sensors

-> Additional 12V Power Supply for Water Pump (with shared ground)

-> Breadboard and Hook-up Wire



Software Requirements:

-> Arduino IDE or PlatformIO

-> ESP-Mail-Client library for sending emails

-> Adafruit-Sensors and Adafruit-Unified-Sensors libraries (for pH, soil moisture if applicable)



Installation:

-> Clone this repository:

`git clone https://github.com/yourusername/smart-irrigation.git`

-> Open smart_irrigation.ino in Arduino IDE or PlatformIO.



Installation (Library):

-> Add these libraries to your Arduino IDE:

-> ESP-Mail-Client

-> Adafruit-Sensors

-> Adafruit-Unified-Sensors



Pin Connection:

Component	---> ESP32 Pin

pH Sensor	---> GPIO 35

Moisture Sensor	---> GPIO 34

Relay Module	---> GPIO 26

Water Pump	---> Relay (Controlled by GPIO 26)

WiFi	---> Managed by ESP32 internally




How It Works:

-> The ESP32 constantly checks soil moisture (lower == drier) and pH.

-> If the soil drops below the threshold, it activates the water pump for a short period.

-> If pH drops or climbs outside range (pH < 5.5 or pH > 7.5), it parses an email alert with pH details.




Email alerts:

To enable alerts:

Set up your SMTP credentials and the recipient’s email in the code:


```
const char* ssid = "your-ssid";
const char* password = "your-wifi-password";

#define SMTP_HOST "smtp.example.com"
#define SMTP_PORT 465
#define AUTHOR_EMAIL "your.email@example.com"
#define AUTHOR_PASSWORD "your_secret_pass"
#define RECIPIENT_EMAIL "alert.email@example.com"

const int soilMoistureThreshold = 500;
const float pHLow = 5.5;
const float pHHigh = 7.5;
```



File Structure:

```
smart-irrigation/
 └ src/
   └ smart_irrigation.ino
 └ smart_irrigation_box.scad
 └ README.md
 └ license.txt
 └ requirements.txt
```


 
How to Use:

-> Wire components to ESP32 following the schematic.

-> Update your WiFi, pH, soil moisture threshold, and SMTP credentials in the code.

-> Compile and upload to ESP32.

-> Monitor Serial Monitor for messages.

-> pH alerts will arrive by email, and irrigation will activate when the soil is dry.




Future Improvement Ideas:

-> Implement phone notifications with PushBullet or IFTTT.

-> Monitor temperature, light, or CO₂ alongside pH and soil moisture.

-> Provide a small OLED or LCD for real-time data.

-> Develop a phone application to control irrigation remotely.



Support:
If you have any questions or issues, please feel free to create a new Issue or Pull Request in this repository.

