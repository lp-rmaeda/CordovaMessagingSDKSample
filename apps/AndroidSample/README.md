# Sample for Android

> A sample for testing each feature in LiveEngage

# How to build
Android Messaging SDK v5.1.1 requires API level 29, and the version 9 of Apache Cordova has not yet supported it.
However, a nightly build works with API level 29, then building needs as follows:

```
$ cordova platform add https://github.com/apache/cordova-android.git#c56cd4d5a8fdf2fc80ee8a9f1c960f21fca87a9a
$ cordova plugin add ../../plugins/MessagingSDKPlugin/
$ cordova build android
```
# How to test

Now on it.
