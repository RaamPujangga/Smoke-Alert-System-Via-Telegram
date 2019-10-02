# Smoke Alert System Via Telegram
## Introduction
In this case, this device capabale of detecting smoke, and LPG gas leaks.
At the same time, the device must be able to provide notifications to the user through a smartphone.

This readme describes every step required to get going with the smoke detector:

1. Preparing the materials
2. Preparing Telegram Bot
3. Downloading and Installing the necessary library
4. Downloading and Editing the Scripts
5. Testing

Next time, I will make this tutorial on YouTube

# Steps
##  1. Prepare The Materials
In making this series of the smoke detection device, the following materials are needed:
1. ESP 32
2. MQ-2 Smoke Sensor
3. USB Cable | Input : 100-240V ~ 50/60Hz 0.2 A | Output : 5V 1A
4. Buzzer
5. 6 Female Cables

**Notes : For the USB Cable, I already tried with an unknown brand. Even though the Input and the Ouptut same, when ESP 32 connecting to wifi it didn't work, so I use USB Cable originally from Oppo Smartphone**

For electrical circuits, please follow this picture

![image](https://user-images.githubusercontent.com/48588826/65933716-e143d300-e43c-11e9-928a-820a91e35d56.png)

### 2. Prepare Telegram Bot
The purpose of making this telegram bot is to notify the user, that the system has detected a smoke or LPG gas.
#### 2a. Make Telegram Bot
1. Search for the “@BotFather” telegram bot (he’s the one that’ll assist you with creating and managing your bot)
2. Click on or type **/newbot** to create a new bot.
3. Follow instructions and make a new name for your bot. Although, its screen name can be whatever you like. I have chosen “test” as the screen name and “testfiredetection_bot” as its username.
4. Congratulations! You have created your first bot. You should see a new API token generated for it (for example, in the picture, you can see my newly generated token is 944415410:AAFCIgbTCjs-_ZAEPz4YciCGzg5mX_FFF9M)
5. Now you can search for your newly created bot on telegram
6. For more details, see this tutorial in [picture](https://drive.google.com/file/d/1eR0mJnltrvTEQYJQTUSkXaa4hTjNBKq_/view?usp=sharing)

#### 2b. Get Chat ID
After created Telegram Bot we need to know the **chat id** for sending notifications to the user. Follow this step to get the **chat id**
1. Type anything on the bot and send it
2. Open web browser and type
```
https://api.telegram.org/bot**YourBOTToken**/getUpdates
```
3. In this case, my Bot Token is **944415410:AAFCIgbTCjs-_ZAEPz4YciCGzg5mX_FFF9M**
4. So type 
```
https://api.telegram.org/bot944415410:AAFCIgbTCjs-_ZAEPz4YciCGzg5mX_FFF9M/getUpdates
```
5. If the process didn't work, try again from step 1
6. If you make it, you will see the **id : your id** (for example, in the picture, you can see **my id : 389776309**)
7. For more details, see this tutorial in [picture](https://drive.google.com/file/d/1ga6ddiikhoHDYwLv_vONb1P3ytHlTAO8/view?usp=sharing)


## 3. Download and Install necessary Library
Download and Install the library, by following this step, **Start Arduino > Sketch > Include Library > Add .ZIP Library.** Or you can see this picture below

![image](https://user-images.githubusercontent.com/48588826/65961190-4371f780-e480-11e9-90f0-21b8ca1213d9.png)

Here are the necessary library
1. [Telegram Bot Library](https://github.com/witnessmenow/Universal-Arduino-Telegram-Bot.git)
2. [MQ-2 Library](https://github.com/labay11/MQ-2-sensor-library.git)
3. [ArduinoJson-5.13.5](http://downloads.arduino.cc/libraries/github.com/bblanchon/ArduinoJson-5.13.5.zip)

For the ESP 32, you have to follow installation instructions using Arduino IDE Boards Manager
1. Start Arduino
2. Open File > Preferences
3. Enter ```https://dl.espressif.com/dl/package_esp32_index.json``` into **Additional Board Manager URLs** coloumn, then OK
4. Open Tools > Board:> Boards Manager
5. Search **ESP 32** and install

![image](https://user-images.githubusercontent.com/48588826/65962887-d3657080-e483-11e9-9002-17655a627872.png)

## 4. Download and Editing the scripts
Download the [scripts](scripts) and edit **line 15** with your ssid, and edit **line 16** with your ssid password.
Edit **line 18 & 19**, you have to replace with your BOTtoken & Chat ID.

## 5. Testing
Before you start testing, plese make sure these things:
1. Change the **Boards Manager** to **ESP 32 Dev Module**
2. Change **Upload Speed** to **115200**
3. Match the port, by search it on **Device Manager > Ports (COM & LPT)**

Let's start testing, by following these steps:
1. Click upload and at the same time, **press + hold the BOOT button on ESP 32**, until it finished
2. Open serial monitor, and **press EN button to activate the ESP 32**
3. If you completed all the steps, it will look like the picture below

![image](https://user-images.githubusercontent.com/48588826/65967838-7621ed00-e48c-11e9-8257-326b102e81dd.png)

Hope you make it till the end.

Cheers.
