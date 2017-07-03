# BrewBench Monitor

http://monitor.brewbench.co

<img src="src/assets/img/brewbench-logo-265.png?raw=true" alt="BrewBench logo" title="BrewBench" align="right" />

[![Stories in Ready](https://badge.waffle.io/BrewBench/web-controller.png?label=ready&title=Ready)](https://waffle.io/BrewBench/web-controller)
![codeship](https://codeship.com/projects/8b6f3bc0-b4fd-0134-65d1-5ed8b845772e/status?branch=master)

BrewBench is an Arduino brew monitor, controller and alert system for the home brewer enthusiast.  It uses the Arduino REST API to interface with temp sensors.

#### RIMS
You can also connect a relay to the digital ports and add a heater / pump to create a RIMS system.  The software will start/stop the heater/pump based on the target temperature you set.

#### Fermenter
BrewBench Monitor can also be used with fermenters.  I have an [SS Brewtech Chronical](https://www.ssbrewtech.com/collections/chronicals) that I thread the thermistor into the temperature [thermowell](https://www.ssbrewtech.com/collections/accessories/products/weldless-thermowell-with-lcd-temp-display) along with the digital one provided.

## Setup the Arduino

* Wire up a temp Sensors (Three options)
  * [Thermistors](https://learn.adafruit.com/thermistor/using-a-thermistor) (Analog)
  * [PT100](https://www.adafruit.com/product/3290) (Analog)
  * [DS18B20](https://www.adafruit.com/product/381) (Digital)
    * Will need the [cactus](http://static.cactus.io/downloads/library/ds18b20/cactus_io_DS18B20.zip) library
* Wire up a relay for heat and pump controls
  * Digital ports [Sainsmart 2 channel relay](http://www.sainsmart.com/arduino-pro-mini.html)
    * Arduino GND -> Relay GND
    * Arduino 5V -> Relay VCC
    * Arduino Vin -> Relay JD-VCC (no jumper needed)
    * Arduino Digital (D2) Port -> Relay IN1 (heater)
    * Arduino Digital (D4) Port -> Relay IN2 (pump)

## Arduino Board Options

1. Power up and connect to the default IP http://192.168.240.1
1. Set the digital pin or analog pin depending on which temp sensor you're using.
1. Press play, you can adjust the temp by sliding the temp knob.

### Yun Arduino.cc setup
  * If the WiFi network starts with Arduino use password: arduino
  * Set REST API access to openÂ
  * Change or remember the host name or IP address (you will need this later)
  * Save to reboot
  * Using the [Arduino IDE](https://www.arduino.cc/en/Main/Software) upload the [BrewBenchYun sketch](arduino/BrewBenchYun/BrewBenchYun.ino)

### Yun Arduino.org (aka. Linino) setup
  * If the WiFi network starts with Linino use password: doghunter
  * Set REST API access to open
  * Change or remember the board name or IP address (you will need this later)
  * Save to reboot
  * Using the [Arduino IDE](https://www.arduino.cc/en/Main/Software) upload the [BrewBenchYunLinino sketch](arduino/BrewBenchYunLinino/BrewBenchYunLinino.ino)

### Uno WiFi Arduino.cc setup
  * If the WiFi network starts with Arduino use password: arduino
  * Set REST API access to open
  * Change or remember the host name or IP address (you will need this later)
  * Save to restart
  * Using the [Arduino IDE](https://www.arduino.cc/en/Main/Software) upload the [BrewBenchUnoWiFi sketch](arduino/BrewBenchUnoWiFi/BrewBenchUnoWiFi.ino)

## Open BrewBench

Go to [brewbench.co](http://brewbench.co) or clone this repo and run gulp [http://127.0.0.1:8080](http://127.0.0.1:8080).

## Development

```sh
npm install -g yarn
yarn
gulp
```

## Deployment

Code is compiled to a `build` directory, build the code and copy that to your web server.

```sh
npm install -g yarn
yarn
yarn run build
```

<img src="src/assets/img/screenshot-fermenter.png?raw=true" alt="BrewBench fermenter" align="center" width="400" />

<img src="src/assets/img/screenshot-desktop.png?raw=true" alt="BrewBench screenshot" align="center" />

<img src="src/assets/img/brewbench-wiredup.jpg?raw=true" alt="BrewBench wired up" align="center" />

## Thanks

* For the Lovibond Hex colors: http://brookstonbeerbulletin.com/thinking-about-beer-color
* For the SVG icons:
  * https://thenounproject.com/dejv
  * https://thenounproject.com/creativestall
* For the Hop and Grain reference: https://byo.com
* For the recipes: http://beersmithrecipes.com
* For the bell sounds: http://www.orangefreesounds.com/category/sound-effects/bell-sound

## About

[BrewBench](//brewbench.co) is a brew monitor and controller Developed by [Andrew Van Tassel](https://www.andrewvantassel.com) and [Lee Kendrick](http://www.leekendrick.info) &copy;2017.

Made with <img src="src/assets/img/beer.png" width="45"> from Colorado
