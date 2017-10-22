# Android Studio Installation
- Visit https://developer.android.com/studio/install.html
- Download Android Studio (1.9G)
- Install Android Studio

# NodeJS Installation
- Visit https://nodejs.org/en/download/
- Download Node LTS 6.11.4
- Install Node

# Ionic setup
- Start Node command line
```
sudo npm install -g ionic@latest
```
- verify installation with:
```
ionic --version
```

# Cordova setup
- In Node command line, install Cordova by running:
```
sudo npm install -g cordova
```
# Visual Studio Code setup
- Download Visual Studio Code from https://code.visualstudio.com/download
- Install it
- git clone https://ychen.visualstudio.com/DefaultCollection/_git/Beerlist
- Run Visual Studio Code
- Navigate to Beerlist
- Switch to develop branch (click botton left button to see a list of branches)

# Ionic registration
- Go to https://apps.ionic.io/login
- Click "Sign-up"
- Register an account. This email & password will be used later

# Download Java SDK
- Download http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
- Install the SDK

# Create APK for the default organization (MBL)
The goal here is to create an APK for MBL
```
cd app_ionic2
npm install
ionic cordova resources android
ionic cordova build android --release
```

# Get settings from API
- Make API call to get org setting

- Visit https://mybeerlist.co/Beer.Services/api/Settings/29
- Replace defaultSetting.json with the online version
- Extract Head Image & Icon from Settings JSON. 
- Replace JSON's Icon with icon.PNG. Must scale to 1024x1024
- Replace JSON's Header Image with Splash.PNG. Must scale to 2732x2732
- Edit config.xml with correct app name
- Replace Firebase's google-services.json 

# Visual Studio Code Compiling
- Switch to Develop branch
- Run the following
```
cd app_ionic2
npm install
ionic cordova resources android
ionic cordova build android --release
```
- Remember to enter the email & password above
- Generated APK can now be tested on Android phone








