# Connect ESP32 to Android

Based on this repo: https://github.com/palmmaximilian/ReactNativeArduinoBLE

Original project ran on Windows. I couldn't make it work on Ubuntu 20.04, so I copy-pasted all files to a brand new React Native project, created on Ubuntu, and then it just worked.


## What do I need to run it?
* NodeJS
* Android Studio (download [here](https://developer.android.com/studio) or [install using snap](https://snapcraft.io/android-studio)). Open it a first time, to ensure all dependencies are installed.
* JAVA SDK (I installed it with `sudo apt install openjdk-8-jdk`)
* ReactNative
* Visual Studio Code with PlatformIO (to flash the ESP32)

For additional details, please refer to the [docs](https://reactnative.dev/docs/environment-setup).

## Installation
Place the contents of the repository somewhere on your system (manualy or with git) and open the folder in VSCode

1. After installing the aforementioned softare, run the following command to install all needed libraries
    ```
    npm install
    ```
2. Update the Android Studio SDK location in `./android/local.properties`

3. Run the following command to start Metro on your terminal:
    ```
    npx react-native start
    ```  
4. On another terminal, run the following command to launch the app on your connected android phone (make sure it has USB debugging enabled). Note that this step may trigger additional dependency downloads from Android Studio.
    ```
    npx react-native run-android
    ```
5. In a separate VSCode Window open the "Arduino" folder and upload the Code to an ESP32 using PlatformIO

## How do I export the apk file?
Why, that's a great question indeed...

In a nutshell:
1. Verify if the file `index.android.bundle` exists in directory `.android/app/src/main/assets/`. If not, create both.
2. Run
    ```
    npx react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res
    ```
3. Then run
    ```
    cd android && ./gradlew assembleDebug
    ```
4. The apk will be found in `./android/app/build/outputs/apk/debug/app-debug.apk`
For additional details please refer to https://dev.to/nitish173/how-to-generate-a-debug-apk-in-react-native-1gdg


