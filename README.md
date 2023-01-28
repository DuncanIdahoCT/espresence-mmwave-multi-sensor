# espresence-mmwave-multi-sensor
My DIY project to build a multi sensor based on the EP1

![mmWave + PIR - Multi-Sensor](static/images/espresence-mmwave-multi-sensor.jpg)

Just like the Everything Presence One, my DIY version has an mmWave sensor, a PIR motion sensor, light illuminance, and a combo temperature/humidity sensor. Similarly it's added into Home Assistant by using the ESPHome add-on.

### Installation:
 * Download these files and copy them (keeping their subfolder paths) into your Home Assistant config/esphome main folder:
   
   header/leapmmw_sensor.h / packages/leapmmw_sensor.yml
  
 * In the ESPHome add-on, click new device and opt to continue, give your new project a name
   ```
   substitutions:
     device_name: leapmmw
 
     # This will vary based on your board
     uart_tx_pin: TX
     
     # This will vary based on your board
     uart_rx_pin: RX
     
     # This will vary based on your board
     gpio_pin: D0
     
     # (Optional) Path to the leapmmw_sensor.h file relative to your esphome configuration directory.
     # header_file: leapmmw_sensor.h
   
   packages:
     remote_package:
       url: https://github.com/hjmcnew/esphome-hs2xx3a-custom-component
       ref: release
       files: [packages/uart.yml, packages/leapmmw_sensor.yml]
       # For additional debugging replace the above line with:
       # files: [packages/uart_debug.yml, packages/leapmmw_sensor.yml]
   ```
