# #5 MCU, Sensors, and Digital Communication Interface Selection

## 1. Purpose
The purpose of this document is to define the selected MCU, sensors, and digital communication interfaces, the selection of each part will be carried out using selection matrices.

## 2. Sensors and components final list
| Component ID | Description |
|---------|-------------|
|MCU- 01| Main processor for the Instrumentation System |
|BULK- 01| Sensor located in the bulkhead for measuring its deformation in different points |
|AIRFRAME- 01| Sensor located in the airframe of the vehicle for measuring its deformation on different axes |
|AIRFRAME- 02| Sensor located in the airframe of the vehicle for measuring its loads on different axes |
|TEMP- 01| Sensor located in the avionics bay for measuring the temperature of the onboard cameras and computers |
|MIC- 01| Sensor located in the avionics bay for recording the sounds inside the vehicle |
|ALT- 01| Sensor for measuring the ambient pressure and altitude |
|IMU- 01| Gyroscope and Accelerometer for measuring vehicle's attitude, acceleration and velocity |
|FLASH- 01| non-volatile memory for storing data during flight |
|SD-01| Memory for storing data after landing |

## 3. MCU selection
| ISAQ        |                      | Clock Frequency [MHz] | Flash [KB] | SRAM [KB] | GPIO Quantity [-]| Cost [COP] | Final score|
|-------------|----------------------|-----------------------|------------|-----------|------------------|-------------|-----------|
|             | **Operation**        | Maximize              | Maximize   | Maximize  | Maximize         | Minimize    | N/A       |
|             | **Percentage (%)**   | 10                    | 35         | 10        | 10               | 35          | N/A       |
| **Options** | **ESP32-S3-DevKitC-1**   | **240**                   | **16000**      | **512**       | **33**               | **52000**       | **61.8**      |
|             | Arduino Nano         | 16                    | 32         | 2         | 22               | 17374       | 39.4      |
|             | Teensy 4.1           | 600                   | 8000       | 1000      | 55               | 260253      | 49.8      |
|             | ESP8266              | 160                   | 4000       | 160       | 17               | 20000       | 46.5      |
|             | Arduino Pro Micro    | 16                    | 32         | 2         | 16               | 26775       | 26.0      |

The selected MCU is the ESP32-S3-DevKitC-1, this chip has great clock frequency and specifications for this flight, also it has been flight proven by different teams on the IREC competition.

## 4. BULK-01 selection
The selected Bulkhead sensor for measuring the deformation is a Flex Sensor, BF350-3AA model, this model has a sensibility factor of 2 and a deformation limit of 2%, a resistance of 350 ohms and its dimmensions ares 5x4.5mm, this sensor is good for measuring small changes that the ones that will be experienced on the bulkhead.

## 5. AIRFRAME-01 selection
The selected sensor for measuring the deformation in the airframe is a Flex Sensor, BF350-3AA model, this model has a sensibility factor of 2 and a deformation limit of 2%, a resistance of 350 ohms and its dimmensions ares 5x4.5mm, this sensor is good for measuring small changes that the ones that will be experienced on the airframe.

## 6. AIRFRAME-02 selection
Based on Team 162 Project Technical Report IREC 2025, the accelerations expected with a range of 15% are the next ones:

Axial Acceleration: 115 m/s² (11.72 g)

Lateral Acceleration: 27.1 m/s²   (2.76 g)

| ISAQ        |                      | ADC [bit] | Interface Speed [MHz] | g-range [g]  | Acceleration accuracy [g]| Cost [COP] | Final score|
|-------------|----------------------|-----------|-----------------------|--------------|----------------------------|-------------|---------------|
|             | **Operation**        | Maximize  | Maximize              | Maximize     | Minimize                   | Minimize    | N/A           |
|             | **Percentage (%)**   | 10        | 10                    | 10           | 25                         | 45          | N/A           |
| **Options** | LSM6DS3          | 16    | 0.4               |16        | 0.02                  | 24000   | 63.9      |
|             | **MPU6050**              | **16**        | **0.4**        | **16**           | **0.05**                       | **15000**       |  **65.8**         |
|             | LIS331HH             | 16        | 10                    | 24           | 0.07                       | 40000       |  44.6         |
|             | H3LIS331DL           | 16        | 10                    | 400          | 1                          | 64000       |  41.0         |

