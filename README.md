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

# Install Postman for making API calls
- Download Postman at https://www.getpostman.com
- Install Postman
- Run Postman

# Get Organization List
- Make a POST call with the following parameters (make sure to select x-www-form-urlencoded)
```
POST https://mybeerlist.co/Beer.Identity/token
grant_type:password
username:xxxxxxxx
password:xxxxxxxx
client_id:beerApp
```
- Get the access token back
- Retrieve organization list by making a GET call.
```
GET https://mybeerlist.co/Beer.Services/api/Organizations

```
- In Headers, make sure to have the following entry. The access token (eyJ0.. needs to be pasted behind "Bearer" in Authorization header)
```
Accept: application/json
Authorization: Bearer xxxxxxxxxxxxx
```
- Find the organization ID from the list, and we will try to create the APK for the specific organization. Let's say the ID is 31 (Rose Brewery)

# Organization folder customization
- Clone a folder under app_ionic2/configurations for an organization
- In Postman, make the following GET call:
```
GET https://mybeerlist.co/Beer.Services/api/Settings/31
```
- Replace defaultSetting.json in the with the online version
- Find appIcon's ImageId (103) and headImage's ImageId (104)
- Let's download ICON image first (103): visit the following URL (with the appropriate image ID):
```
GET https://mybeerlist.co/Beer.Services/api/Images/103
```
- Replace icon.png with the image above. Must scale to 1024x1024
- Now let's download splash image (104). Visit the following URL (with the appropriate image ID):
```
GET https://mybeerlist.co/Beer.Services/api/Images/104
```
- Replace splash.png with the image above. Must scale to 2732x2732
- Edit config.xml with correct app name
- Replace Firebase's google-services.json 

# Visual Studio Code Compiling
- Replace files with the above settings
- Compile against the updated setting
```
cd app_ionic2
ionic cordova resources android
ionic cordova build android --release
```








