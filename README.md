# Sensor to user

---

## Student information

Student's name: Nguyen Thi Ly Linh

Student's code: M22.ICT.003

Email: linhntl.m22ict@usth.edu.vn

Last updated date: 28/04/2023 

---

## 1. Introduction:

- I build a system which is have sensor to get temperature and humidity in the area like small garden in house (around 10 square meter). Data will transfer to mobile device via wifi. Data would be processed and analyzed by application. Which is notify for user to decide to active watering. System also notify for user when the garden too humid, help user decide to turn off watering system
- Effectively collecting and processing data from sensors used to detect humidity in a garden watering system is crucial for several reasons:
    1. Optimal watering: By monitoring the humidity levels in the soil, the watering system can be optimized to ensure that plants receive the appropriate amount of water. Overwatering or underwatering can have negative effects on plant growth and health. By collecting and processing data from humidity sensors, the watering system can be set to automatically water the plants only when necessary, reducing water waste and promoting healthy plant growth.
    2. Resource conservation: Water is a valuable resource, and conserving it is important. By collecting and processing data from humidity sensors, the watering system can be programmed to only water when necessary, reducing water waste and conserving this valuable resource. This is especially important in areas where water is scarce, or during times of drought.
    3. Plant health: Humidity levels in the soil can directly impact plant health. If the soil is too dry, plants may wilt or die. If the soil is too wet, it can lead to root rot and other fungal diseases. By collecting and processing data from humidity sensors, the watering system can be adjusted to maintain optimal soil moisture levels, promoting healthy plant growth and preventing plant diseases.
    4. Convenience: An automated garden watering system that uses humidity sensors can provide convenience for the gardener, as it eliminates the need for manual watering. By collecting and processing data from the sensors, the system can be set to automatically water the plants based on their moisture needs, freeing up time and effort for the gardener.

---

## 2. System Components and Architecture:

- Identify and describe the main components of the smart decision-making system.
    
    ### System Components
    
    1. DHT11 sensor: A digital sensor that can measure temperature and humidity in a small area.
    2. ESP32: A microcontroller that can connect to Wi-Fi and transmit data wirelessly.
    3. Mobile application: An application that can receive and display data from the ESP32.
    4. Power supply: A power source to power the ESP32 and the DHT11 sensor.
    
    ### System Architecture
    
    1. The DHT11 sensor is connected to the ESP32 microcontroller through the digital input/output pins.
    2. The ESP32 is connected to the Wi-Fi network and configured to periodically collect temperature and humidity data from the DHT11 sensor.
    3. The ESP32 uses the Wi-Fi connection to transmit the data wirelessly to the mobile application.
    4. The mobile application receives the data from the ESP32 and displays it to the user in a user-friendly format.
    5. The power supply is connected to the ESP32 and the DHT11 sensor to provide power to the system.
    6. The system is housed in a suitable enclosure to protect it from environmental factors such as moisture and dust.

---

## 3. Implementation details:

- DHT11: Specification

