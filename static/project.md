
# Project Start

I had some fun and also some frustrations along the way with this project-starting very simple with the breadboard, I realized that a single breadboard, at least the ones I was used to working with, was not wide enough so I had to connect a pair of them together and have the ESP straddle the both of them in order to gain access to both sides of the ESP32 pin headers for breadboard wiring:

![starting out](images/breadboard-beginnings.jpg)

# Adopt/Install/or otherwise... Get Your ESP into ESPHome

Now that my ESP32 had pins and wasn't dangling on the end of a hanging USB cable, I did the install of the code, this isn't too dificult and there are many guides and several ways to do this using ESPHome either inside HA as an add-on, or by installing the tools on your PC. You may need to install a com port driver which is available on the esphome.io website my pc alread had these drivers as I had used some other random USB-COM port device and many of them share the same chipset.

# Connecting sensors...

The first connections I made were for the BME280 (Press/Humid/Temp) sensor which wasn't too hard, basically you chose pins on the ESP32 for the I2C bus, one being clock and other data (on the BME280 side it's SCK and SD1) and then wire it up! sounds easy right??? I realized the code sample I used wasn't for the BME280 but Rather some other environment sensor that looks similar but operates on another address but after a little bit I figured this out and my sensor started to come alive!

![first connections](images/first%20connections.jpg)

The order of my progress was very much determined by the United States Postal Service ;) so next I added in the mmWave and the PIR dome. The mmWave wasn't too hard, I soldered the header onto the mmWave and popped it onto the breadboard... why not stacked you might asked? that would make sense right?? after all the mmWave header pins align perfectly with the ESP32 (Wemos D1 mini) pins... well, again, these components arrived over time and I didn't think about the end results so I had already soldered the headers onto the ESP32 "wrong" for stacking... besides, as a breadboard project, it looks cooler this way right!?

Note: The pins for the PIR and mmWave are commented in the full config yaml file in this repo. Basically for the mmWave you need only the pull-down pin and power to see the sensor "work" but you'll definitely want the UART rx/tx connections for all the settings you can manage. These sensors come set to full power and will passthrough and detect movement on the other side of walls or in small spaces, the radar waves reflect or bounce around and you will see a lot of false positives unless you have the UART connection and can turn down the range. I haven't not personally changed the sensitivity on any of the units I have now though there is that option too. Also with the UART connections complete, you can turn off the annoying little red LED on the face of the mmWave sensor, you must first turn it on, then wait, then turn it off.
 
![Adding the mmWave and PIR](images/adding%20the%20mmwave%20and%20pir.jpg)

Once my BH1750 (illuminance) sensor arrived I found a spot for it on the now very busy looking breadboard and wired it up. Since I2C is a parallel bus, at least that's what I call it, the pins are just joined together with the BME280. On the BH1750 those pins are SCL (clock) and SDA (data) and the code I found already had the correct I2C address and descriptor for the BH1750 so it came right up :)

![Finished Prototype](images/finished%20prototype.jpg)


# Using your sensors built-in website for initial testing

Unless disabled, the ESP modules have a built-in webserver which is quite handy even without Home Assistant or ESPHome add-on to be able to diagnose or fine tune the settings:

Just open up a browser and pop in the ip of your device

http://your-sensor-ip

It should look something like this:

![Finished Prototype](images/esp32-webserver.png)


# Adding to Home Assistant

This is actually pretty straight forward. In Home Assistant, go to settings>devices and click add integration and search for esphome. You can enter the ip of the unit here and click submit, and you'll be prompted for the encryption key along with a location selector. That's about it. You'll see it listed in devices on the ESPHome card and also you'll then be able to see the device and all entities and use the states for automations or add to the dashboard.





# Building this all into an electronics project box!


I had some fun and also some frustrations along the way with this project-starting very simple with the breadboard, I realized that a single breadboard, at least the ones I was used to working with, was not wide enough so I had to connect a pair of them together and have the ESP straddle the both of them in order to gain access to both sides of the ESP32 pin headers for breadboard wiring:

![starting out](images/breadboard-beginnings.jpg)

The first connections I made were for the BME280 (Press/Humid/Temp) sensor which wasn't too hard, basically you chose pins on the ESP32 for the I2C bus, one being clock and other data (on the BME280 side it's SCK and SD1) and then wire it up! sounds easy right??? I realized the code sample I used wasn't for the BME280 but Rather some other environment sensor that looks similar but operates on another address but after a little bit I figured this out and my sensor started to come alive!

![first connections](images/first%20connections.jpg)

