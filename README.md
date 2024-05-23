# ESP32CAM + Telegram Bot

![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/08/ESP32-CAM-Telegram-Picture.jpg?w=1280&quality=100&strip=all&ssl=1)

## Here you will learn how to use ESP32 with Telegram Bot.

### Here's a summary of the project you'll be building:

    You will develop a Telegram bot for your ESP32-CAM.
    You can initiate a chat with the ESP32-CAM bot.
    Sending the command /photo to the bot will prompt the ESP32-CAM to capture and return a photo.
    Sending the command /flash will toggle the LED flash on the ESP32-CAM.
    Sending the command /start will provide a welcome message and list the available commands.
    The ESP32-CAM will only respond to messages from your specific Telegram account ID.

### This straightforward project demonstrates how to integrate Telegram with your IoT and Home Automation projects. The goal is to help you apply these concepts in your own projects.





![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/08/ESP32-CAM-Take-Send-Photo-Telegram-Project-Overview.jpg?w=867&quality=100&strip=all&ssl=1)


### Firstly clone my repository by using terminal and following code
`git clone https://github.com/your-username/your-repository.git ` 
Or download my repository as ZIP

### You will need also VS Code
+ *Then in VS Code extensions, find Platform IO and download it!*
+ After this, you will see two main files, **"main.cpp**" and **"platform.ini"**
+ Check and click to **"BUILD"** this will run your code and will check for errors, if everything were made right, you wont see any errors.

  
+ You will need some new drivers for working with ESP32 PORTS, you need to download CP210x USB driver or something similar if your device doesnt recognise ESP32 CAM etc, you can find it [here](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads)
+ Go to Settings - Device Manager - Ports and find your port (COMX) where X is number usually 0-9
+ Then in VS code find platform.ini and here write your COM
+ `upload_port = COMX`

## After selecting correct port, we need to create Telegram Bot
### Open Telegram and follow the next steps to create a Telegram Bot. First, search for “botfather” and click the BotFather as shown below. Or open this link t.me/botfather in your smartphone.
![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/06/Telegram-Botfather.png?w=362&quality=100&strip=all&ssl=1)

### After this, you will be given your BOT TOKEN, copy and save it!
![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/06/Bot-Token-Telegram-Bot-Father.png?w=356&quality=100&strip=all&ssl=1)

+ Then we need to know our Telegram account ID, for this, In your Telegram account, search for “IDBot” or open this link t.me/myidbot in your smartphone.
+ ![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/06/Telegram-Get-Chat-ID.png?w=354&quality=100&strip=all&ssl=1)
+ Copy and save your ID we will use it later.
+ Go to VS code and in your project, turn to **" PIO Home"** click "Library" and add 2 library in your project
+ Universal Telegram Bot Library
+ ArduinoJson Library


  ## Finally we just need to configure our code in **main.cpp** file
  
``const char* ssid = "REPLACE_WITH_YOUR_SSID";
const char* password = "REPLACE_WITH_YOUR_PASSWORD";``

+ Here just write your WIFI's name (ssid) and his password, to allow your ESP32 cam connect to Internet and work!

// Initialize Telegram BOT
``String BOTtoken = "XXXXXXXXXX:XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX";  // your Bot Token (Get from Botfather)``

// Use @myidbot to find out the chat ID of an individual or a group
// Also note that you need to click "start" on a bot before it can
// message you
`String CHAT_ID = "XXXXXXXXXX";` //Your Telegram ID


## After uploading the code, press the ESP32-CAM on-board RST button so that it starts running the code. Then, you can open the Serial Monitor to check what’s happening in the background.

Go to your Telegram account and open a conversation with your bot. Send the following commands and see the bot responding:

    /start shows the welcome message with the valid commands;
    /flash inverts the state of the LED flash;
    /photo takes a new photo and sends it to your Telegram account.

  ![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/08/ESP32-CAM-Take-Send-Photo-Telegram.jpg?w=321&quality=100&strip=all&ssl=1)

At the same time, on the Serial Monitor, you should see that the ESP32-CAM is receiving the messages.
![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/08/ESP32-CAM-Telegram-Serial-Monitor.png?w=669&quality=100&strip=all&ssl=1)

If you try to interact with your bot from another account, you’ll get the “Unauthorized user” message.

![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2020/06/Control-ESP32-ESP8266-Outputs-Telegram-Unauthorized-User.png?w=352&quality=100&strip=all&ssl=1)


# In this tutorial, you’ve learned how to send a photo from the ESP32-CAM to your Telegram account. As long as you have access to the internet on your smartphone, you can request a new photo no matter where you are. This is great to monitor your ESP32-CAM from anywhere in the world.
