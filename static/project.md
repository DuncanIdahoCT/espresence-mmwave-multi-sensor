
# Hardware Overview


I had some fun and also some frustrations along the way with this project-starting very simple with the breadboard, I realized that a single breadboard, at least the ones I was used to working with, was not wide enough so I had to connect a pair of them together and have the ESP straddle the both of them in order to gain access to both sides of the ESP32 pin headers for breadboard wiring:

![starting out](images/breadboard-beginnings.jpg)

The first connections I made were for the BME280 (Press/Humid/Temp) sensor which wasn't too hard, basically you chose pins on the ESP32 for the I2C bus, one being clock and other data (on the BME280 side it's SCK and SD1) and then wire it up! sounds easy right??? I realized the code sample I used wasn't for the BME280 but Rather some other environment sensor that looks similar but operates on another address but after a little bit I figured this out and my sensor started to come alive!

![first connections](images/first%20connections.jpg)

The order of my progress was very much determined by the United States Postal Service ;) so next I added in the mmWave and the PIR dome. The mmWave wasn't too hard, I soldered the header onto the mmWave and popped it onto the breadboard... why not stacked you might asked? that would make sense right?? after all the mmWave header pins align perfectly with the ESP32 (Wemos D1 mini) pins... well, again, these components arrived over time and I didn't think about the end results so I had already soldered the headers onto the ESP32 "wrong" for stacking... besides, as a breadboard project, it looks cooler this way right!?

Note: The pins for the PIR and mmWave are commented in the full config yaml file in this repo. Basically for the mmWave you need only the pull-down pin and power to see the sensor "work" but you'll definitely want the UART rx/tx connections for all the settings you can manage. These sensors come set to full power and will passthrough and detect movement on the other side of walls or in small spaces, the radar waves reflect or bounce around and you will see a lot of false positives unless you have the UART connection and can turn down the range. I haven't not personally changed the sensitivity on any of the units I have now though there is that option too.
 
![Adding the mmWave and PIR](images/adding%20the%20mmwave%20and%20pir.jpg)

