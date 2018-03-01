# training-mobile-appium-desktop
Learn about basic functionalities of Appium desktop application.

## Prerequisites
* In order to use Appium desktop app you need to install Android SDK.
* You can use an emulator or your own Android device for this example. 
    * If you use your Android device you will need to activate Developer Mode and enable USB debugging - please follow the steps here:
      https://www.androidphonesoft.com/resources/enable-usb-debugging-on-android.html
    * If you use an emulator, I recommend Genymotion for Personal Use: https://www.genymotion.com. Please have prepared one Android 6.0 emulator ready for start
* You will need to clone or download this project as zip file, in order to have access to the test application and Appium session json configuration files

1. Android tools

* Make sure you have the correct value in ANDROID_HOME System variable - the path to the Android SDK installed with Android Studio or standalone.
* Adb Android tool can be found in ANDROID_HOME\platform-tools
* Command line command for finding the connected Android devices on your computer:
   >adb devices
   
## Install Appium desktop
Please download the latest release of Appium app, the `.exe` for Windows or `.dmg` for Mac OS:
* https://github.com/appium/appium-desktop/releases

After download please follow the install wizard.

The version used in this tutorial is Appium Desktop 1.3.2 for Mac OS which contains Appium Server version 1.7.2.

## Application under test
Yamba is Yet Another Micro Blogging App. It was written to support various Android training classes, most specifically Android Bootcamp, and is an evolution of the project from Learning Android book written by Marko Gargenta. You can find it at http://github.com/thenewcircle/yamba. The version of the app used in this tutorial was downloaded from: https://github.com/mailat/android-testing-2016-02-19.

The debug apk can be found here:
* `apps/yamba-debug.apk`

The test user for this app is:
* username = `student`
* password = `password`

## Appium Desktop
Follow these steps in order to start the Appium server and to use the Appium Inspector with the application
under test, Yamba.

1. Appium Simple server
    Start the Appium application.
    1. Enter in the app's first screen:
        * Host = 127.0.0.1
        * Port = 4723 (this is the default server port)
        and click `Start Server` which will start the Appium Server

     ![Alt text](screenshots/StartLocalhost.png?raw=true)
    
    2. When the server starts, the server logs window is opened:
  
     ![Alt text](screenshots/StartedLocalhost.png?raw=true)
    
    This window will show through its logs and messages the status of the Appium server.

2. New Session

    Through the New Session we want to start an Appium session for the application under test.
Our goal is to inspect and interact with Appium Inspector some of the application elements. This session can use
the currently running Appium server, or a new one.

    1. From the server logs window, upper right corner, click the `Start Inspector Session` button:
   
     ![Alt text](screenshots/InspectorBtn.png?raw=true)
    
    2. A New Session window is opened which has by default selected the option `Automatic Server`
    which is using the server we just opened (section 1.)
    
     ![Alt text](screenshots/NewSession.png?raw=true)
     
    3. Add the needed Desired Capabilities with `+` button:
        * `platformName` = `Android` - we test on Android
        * `deviceName`, `deviceUdid` - please add your phone/tab/emulator values here
        For Genymotion emulator use: `udid` = `192.168.56.101:5555`
        * `app` - full path of the Yamba app, where you downloaded/closed this project, folder /apps
        * `appPackage` = `com.example.android.yamba`
        * `appActivity` = `com.example.android.yamba.MainActivity`
        * `noReset` = `true` - because we will start multiple sessions, and we don't want the app to be reset
       
        ![Alt text](screenshots/SimpleYambaSession.png?raw=true)
        
        You can find the json with these capabilities here: (this can be copied directly in the `JSON Representation` section)
        * for emulator - `inspector/emulatorS7YambaSession.json`
        * for real device - `inspector/simpleYambaSession.json`
        
     4. Click the `Start Session` button which will start the Appium session and open a new Inspector window to 
     the Yamba app with no element selected:
        
        ![Alt text](screenshots/SimpleYambaSessionStarted.png?raw=true)      
        
3. Appium Inspector
    When the session with the Yamba app is started you can inspect the application elements and perform basic
    interactions with them.
    
    1. The app's hierarchy is in the middle of the window, represented as XML. You can navigate this tree by clicking through it, or by clicking on elements in the screenshot view.
    They will then be highlighted.
 
    2. On the left side, Screenshot view of the app, click on the Menu button (3 dots) element and click `Tap`
   
        ![Alt text](screenshots/MoreOptionsBtn.png?raw=true)      
        
    3. The Options menu is opened and the app screen gets refreshed and the elements hierarchy the same (App Source section)
    
        ![Alt text](screenshots/AfterMoreOptionsBtn.png?raw=true)  
        
        
## Practice, practice :exclamation: :sweat:

In the Inspector window you also have a Toolbar in the upper section. There you have `The Recorder` option with which
you can record some of your interactions with the app and some code will be generated for you.
Please read the section `The Recorder` from Appium desktop app: 
https://github.com/appium/appium-desktop   

