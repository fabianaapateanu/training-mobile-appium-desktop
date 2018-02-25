# training-mobile-appium-desktop
Learn about basic functionalities of Appium desktop application

## Install Appium desktop
Please download the latest release of Appium app, the `.exe` for Windows or `.dmg` for Mac OS:
* https://github.com/appium/appium-desktop/releases

The version used in this tutorial is Appium Desktop 1.3.2 for Mac OS which contains Appium Server version 1.7.2.

## Application under test
Yamba is Yet Another Micro Blogging App. It was written to support various Android training classes, most specifically Android Bootcamp, 
and is an evolution of the project from Learning Android book written by Marko Gargenta. Find it at http://github.com/thenewcircle/yamba
This used version of the app was downloaded from: https://github.com/mailat/android-testing-2016-02-19

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

2. Appium Inspector

    Through the Appium Inspector we want to start an Appium Driver session for the application under test.
Our goal is to inspect and interact with some of the applications elements.

    1. From the server logs window, upper right corner, click the `Start Inspector Session` button:
     ![Alt text](screenshots/InspectorBtn.png?raw=true)
    
    2. A new Inspector Session window is opened which has by default selected the option `Automatic Server`
    which is using the server we just opened (section 1.)
     ![Alt text](screenshots/NewSession.png?raw=true)
     
    3. Add the needed Desired Capabilities with `+` button:
        * `platformName` = `Android` - we test on Android
        * `deviceName`, `deviceUdid` - please add your phone/tab values here
        * `appPacakge` = `com.example.android.yamba`
        * `appActivity` = `com.example.android.yamba.MainActivity`
        * `noReset` = `true` - because we will start multiple sessions, and we don't want the app to be reset
        ![Alt text](screenshots/SimpleYambaSession.png?raw=true)
        
        You can find the json with these capabilities here: (this can be copied directly in the `JSON Representation`)
        * `inspector/simpleYambaSession.json`
        
     4. Click the `Start Session` button which will open a new session to the Yamba app with no element selected:
        ![Alt text](screenshots/SimpleYambaSessionStarted.png?raw=true)      
        
