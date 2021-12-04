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


## Hardware Components:
![image](https://user-images.githubusercontent.com/72893623/143673083-8263de9f-b8ff-45a2-8655-3f077c83531c.png)
 

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

## Components Usage Refrence:
### PIR Sensor

### ESP32 Cam
*Hardware:*
![ESP32-CAM](https://user-images.githubusercontent.com/79912650/144700021-ad580082-ea06-44ee-b5a6-f8d23cd11f59.png)
* To program the ESP32 camera, we used Arduino IDE and we uploaded the code to it using the USB-TTL module which is connected to the PC. 
* The 3.3V pin in ESP32 is connected to the vdd of the USB-TTL and gnd is connected to gnd while GPIO 3 (RX) is connected to TX and GPIO 1 (TX) is connected to RX. 
Note: while uploading the chip, GPIO 0 must be connected to ground.
* After uploading the code on the ESP32 module, The wire connecting GPIO 0 to gnd is removed and the restart button is pressed

*Software:*
* Arduino IDE
* HTML code 

## Timeline:
![WhatsApp Image 2021-11-27 at 9 40 29 AM](https://user-images.githubusercontent.com/79912650/143672870-61a3287c-9d7d-415c-80f5-151356e83c21.jpeg)

## Demo
video link: https://drive.google.com/file/d/1MOrTH0CufxyeCBV7rKbK48qbX1alhv68/view?usp=sharing


