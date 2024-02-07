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
- Linear voltage regulator


### How to build it