The selected accelerometer is the MPU6050.

## 7. TEMP-01 selection
| ISAQ        |                      | ADC [bit] | Temperautre Accuracy [°C]  | Maximum Temperature [°C]  | Cost [COP]  | Final score   |
|-------------|----------------------|-----------|----------------------------|---------------------------|-------------|---------------|
|             | **Operation**        | Maximize  | Minimize                   | Maximize                  | Minimize    | N/A           |
|             | **Percentage (%)**   | 25        | 30                         | 15                        | 30          | N/A           |
| **Options** | DS18B20              | 12        | 0.5                        | 125                       | 10000       | 40.0          |
|             | TMP117               | 16        | 0.2                        | 150                       | 50000       | 70.0          |
|             | **ADT7410**          | **16**        | **0.4**                        | **150**                       | **22000**       | **71.0**          |
|             | DHT22                | 16        | 0.5                        | 80                        | 10000       | 0.55          |

The selected temperature sensor is the ADT7410, in this case, since there are 4 units of this sensor in the launch vehicle, priority was given not only to accuracy but also to the cost of the sensor, so that it could have high accuracy for a relatively low price. .

## 8. MIC-01 selection
| ISAQ        |                      | ADC [bit] | Signal-to-Noise Ratio [dB] | Total Harmonic Distortion [%]   | Cost [COP]  | Final score   |
|-------------|----------------------|-----------|----------------------------|---------------------------------|-------------|---------------|
|             | **Operation**        | Maximize  | Maximize                   | Minimize                        | Minimize    | N/A           |
|             | **Percentage (%)**   | 25        | 35                         | 25                              | 15          | N/A           |
| **Options** | **MAX4466**          | **10**        | **112**                        | **0.02**                          | **12000**       | **100**           |
|             | MAX9814              | 10        | 61                         | 0.04                            | 17000       | 67.2          |
The selected microphone is the MAX4466.

## 9. ALT-01 selection

| ISAQ        |                 | ADC [bit] | Interface Speed [MHz] | Minimum barometric pressure [hPa] | Relative Pressure Accuracy [hPa]| Cost [COP] | Final score|
|-------------|----------------------|-----------|-----------------------|-----------------------------------|------------------------|-------------|---------------|
|             | **Operation**        | Maximize  | Maximize              | Minimize                          | Minimize               | Minimize    | N/A           |
|             | **Percentage (%)**   | 10        | 15                    | 25                                | 40                     | 10          | N/A           |
| **Options** | BMP180               | 19        | 3.4                   | 300                               | 0.12                   | 5000        | 48.0          |
|             | BMP280               | 20        | 10                    | 300                               | 0.12                   | 10000       | 48.3          |
|             | BMP388               | 24        | 10                    | 300                               | 0.08                   | 40000       | 59.6          |
|             | **MS5611**           | **24**    | **20**                | **10**                            | **0.1**                | **28400**   | **83.8**      |
|             | MS5607               | 24        | 20                    | 10                                | 0.1                    | 32900       | 83.5          |

The selected pressure sensor is the MS5611. This sensor is an updated version of the MS5607, and the MS56 series has demonstrated highly accurate performance in high-risk flight applications. These sensors have been successfully used in flight computers such as EasyMini, TeleMetrum, and TeleMega from AltusMetrum, as well as AVA from BPS.SPACE.

## 10. IMU-01 selection