| Conditions | Conditions | Minimum | Typical | Maximum |
| --- | --- | --- | --- | --- |
| Humidity |  |  |  |  |
| Resolution |  | 1%RH | 1%RH | 1%RH |
|  |  |  | 8 Bit |  |
| Repeatability |  |  | ±1%RH |  |
| Accuracy | 25℃ |  | ±4%RH |  |
|  | 0-50℃ |  |  | ±5%RH |
| Interchangeability | Fully Interchangeable |  |  |  |
| Measurement Range | 0℃ | 30%RH |  | 90%RH |
|  | 25℃ | 20%RH |  | 90%RH |
|  | 50℃ | 20%RH |  | 80%RH |
| Response Time (Seconds) | 1/e(63%)25℃，
1m/s Air | 6s | 10s | 15s |
| Hysteresis |  |  | ±1%RH |  |
| Long-Term Stability | Typical |  | ±1%RH/year |  |
| Temperature |  |  |  |  |
| Resolution |  | 1℃ | 1℃ | 1℃ |
|  |  | 8 Bit | 8 Bit | 8 Bit |
| Repeatability |  |  | ±1℃ |  |
| Accuracy |  | ±1℃ |  | ±2℃ |
| Measurement Range |  | 0℃ |  | 50℃ |
| Response Time (Seconds) | 1/e(63%) | 6s |  | 30s |
- Pumps: HM-1206
    - Usage voltage: 12v
    - Usage voltage: 80W.
    - Traffic: 6 l/min.
    - Pressure: 145PSI (10bar).
    - Weigth: 1,2kg
    - Electricity supply: ****[meanwell SD-15A-12](http://meanwell.com.vn/)****
- Electricity supply: Meanwell SD-15A-12
    - Input => A: 9.2~18VDC (12VDC)
    - Performance: 72%
    - Output: 12V, 1.25A, 15W
    - Impulse noise: 120mVp-p
    - Size: 78*51*28 (L*W*H)
    - Weigth: 0.18kg/pc
- ESP32 WROOM:
    
    ESP32: ESP32 WROOM has two processor cores, which allows for more efficient multitasking and better performance. Which has build-in Wi-Fi and Bluetooth modules, which allows it to connect to wireless networks and other devices. has a low power consumption mode, which allows it to operate on battery power for extended periods of time. It has a large amount of memory, including both RAM and flash memory, which allows for more complex applications and data storage. Relatively low cost compared to other microcontrollers with similar capabilities, making it an affordable option for hobbyists and developers.
    
    | Bandwidth | 72 MHz |
    | --- | --- |
    | Data Rate | 150 Mbps |
    | Interface | Ethernet, I2C, I2S, SPI, UART |
    | Max Frequency | 2.484 GHz |
    | Max Operating Temperature | 85 °C |
    | Max Supply Voltage | 3.6 V |
    | Min Operating Temperature | -40 °C |
    | Min Supply Voltage | 3 V |
    | Nominal Supply Current | 500 mA |
    | Number of ADC Channels | 16 |
    | Number of GPIO | 32 |
- Describe the data processing techniques used to make informed decisions based on the collected data.
    1. Filtering: Filtering techniques can be used to remove noise from the data collected by the sensor. Noise can be caused by a variety of factors, such as fluctuations in the electrical signal or environmental factors like wind or vibration. Filtering can help to remove these unwanted variations in the data, making it easier to interpret and analyze.
    2. Averaging: Averaging techniques can be used to calculate the average value of the data collected over a certain period of time. This can help to smooth out fluctuations in the data and provide a more stable representation of the overall trend. For example, if the humidity levels in a garden are fluctuating rapidly throughout the day, averaging the data over a longer period of time (such as several hours) can provide a more accurate representation of the overall humidity level.
    3. Trend analysis: Trend analysis techniques can be used to identify patterns in the data collected over time. This can help to identify trends and correlations that may not be immediately apparent from just looking at the raw data. For example, if the humidity levels in a garden are consistently low during certain times of the day, this could indicate that the plants are not receiving enough water during those times.
- Model: Auto watering system (Image 1)
    - Data collection system
        - ESP collect data of sensor
        - ESP push data via Wi-Fi
    - Application:
        - Pull data were sent from ESP then storage data
        - Processing data was storage to make decision
            - Notify for user
            - Automation active/de-active watering
        - User can active/de-active watering via application
    - Watering system:
        - Watering
        - Close watering
- Working flow (Image 2)

---

## 4. Testing and Validation

- Code on github: How to use. capture template data
    - Code connection of DTH11 vs ESP32, simulate watering job, just need to log data
    

---

## 5. Conclusion

- Advantages
    - The system's ability to optimize watering and conserve resources make it an environmentally-friendly solution for gardeners and farmers alike.
    - The system's use of low-cost and widely available components such as the DHT11 sensor and ESP32 microcontroller make it an affordable option for hobbyists and small-scale applications.
    - The scalability of the system may be limited by the use of a single sensor and the processing power of the microcontroller, which may need to be upgraded for larger-scale implementations.

- Scalability
    The scalability of the system would depend on the specific implementation and the needs of the real-world application. However, one potential limitation of the system's scalability is the use of a single sensor to collect data in a limited area. If the real-world application requires data collection over a larger area or more precise measurements, additional sensors may need to be added or a different sensor with higher accuracy may need to be used. Additionally, the system's scalability may be limited by the processing power of the microcontroller, which may struggle to handle larger amounts of data or more complex decision-making algorithms. Therefore, it may be necessary to upgrade the microcontroller or use a more powerful processing unit to accommodate a larger scale implementation.
    
- Limitations
    - The system can be improved by incorporating more sensors to collect additional data such as light levels and soil pH, which can provide further insight into plant health and growth.
    - Additionally, the system can be further developed to include machine learning algorithms to analyze the data and make more informed decisions about watering schedules and plant care.
    - Another potential improvement would be to incorporate remote access and control capabilities, allowing the user to monitor and adjust the system from anywhere.
