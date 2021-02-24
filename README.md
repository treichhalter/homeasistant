# Installation
## Home Assistatn online
1. [Online documentation](https://www.home-assistant.io/installation/raspberrypi)
2. [Onboarding](https://www.home-assistant.io/getting-started/onboarding/)
3. Acivate Advance Mode
    - User (you name) left bottom
    - Enable Advance Mode
4. [Home Assistant Add-on: File editor](https://github.com/home-assistant/addons/blob/master/configurator/README.md)
# Configuration
## MQTT Broker 
[Home Assistant Add-on: Mosquitto borker](https://github.com/home-assistant/addons/blob/master/mosquitto/DOCS.md)
1. Install add-on
2. Creat User (Advance Mode enabled) for mqtt
## MQTT for Home Assistant

In HA got to:
- Configuraiton, Integrations and add [MQTT](https://www.home-assistant.io/integrations/mqtt/)
- Configure
- MQTT Settings:
    - Broker address 
        - in my case MQTT runs as HA Add-on (see above)
        - so I use localhost ip 127.0.0.1 or name localhost (both tested)
    - Username createt in MQTT Broker
    - Password the same
- Test connection with listing on topic

/config/configuration.yaml
```yaml
mqtt:
  broker: mqtt://homeassistant.local/

sensor:
  - platform: mqtt
    name: "Fredy earth moisture"
    state_topic: "sensor/moisture"
    unit_of_measurement: "%"
```