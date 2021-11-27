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
![image](https://user-images.githubusercontent.com/72893623/143669368-18c91485-1d2d-45c2-b644-dabdf9961fcb.png)


## System Block Diagram
![Untitled Diagram drawio (1)](https://user-images.githubusercontent.com/72893623/142475750-f525a755-3b48-42ca-98c0-f31a19548c6d.png)

## Progress
* We were able to bring all hardware components from workshop except for electric strike
* We built the system using cubemx on FreeRtos
* We connected the MCU to the bluetooth using UART
* We developed the logic for unlocking the door in case of the user enetering a right password
* We develooped the logic for  producing an Alert in case of user entering the password wrong for three times

