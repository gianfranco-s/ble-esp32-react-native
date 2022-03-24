# Connect ESP32 to Android

Based on this repo: https://github.com/palmmaximilian/ReactNativeArduinoBLE

Original project ran on Windows. I couldn't make it work on Ubuntu 20.04, so I copy-pasted all files to a brand new React Native project, created on Ubuntu, and then it just worked.


## What do I need to run it?
* NodeJS
* JAVA SDK
* ReactNative
* Visual Studio Code with PlatformIO


## Installation
Place the contents of the repository somewhere on your system (manualy or with git) and open the folder in VSCode

1. Run the following command to install all needed libraries
    ```
    npm install
    ```
2. Update the Android Studio SDK location in `./android/local.properties`

3. Run the following command to start Metro on your terminal:
    ```
    npx react-native start
    ```  
4. On another terminal, run the following command to launch the app on your connected android phone (make sure it has debugging enabled)
    ```
    npx react-native run-android
    ```
5. In a seperate VSCode Window open the "Arduino" folder and upload the Code to an ESP32 using PlatformIO

## Are you HDSM?
Just download the directory `UniquelyMadeESP32`, and ask me for the APK file.
