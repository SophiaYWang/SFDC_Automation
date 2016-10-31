# SFDC_Automation

SFDC (Sales Force Dot Com) Automation is a test automation demo project designed for purpose of test automation POC (Prove Of Concept) and sales/marketing demo.


## Pre-request
1. Python, wxPython2, and RIDE Installation<br />
 * Install [python-2.7.11.amd64.msi](https://www.python.org/ftp/python/2.7.11/python-2.7.11.amd64.msi)
 * Add "C:\Python27;C:\Python27\Scripts;" to %PATH%
 * Install [wxPython2.8-win64-unicode-2.8.12.1-py27.exe](https://sourceforge.net/projects/wxpython/files/wxPython/2.8.12.1/) 
 * Extract robotframework-ride-1.5.2.1.tar.gz
 * Go to the extracted directory and run<br /> 
    ```
    python setup.py install
    ```
2. Install Robotframework, ExcelLibrary, Selenium2Library and AppiumLibrary<br />
    ```
    pip install robotframework
    
    pip install robotframework-ExcelLibrary
    
    pip install robotframework-selenium2library
    
    pip install robotframework-appiumlibrary
    ```
3. Download and install appium server.<br />
Appium server [download](https://bitbucket.org/appium/appium.app/downloads/)
4. Download and Install browser drivers.<br />
 * Download driver and copy to your %PATH%.<br />
    Firefox Driver: [geckodriver.exe](https://github.com/mozilla/geckodriver/releases)<br />
    Chrome Driver: [chromedriver.exe](https://sites.google.com/a/chromium.org/chromedriver/downloads)<br />
    IE Driver: [IEDriverServer.exe](https://github.com/SeleniumHQ/selenium/wiki/InternetExplorerDriver)<br />
5. Android Environment setup.
 * [Download](https://developer.android.com/studio/index.html) and Install Android STUDIO/STUDIO BUNDLE
 * Run Android SDK manager to Install Platform-tools and Build-tools。
 * Set the ANDROID_HOME environment variable with the Android SDK root directory path
 * Add %ANDROID_HOME%\platform-tools;%ANDROID_HOME%\tools to %PATH%
 * Install [Wandoujia](https://www.wandoujia.com/) so that mobile device driver will be installed automatically when devices get connected.
6. Parallel execution
 * Parallel execution only supports Android environment only currently.
 * Start a appium server thread for each execution thread. If appium servers were run within one host, set different appium bootstrapport, nodeport and chromedriver port among those parallel process. Like:<br />
    ```
    node node_modules\appium\bin\appium.js -p 4723 -bp 4733 --chromedriver-port 4743
    ```
 * Start a RIDE process for each execution thread. Connect to different appium server in your environment.
 
6. iOS Environment setup.
 * [Download](https://github.com/snevesbarros/SafariLauncher) latest version of SafariLauncher 
 * Code sign for SafariLaucher from xcode and build app to ios device
 * Go to build folder and zip SafariLauncher.app to SafariLauncher.zip file
 * Copy the SafariLauncher.zip file to 
/Applications/Appium.app/Contents/Resources/node_modules/appium/build/SafariLauncher/SafariLauncher.zip
 * Copy same source code to /Applications/Appium.app/Contents/Resources/node_modules/appium/node_modules/SafariLauncher
 * Install ios-webkit-debug-proxy:<br /> 
   ```
    brew install ios-webkit-debug-proxy
   ``` 
 * Config node.js  environment variable:<br />
   ```
   export PATH=/Applications/Appium.app/Contents/Resources/node/bin:$PATH
   ```
 * navigate to appium installation folder:<br />
   ```
   cd /Applications/Appium.app/Contents/Resources/node_modules/appium/bin/
   ```
 * Start ios-webkit-debug-proxy:<br />
   ```
   ./ios-webkit-debug-proxy-launcher.js -c [udid]:27753 -d
   ```
 * Appium setting
 * Device Settings
    Settings->Safari->Advanced->Web Inspector
    Developer->Enable UI Automation
 * Install idevice installer: <br />
   ```
   brew –install ideviceinstallerz
   ```


## SFDC Environment dependency

1. Please email lanny.zhu@pwc.com to get real user_credential.txt before you run the cases.

2. 4 Contacts under Android SDFC user: ${AN_USERNAME}<br />
  - Contact1: android phone1 //in (lastname) (firstname) format<br />
  - Contact2: android phone2<br />
  - Contact3: android pad1<br />
  - Contact4: android pad2<br />

3. 4 Contacts under iOS SDFC user: ${IOS_USERNAME} <br />
  - Contact1: ios phone1 //in (lastname) (firstname) format<br />
  - Contact2: ios phone2<br />
  - Contact3: ios pad1<br />
  - Contact4: ios pad2<br />

4. WEB SDFC user: ${WEB_USERNAME}


# SFDC_Automation

SFDC (Sales Force Dot Com) Automation 是一个专门为Salesforce.com自动化测试定制的演示项目，主要用于原型验证和销售市场演示使用。

## SFDC 环境依赖

1. 运行前请先发送邮件给lanny.zhu@pwc.com获取真实user_credential.txt账号文件。

2. Android SDFC 账号${AN_USERNAME}下有4个用户: <br />
  - Contact1: android phone1 //in (lastname) (firstname) format<br />
  - Contact2: android phone2<br />
  - Contact3: android pad1<br />
  - Contact4: android pad2<br />

3. iOS SDFC 账号${IOS_USERNAME}下有4个用户: <br />
  - Contact1: ios phone1 //in (lastname) (firstname) format<br />
  - Contact2: ios phone2<br />
  - Contact3: ios pad1<br />
  - Contact4: ios pad2<br />

4. WEB SDFC 账号: ${WEB_USERNAME}