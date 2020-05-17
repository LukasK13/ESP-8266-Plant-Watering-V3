# ESP-8266 Plant Watering V3
A plant watering system using the ESP-8266 D1 Mini microcontroller and ESPHome / Home Assistant for controlling featuring water flow measurement, a water level sensor and a soil moisture sensor

This repository contains the configuration used for programming the D1 Mini using ESPHome as well as well as the corresponding electric plan and the configuration used for Home Assistant integration. As MQTT is used for communication with Home Assistant, you need to set up a MQTT broker of your choice in advance.

## Major parts
* D1 Mini
* 12V (or something else) water pump [I used this one](https://www.alibaba.com/product-detail/DC-12V-mini-micro-water-pump_60633545565.html)
* Flow meter [I used this one](https://www.digmesa.com/de/product-details/flow-sensor-fhksc/)
* Water proof housing
* 5.0 V and 3.3 V voltage regulator (for example L7805CV and L7833)
* Relais board KY-019 [I used this one](https://www.az-delivery.de/products/relais-modul?_pos=16&_sid=ea41aa481&_ss=r)
* Counter IC CD4040B
* Ultrasonic sensor HC-SR04: [I used this one](https://www.az-delivery.de/products/3er-set-hc-sr04-ultraschallmodule?_pos=2&_sid=ebf8c0ed7&_ss=r)
* Capacitive soil moisture sensor: [I used this one](https://www.ramser-elektro.at/shop/bausaetze-und-platinen/giesomat-kapazitiver-bodenfeuchtesensor-erdfeuchtesensor-mit-beschichtung/)


## Electric Layout
The electric layout is pretty simple for this project.
You can find the electric plan in the following image.
![Electric Plan](Plant_Watering.png?raw=true "Electric Plan")

## Flashing the D1 Mini
An ESPHome installation is required for flashing the D1 Mini. Follow [this](https://esphome.io/guides/getting_started_command_line.html) guide to set things up. In order to integrate the system into your WiFi, you need to rename the file [`secrets_template.yaml`](secrets_template.yaml) to `secrets.yaml` and fill your passwords in. Afterwards just run `esphome plant_watering.yaml run` and you're good to go.

## Home Assistant Integration
In newer Home-Assistant installations, your plant watering system will be automatically detected. If not, you can use the ESPHome-Integration to integrate it into Home-Assistant
