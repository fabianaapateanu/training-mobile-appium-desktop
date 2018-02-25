# training-mobile-appium-desktop
Learn about basic functionalities of Appium desktop application

# Install Appium desktop
Please download the latest release of Appium app from:
* https://github.com/appium/appium-desktop/releases
Download the ".exe" for Windows or ".dmg" for Mac OS.

The version used in this tutorial is Appium Desktop 1.3.2 for Mac OS which contains Appium Server version 1.7.2.

# Application under test
Yamba is Yet Another Micro Blogging App. It was written to support various Android training classes, most specifically Android Bootcamp, 
and is an evolution of the project from Learning Android book written by Marko Gargenta. Find it at http://github.com/thenewcircle/yamba

The debug apk can be found here:
* apps/yamba-debug.apk
and it was downloaded from:

https://github.com/mailat/android-testing-2016-02-19

The test user for this app is:
* username = `student`
* password = `password`

# Start server
1. Simple server
    1. Enter in the app's first screen:
        * Host = 127.0.0.1
        * Port = 4723 (this is the default server port)
        and click `Start Server`

    ![Alt text](screenshots/StartLocalhost.png?raw=true)
    
    2. When the server start, the server logs window is opened:
    ![Alt text](screenshots/StartedLocalhost.png?raw=true)
2. Presets
