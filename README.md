# Setup Push Notifications in your Expo App
Forked from the sample project https://github.com/friyiajr/Expopushnotifications for Youtube tutorial
https://www.youtube.com/watch?v=V-hois8dgM4&ab_channel=Dan%27sReactNativeLab


Expo Push Notifications Tool: https://expo.dev/notifications

## Create and configure Firebase Project
Create a Firebase project "ExpoPushNotification" in https://console.firebase.google.com

Add Firebase to your Android app, register the app and download google-services.json file, copy google-services.json file to `./android/app/google-services.json`, add  `googleServicesFile": "./android/app/google-services.json` to the entry `android` in app.json.


then prebuild

`npx expo prebuild`

`asdf local nodejs 20.15.0`
`npx expo install expo-dev-client`

Create Expo project "ExpoPushNotifications", then

`npm install --global eas-cli`
Project already linked (ID: e9370c3c-47e4-477b-9344-1a211f2aead2). To re-configure, remove the "extra.eas.projectId" field from your app config.


`npx expo-doctor`
`npx expo install --check`

`eas build --profile=development --platform=android`

🤖 Android build failed:
Gradle build failed with unknown error. See logs for the "Run gradlew" phase for more information.

`expo upgrade`

`eas build --profile=development --platform=android`

## Expo Project Configuration
Project settings -> Service accounts to Generate new private key

Expo Project credentials -> clikc Application identifier "com.healthq.PushNotifications"
In FCM V1 service account key, Add a service account key by uplodaing the new private key file.


`eas build --profile=preview --platform=android`

Go to Expo All builds -> Android internal distribution build -> Install

Scan this code with a device

Open the Camera app and point it at this code. Then tap the notification that appears.

Download the app preview and install it manually on your Android device.


Open the app and go to
https://expo.dev/notifications
Recipent
Expo push token from your app (shown in the app)
    eg. ExponentPushToken[Mly8NULNfHeGEEt1wAYeLq]

Message title
    Hello, World!

Message body
    Android Push Notification!

Force FCM Protocol
    Force FCM V1
    Send Android notifications via FCM V1, regardless of whether a valid credential exists