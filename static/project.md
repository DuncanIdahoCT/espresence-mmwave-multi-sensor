
# Hardware Overview


I had some fun and also some frustrations along the way with this project-starting very simple with the breadboard, I realized that a single breadboard, at least the ones I was used to working with, was not wide enough so I had to connect a pair of them together and have the ESP straddle the both of them in order to gain access to both sides of the ESP32 pin headers for breadboard wiring:

![starting out](images/breadboard-beginnings.jpg)

The first connections I made were for the BME280 (Press/Humid/Temp) sensor which wasn't too hard, basically you chose pins on the ESP32 for the I2C bus, one being clock and other data and then wire it up! sounds easy right??? I realized the code sample I used wasn't for the BME280 but Rather some other environment sensor that looks similar but operates on another address but after a little bit I figured this out and my sensor started to come alive!

![starting out](images/first_connections.jpg)
