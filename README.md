mqtt-automanual-input

# MQTT Sensor and Auto/Manual Input

Just a simple MQTT message display (with ESP8266 as additional tools)

## Features
### Switch input mode

#### Auto mode
-  Shows indicator from generated message, disables "send" switch

#### Manual mode
-  Stores auto mode values and override to manual mode, enables "send" switch

#### Sensor indicator
-  Displays sensor value

## Output
Displays indicator to web and ESP8266

### Requirements:
1. Python Library
   1. paho-mqtt
2. Arduino IDE
   1. PubSubClient v2.6
   2. ESP8266Wifi
   3. ArduinoJson v6
   4. Adafruit DHT
3. ESP8266 (NodeMCU)
   1. LED
   2. DHT11 or DHT22 temperature/humidity sensor

## Running the program
1. Download or clone the repository
2. Run the python program (`python mqtt_pub_test_group.py`)
3. Open the html file
4. For ESP8266: open and upload `IoT_esp.ino` to device
   -  Don't have ESP? It's fine, the html already represents values in ESP's serial monitor. For sensors, you can unquote commands related to sensors in python file (the commands are the same as auto part), then publish them
   -  Additional tools: you can analyze MQTT topics in topic viewer, such as mosquitto topic viewer (with `mosquitto-sub -t 'insert_topic'` in cmd, make sure to change directory to mosquitto folder). If you're not into cmd, MQTTX topic viewer helps too

## Operating the program
- When everything is running, the initial state is in **auto mode**, which means ESP receives data from data generated from python. LED buttons are disabled
- In HTML file, you can switch to **manual mode**, which you can input LED individually
- ESP publishes sensor values to html. No inputs needed
- All MQTT messages are in JSON format

### Notes
- Be careful if you want to switch to **manual mode** early as html has not received messages yet. When this happens, the individual input only publishes only individual value (it's JSON btw). This means you have to wait for messages first before switching to **manual mode** (*will be improved later*)
  
### References I learn and use (with modifications)
- [ArduinoJson (with v6 documentation)](https://arduinojson.org/)
- [Rui Santos: ESP8266 publishing DHT data to Flask Web](https://randomnerdtutorials.com/esp8266-publishing-dht22-readings-with-mqtt-to-raspberry-pi/)
- [EMQX: MQTT publish generator](https://www.emqx.io/blog/how-to-use-mqtt-in-python)
- [Steve's Internet Guide: MQTT Javascript](http://www.steves-internet-guide.com/using-javascript-mqtt-client-websockets/)