| ISAQ        |                      | ADC [bit] | Interface Speed [MHz] | g-range [g]  | gyro range [dps]| Cost [COP] | Final score|
|-------------|----------------------|-----------|-----------------------|--------------|-----------------|-------------|---------------|
|             | **Operation**        | Maximize  | Maximize              | Maximize     | Maximize        | Minimize    | N/A           |
|             | **Percentage (%)**   | 10        | 15                    | 30           | 30              | 15          | N/A           |
| **Options** | LSM6DS               | 16        | 10                    | 16           | 2000            | 24000       | 74.6          |
|             | MPU6050              | 16        | 0.4                   | 16           | 2000            | 15000       | 67.0          |
|             | ICM-20602            | 16        | 8                     | 16           | 2000            | 68000       | 70.0          |
|             | ICM-20649            | **16**        |**7**                   | **30**           | **4000**            | **55000**       | **85.8**          |
|             | BMI270               | 16        | 10                    | 16           | 2000            | 68000       | 70.7          |
|             | BNO055               | 16        | 0.4                   | 16           | 2000            | 64000       | 64.7          |
|             | MPU9250              | 16        | 20                    | 16           | 2000            | 37000       | 79.0          |

The selected pressure sensor is the ICM-20649. This sensor has the capacity to withstand up to 30g, exceeding the 16g limit of most IMUs; this greater range is necessary due to supersonic flight.

## 11. FLASH-01 selection
| ISAQ        |                      | Capacity [MB] | Writing Cycles [-]   | Interface Speed [MHZ]  | Cost [COP] | Final score|
|-------------|----------------------|---------------|----------------------|------------------------|------------|------------|
|             | **Operation**        | Maximize      | Maximize             | Maximize               | Minimize        | N/A        |
|             | **Percentage (%)**   | 35            | 20                   | 25                     | 20              | N/A        |
| **Options** | W25Q32JV             | 4             | 100000               | 133                    | 15000           | 67.2       |
|             | W25Q64               | 8             | 100000               | 104                    | 16000           | 66.5       |
|             | W25Q128              | **16**           | **100000**               | **133**                    | **20000**           | **90.8**       |
|             | AT24C256             | 0.032         | 100000               | 1                      | 5800            | 40.3       |

The selected Flash card is the W25Q128. This Flash card has high Interfac Speed and high capacity for storaging flight data.

## 12. SD-01 selection
A Micro SD adapter module without a level converter will be used to avoid SPI bus issues. This is because, according to various forum posts found on the official Arduino website, Micro SD modules with level converters have been shown to block the SPI bus, allowing only the Micro SD module to function and preventing any other peripherals from working.

Additionally, a 16GB Micro SD card will be used to store a file containing all the mission flight data and microphone recordings.

## 13. Communication Protocols
| Sensor ID    | Selected Sensor | Communication Protocol | Comments |
|--------------|-----------------|------------------------|----------|
| BULK- 01     | BF350-3AA       | Analog Communication   |          |
| AIRFRAME- 01 | BF350-3AA       | Analog Communication   |          |
| AIRFRAME- 02 | MPU6050         | I2C     |There will be only 2 accelerometers in this case, because the I2C bus for the MPU6050 can only afford two I2C addresses |
| TEMP- 01     | ADT7410         | I2C                    |          |
| MIC- 01      | MAX4466         | Analog Communication   |          |
| ALT- 01      | MS5611          | SPI                    |The sensor can work both SPI or I2C, but for faster communication it uses SPI|
| IMU- 01      | ICM-20649       | SPI                    |The sensor can work both SPI or I2C, but for faster communication it uses SPI|
| FLASH- 01    | W25Q128         | SPI                    |          |
| SD- 01       | MicroSD Adapter | SPI                    |          |

## 14. PRELIMINARY PIN DISTRIBUTION
| PIN    | Function |
|--------|----------|
| GPIO11 | SPI MOSI |
| GPIO12 | SPI SCK  |
| GPIO13 | SPI MISO |
| GPIO4  | SD-01 CS |
| GPIO5  | FLASH-01 CS |
| GPIO6  | ALT-01 CS |
| GPIO7  | IMU-01 CS |
| GPIO8  | SDA |
| GPIO9  | SCL |
| GPIO16 | MIC-01 |
| GPIO17   | AIRFRAME-01|
| GPIO18   | BULK-01 |