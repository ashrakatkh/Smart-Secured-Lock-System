# Smart-Secured-Lock-System
## Motivation
Traditional  keys are:
* Easy to lose
* Need to make copies
* Easy to forget them inside house
* Losing them will threaten your security
* Limit access to key owners

## Updated Proposed Solution
Smart secured Lock system with:
* bluetooth connection for user to enetr password using mobile 
* Motion sensor to open lamp
* buzzer to produce an alert sound in case of wrong password for three times
* camera to send a photo in case of wrong password for three times 

## Software Components:
![sw_components](https://user-images.githubusercontent.com/79912650/144701500-cd07eb85-9777-4510-a015-72ce3d1c522b.png)

## Hardware Components:
![image](https://user-images.githubusercontent.com/72893623/143673083-8263de9f-b8ff-45a2-8655-3f077c83531c.png)

1.	STM32l432kc

![image](https://www.st.com/bin/ecommerce/api/image.PF263436.en.feature-description-include-personalized-no-cpn-large.jpg)

   a. STM32l432kc is the microcontroller used in Smart-Secured-Lock-System
 
   b.	It is an ARM cortex M4 based processor that is used to get the data from the sensors, such as PIR, process it and control the actuators, such as the relay, based on the          given data.
2.	ESP32-CAM Development Board

![esp32_cam](https://user-images.githubusercontent.com/60285497/144701594-a0dca91d-e736-4b81-b18b-a47df962c27c.jpg)


   a.	ESP32-CAM is used in different functionalities of the system. It contains the camera, OV260 camera module, that is used for capturing the image of the intruder. It              contains a Bluetooth module to read the password from the user and a Wi-Fi module that will be used to send the image of the intruder over the internet to the webserver. 
  
   b.	When the password is entered incorrectly for three times the microcontroller will set a GPIO pin high that is connected to a GPIO pin in the ESP32-CAM. If this pin is            high, then an image will be taken and sent to the web server. 
3.	PIR motion detection sensor 

![download](https://user-images.githubusercontent.com/60285497/144701620-39ae68fd-cf77-4aa1-aa0f-635919dfb6a4.jpg)


   a.	PIR sensor is used to detect the exitance of someone in front of the door which is the triggering event for the system. The PIR sensor wase chosen over other occupancy          sensors because it uses the infrared radiation related to emitted heat to get the difference between background heat and heat emitted by moving object. This way of              sensing eliminates unnecessary triggering of the system by any moving object and triggers it when a human shows up in front of the door.
  
   b.	The sensor senses the existence of a human then it sets its digital output high for a specific duration then it drives it low again 
   
   c.	The rang within which the sensor detects human activities can be adjusted. It ranges from 3 meters to 7 meters. 
   
   d.	At this phase we left the mode and the sensitivity rage as default.
4.	USB-to-TTL Module

![41LgYDO6bmL _AC_UL210_SR210,210_](https://user-images.githubusercontent.com/60285497/144702082-5b2308a6-3e94-4251-8310-a55d1c036465.jpg)

   a.	This module is used to communicate with the ESP32-CAM module during programing and debugging. 

5.	LED

![1200px-LEDs](https://user-images.githubusercontent.com/60285497/144701941-4b85bbec-9ad0-45e9-b623-e7a1c79f6231.jpg)

   a.	LEDs are used as a visual alert to inform the resident about the existence of an intruder.
6.	MP3 Mini Player

![kit_m87_mp3](https://user-images.githubusercontent.com/60285497/144701956-6f018099-d409-4bea-b128-e4d4a7d4a4f0.jpg)

   a.	MP3 Mini Player is used to play a recorded message that guide the user and if there is an intruder it alerts the residents.
7.	Relay

 ![kit_1relay_fares](https://user-images.githubusercontent.com/60285497/144701973-89608930-9884-48ff-916d-6daea87c7e03.jpg)

   a.	A relay module is used to control the 12v electric strike by receiving signal from microcontroller. 
8.	Speaker:

![SP](https://user-images.githubusercontent.com/60285497/144701982-5dfc3c32-8351-4595-962f-dc3ae2c6a48f.jpg)
 
   a.	A speaker is used to clearly play the sound generated from the MP3 Mini Player

## System Block Diagram
![Embedded_project](https://user-images.githubusercontent.com/79912650/143672655-c7f22813-642c-4c53-a92b-fae39fb25447.png)

## Progress I:
* We were able to bring all hardware components from workshop except for electric strike
* We built the system using cubemx on FreeRtos
* We connected the MCU to the bluetooth using UART
* We developed the logic for unlocking the door in case of the user enetering a right password
* We developed the logic for  producing an Alert in case of user entering the password wrong for three times
* Progress I video Link: https://drive.google.com/file/d/1lyq_JVk-_vPWQCBuOJyWCBBWV3k5FAVf/view?usp=sharing

## Progress II:

### Motion Sensor PIR 
* Understand Motion sensor and how it works
* Test motion sensor 
* Connect motion sensor with our circuit 
* Connect the led to the output of the motion sensor, so it lights when someone comes 

### ESP32 Cam
* Understand how camera works
* Download arduino IDE and use it to program camera and to have  web server connection
* Connect camera with mcu
* Program Camera to take photo when GPIO4 is high and connect GPIO4 to mcu GPIO output A5 which is high when the password is entered wrong for three consecutive times


## Components Usage Refrence:


### PIR Sensor
*Hardware:*
![pir](https://user-images.githubusercontent.com/72893623/144701244-761ec933-ca68-4a69-a43a-fc79aee4be14.jpeg)
* The PIR has 3 pins: the vdd, the GND and the output
* To enable PIR, we connect its vdd to 5v output of MCU, its GND pin to the GND pin of MCU and its output to MCU input pin PB0 and led
* The led is connected to 100 ohm resistor to reduce current to avoid its burning


### ESP32 Cam
*Hardware:*
![ESP32-CAM](https://user-images.githubusercontent.com/79912650/144700021-ad580082-ea06-44ee-b5a6-f8d23cd11f59.png)
* To program the ESP32 camera, we used Arduino IDE and we uploaded the code to it using the USB-TTL module which is connected to the PC. 
* The 3.3V pin in ESP32 is connected to the vdd of the USB-TTL and gnd is connected to gnd while GPIO 3 (RX) is connected to TX and GPIO 1 (TX) is connected to RX. 
Note: while uploading the chip, GPIO 0 must be connected to ground.
* After uploading the code on the ESP32 module, The wire connecting GPIO 0 to gnd is removed and the restart button is pressed
* Note: There are different models for the ESP32 cam, the one we are using is the AI thinker

*Software:*
* For the software, to connect the ESP32 to wifi you will need to download two libraries and add them to the Arduino IDE: ESPAsyncWebServer which requires AsyncTCP
* You will need to have an HTML code for the webpage you want to display.
* You can use  Arduino IDE Serial Monitor to make the IP address appear on it after pressing the reset button.


## Demo
### Circuit: 
![cirrcuit](https://user-images.githubusercontent.com/72893623/144700974-b3fc6eb1-14aa-4cde-aaba-31d21f1f79ae.jpeg)

video link:https://drive.google.com/file/d/1MOrTH0CufxyeCBV7rKbK48qbX1alhv68/view?usp=sharing

## Timeline:
![timeline](https://user-images.githubusercontent.com/79912650/144701475-2e2e0939-c0b8-454d-a3e0-8abb63f451fd.png)
