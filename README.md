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
![Embedded_project](https://user-images.githubusercontent.com/79912650/143672655-c7f22813-642c-4c53-a92b-fae39fb25447.png)

## Progress
* We were able to bring all hardware components from workshop except for electric strike
* We built the system using cubemx on FreeRtos
* We connected the MCU to the bluetooth using UART
* We developed the logic for unlocking the door in case of the user enetering a right password
* We develooped the logic for  producing an Alert in case of user entering the password wrong for three times

