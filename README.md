mqtt-automanual-input

# MQTT Sensor and Auto/Manual Input

Just a simple MQTT message display (with ESP8266 as additional tools)

## Features:
### Switch input mode

#### Auto mode
    
Shows indicator from generated message, disables "send" switch
        
#### Manual mode
    
Shows indicator from overriding last auto input data, enables "send" switch
        
#### Sensor indicator

Displays sensor value

## Output

Displays indicator to web and ESP8266
  
### Requirements:
1. Python: paho-mqtt
2. Arduino IDE
    - PubSubClient v2.6
    - ESP8266Wifi
    - ArduinoJson v6
    - Adafruit DHT
  
### Where I learn (references used):
- [ArduinoJson (with v6 documentation)](https://arduinojson.org/)
- [Rui Santos: ESP8266 publishing DHT data to Flask Web](https://randomnerdtutorials.com/esp8266-publishing-dht22-readings-with-mqtt-to-raspberry-pi/)
- [EMQX: MQTT publish generator](https://www.emqx.io/blog/how-to-use-mqtt-in-python)
- [Steve's Internet Guide: MQTT Javascript](http://www.steves-internet-guide.com/using-javascript-mqtt-client-websockets/)
