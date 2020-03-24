# Sample for Android

> A sample for testing each feature in LiveEngage

# What is this?

This is a sample implementation for Android native application integrating [Apache Cordova](https://cordova.apache.org/) and [Mobile Messaging SDK for Android](https://developers.liveperson.com/mobile-app-messaging-sdk-for-android-overview.html).
The purpose of this application is to test and upgrade the plugin [MessagingSDKPlugin](../../plugins/MessagingSDKPlugin/).
There's no guarantee that code here does work for business requirement accordingly.

# Prerequisite

Make sure that the followings end with success:

```
$ cordova platform add android
$ cordova requirements
```

If not, check if appropriate packages are installed and if the variables are correctly set such as:

```
$ echo ${PATH}
$ echo ${ANDROID_SDK_ROOT}
```

PATH should have as follows:

```
$ ls -d ${HOME}/Library/Android/sdk/emulator
$ ls -d ${HOME}/Library/Android/sdk/tools
$ ls -d ${HOME}/Library/Android/sdk/platform-tools
$ ls -d ${HOME}/Library/Android/sdk/tools/bin
```

ANDROID_SDK_ROOT should be below:

```
$ ls -d ${HOME}/Library/Android/sdk
```

Once the check has passed, remove the android platform, because this sample requires nightly build:

```
$ cordova platform remove android
```

# How to build

Android Messaging SDK v5.1.1 requires API level 29, and the version 9 of Apache Cordova has not yet supported it.
However, a nightly build works with API level 29, then building needs as follows:

```
$ cordova --version
9.0.0 (cordova-lib@9.0.1)
$ cordova platform add https://github.com/apache/cordova-android.git#c56cd4d5a8fdf2fc80ee8a9f1c960f21fca87a9a
$ cordova plugin add ../../plugins/MessagingSDKPlugin/
$ cordova build android
```

The plugin itself should be managed at [MessagingSDKPlugin](../../plugins/MessagingSDKPlugin/), because Android support is a part of functionality of this plugin.
That will have change for iOS support.

# How to run the sample application and the plugin

The current combination of versions does NOT work by the following way:

```
$ cordova run --emulate android
```

Therefore open the following directory by Android Studio for testing every feature on Android native application:

```
$ ls -d ${PWD}/platforms/android
```

The code of the plugin is below:

```
$ ls platforms/android/app/src/main/java/com/liveperson/plugin/LPMessagingSDK.java
```

Once "cordova clean" is called, the above file is gone, then make sure that this file has been copied to [MessagingSDKPlugin](../../plugins/MessagingSDKPlugin/) if meaningful changes on this plugin.
