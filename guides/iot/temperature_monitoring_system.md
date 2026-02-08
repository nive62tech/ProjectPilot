1. Project Overview

In this project, you will build a Temperature Monitoring System using an Arduino and a temperature sensor.

The system reads temperature values from the sensor and displays them on the Serial Monitor.
This project introduces how Arduino interacts with real-world sensors and reads analog data.

By the end of this project, you will understand:

How temperature sensors work

How Arduino reads sensor values

How to convert sensor data into meaningful units

2. Difficulty Level

Beginner

3. Prerequisites

Basic computer usage

No prior electronics experience required

Completion of the LED control project is recommended

4. Tools & Platforms
Hardware

Arduino Uno (or compatible board)

Temperature sensor (LM35 or DHT11)

Breadboard

Jumper wires

USB cable

Software

Arduino IDE

Windows / Linux / macOS computer

5. Arduino IDE Setup
Step 1: Install Arduino IDE

Download from https://www.arduino.cc/en/software

Install using default settings

Step 2: Connect Arduino Board

Connect Arduino to computer using USB cable

Ensure power LED on board turns ON

6. Board & Port Selection

In Arduino IDE:

Select Board

Go to Tools → Board

Select Arduino Uno

Select Port

Go to Tools → Port

Select the COM port corresponding to Arduino

If no port is visible, see troubleshooting section.

7. Sensor Connections (LM35 Example)

VCC → 5V on Arduino

GND → GND on Arduino

OUT → Analog pin A0

Ensure all connections are tight.

8. Step-by-Step Project Roadmap
Step 1: Open a New Sketch

File → New

Step 2: Write Temperature Reading Code
int sensorPin = A0;


void setup() {
  Serial.begin(9600);
}


void loop() {
  int sensorValue = analogRead(sensorPin);
  float voltage = sensorValue * (5.0 / 1023.0);
  float temperatureC = voltage * 100;


  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.println(" °C");


  delay(1000);
}
Step 3: Upload the Code

Click Verify

Click Upload

Open Serial Monitor

Set baud rate to 9600

9. Common Errors & Troubleshooting
Error: Serial Monitor Shows Garbage Values

Cause: Baud rate mismatch
Fix: Set Serial Monitor baud rate to 9600

Error: No Temperature Change

Cause: Loose sensor connections
Fix: Recheck wiring and sensor orientation

Error: Port Not Found

Cause: Driver or USB issue
Fix:

Reconnect USB cable

Reinstall Arduino IDE

Try different USB port

10. Testing & Validation

Temperature values should update every second

Touch the sensor lightly to see value change

Ensure values are realistic (room temperature ~25–35°C)

11. Deployment / Submission

Take photo/video of Serial Monitor output

Upload Arduino sketch to GitHub

Add README explaining connections

Share project link on LinkedIn

12. Extensions & Improvements

Display temperature on LCD

Log temperature data to file

Send temperature data to cloud

Add humidity sensing