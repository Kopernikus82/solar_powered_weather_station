### what does that do for you ?

It can measure:
- Air temperature
- Air humidity
- Air pressure (atmospharic)
- Particular matter (PM 1,0 / 2,5 / 4,0 / 10,0)
- Ozone
- Ground temperature
- Wind speed (planned)
- Wind direction (planned)
- Rain (planned)
- Sky temperature (degree of cloud cover) (planned)

and is powered up by some small solar panels  (needs no external power supply).
It sends the data every 5minutes via wifi to your MQTT broker.

### What do you need ?

- ESP-32
- Sensirion SPS30 (Paricular matter sensor)
- SHT31 D (Temperature & humidity) [i use a adafruit breakout board]
- DPS 310 (pressure) [i use a adafruit breakout board]
- Ozone Sensor [i use the Gravity: Electrochemical Ozone Sensor (0-10 ppm, I2C)]
- DS18B20 (Ground temperature) [be sure that it is waterproof]
- Some resistors
- Some wires
- A 3D printed casing
- 18650 Li-Ion  + 18650 SHIELD
- Transistor (to disconnect the sensors while the ESP is sleeping)
- Linear voltage regulator 5V output an minium 750mA, Input from 5,5 up to 12V


### How does it work ?

So what does all this do? When the ESP boots up, it loads everything you need as normal, connects WiFi, MQTT and then starts querying all the sensors one after the other. Then it goes to sleep. Before it goes to sleep, a PIN switches off the power supply to the sensors via a transistor. Why does it do that? If it does not do this, the sensors draw a lot of current and operating so many sensors on a battery with solar cells without an external power supply. This means that the ESP is in deep sleep most of the time and only wakes up every 5 minutes to take a brief measurement and then goes back to sleep.

It was important to me that the whole thing works without an external power supply (cable). That's why the sketch and the hardware are designed in such a way that the ESP with the 18650 battery (the one currently in it should have 3200mA) can easily last 2 days without needing to be charged. That wasn't the problem either. The problem was finding and assembling a power supply that could cope with the extreme conditions. In Deepsleep, the thing draws almost no power, so many ad hoc solutions are useless because they think the power consumption is off. Then the ESP no longer comes on. Another problem is that when the particulate matter sensor starts to measure, it draws over 400mA for a short time, which can cause the voltage to drop briefly and the ESP to crash. As you can see, I have tried a few solutions. If anyone has a better, nicer and more elegant solution: PLEASE LET ME KNOW!


### How to build it ?


ON WORK
