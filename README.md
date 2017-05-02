# Restaurant Hybrid Mobile Application

by The Hong Kong University of Science and Technology. Exercise provided by Coursera.

### About 

conFusion is a restaurant application. This application provides menu presentation, contact and personnel information. Moreover, a visitor can register a new profile, customize it, make reservations, add favorite dishes, write reviews and receive notifications.

### Programming languages, Frameworks and Libraries

* HTML5
* CSS
* Javascript
* Bootstrap framework
* AngularJS
* Bower(Package Manager for the Web)
* Gulp(Task Automation)
* MVC(Model View Controller)
* SPAs(Single Page Application)
* REST API
* Ionic framework
* Cordova(Cordova is used for building hybrid mobile applications using HTML, CSS and JavaScript. Is a set of of libraries together with plugins, that you have for accessing various native capabilities of a device. Cordova is nothing but an open source mobile app development framework).

### Features

- REST API server with json-server
- Menu presentation, Dish categorization and ordering, Table reservation, Profile registration and customization, Contact and Personel Information, Add dish to favorites, Delete dish from favorites, Add comment to dish, Send restaurant feedback, Receive notifications.
- Splash screen, choosing profile picture during registration using build-in camera or android gallery, Local notification, Toast notification, Vibration.

***

## Step 1 - Preconfiguration of your computer

Make sure that you have installed node, gulp and bower on your computer.
	
		To install node go to, https://docs.npmjs.com/getting-started/installing-node
		npm install gulp-cli -g
		npm install bower -g
	
Setting up the Ionic Framework

To install the Ionic framework, at the prompt type:
	
		npm install cordova ionic -g

If you are installing on OSX or Linux, make sure to precede with sudo.
	
Move to the conFusion folder and examine the contents.
To see the resulting project in your browser, type the following at the command prompt:
	
		ionic serve

Now you have installed Cordova and Ionic on your computer.

***

## Step 2 - json-server

The Node module, json-server, provides a very simple way to set up a web server that supports a full-fledged REST API server. It can also serve up static web content from a folder. After the next steps, we will leverage these two features to provide the back-end for the Angular application. Now, we will configure and start a server using json-server to enable serving the application data of the Angular application.


#### Installing json-server

json-server is a node module, and hence can be installed globally by typing the following at the command prompt:
	
		npm install json-server -g
		
If you are using OSX or Linux, use sudo at the front of the command. This will install json-server that can be started from the command line from any folder on your computer.
	
  
#### Configuring Server Folder

In the project there is a folder named json-server, move to this folder. There should be a db.json file there.
Move to this folder in your terminal window, and type the following at the command prompt to start the server:
	
		json-server --watch db.json
		
This should start up a server at port number 3000 on your machine. The data from this server can be accessed by typing the following addresses into your browser address bar:
	
		http://localhost:3000/dishes
		http://localhost:3000/promotions
		http://localhost:3000/leadership
		http://localhost:3000/feedback
		http://localhost:3000/images/<image name>.png
		
Type these addresses into the browser address and see the JSON data being served up by the server. This data is obtained from the db.json file.

The json-server also provides a static web server. Any resources that are in the folder named public in the json-server folder above, will be served by the server at the following address:
	
		http://localhost:3000/
		
You can shut down the server by typing ctrl-C in the terminal window.


#### Ionic server

You can start the ionic server by typing the following at the prompt in the Ionic folder(root folder of the project):
		
		ionic serve --lab

***

## Step 3 - Preparing your Computer for Deploying on Native Platforms

Once the Ionic project is downloaded and set, you need to prepare your computer for developing and deploying the application to mobile devices. The development and deployment instructions depends on the specific platform (Android or iOS).

Below, you will find the Cordova's official guides to prepare your computer for both the Android and iOS platform deployment. Please follow along the instructions given in these guides to set up your computer.

Note: For iOS development and deployment you need a Mac running OS X.

- Preparing your Computer for Android Development: Cordova Guide

           http://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html

- Preparing your Computer for iOS Development: Cordova Guide

           http://cordova.apache.org/docs/en/latest/guide/platforms/ios/index.html
	
#### Resources
  [Android studio](https://developer.android.com/studio/index.html) , 
  [Java Development Kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)


#### iOs Resourses
  [XCode (App Store)](https://idmsa.apple.com/IDMSWebAuth/login?appIdKey=891bd3417a7776362562d2197f89480a8547b108fd934911bcbea0110d07f757&path=%2Fdownload%2Fmore%2F&rv=1) , 
  [Apple Developer Downloads](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

***

## Step 4 Part 1 - Building and Deploying to iOS Emulator

#### - Updating localhost to the IP address of your computer

Find out the IP address of your computer. On a Mac, go to System Preferences->Network to find the IP address of your network adapter.
Open services.js, and change the localhost in the following line to the IP address of your computer:
	
		.constant("baseURL", "http://<Your Machine's IP Address>:3000/")

For example, if your IP address is 192.168.1.121, then the above line should be as follows:
	
		.constant("baseURL", "http://192.168.1.121:3000/")
    
Save the changes.
Make sure that your json-server is up and running


#### - Configure, build and Deploy to an iOS Emulator

Open a terminal window and go to the conFusion folder where the Ionic application is.
Make sure to install ios-sim as shown below:
		
		 npm install -g ios-sim

Use sudo if you are doing this on a Mac or Linux machine.

Next, add the iOS platform to the app by typing the following at the prompt:
		
		 ionic platform add ios
     
Then, build the app for the iOS platform as follows:
	
		ionic build ios
    
Finally, you can deploy the app to the iOS emulator by typing the following at the prompt:
	
		ionic emulate ios

This will start your default iOS emulator and deploy the app to the emulator, and run the app.
	
  

## Step 4 Part 2 - Building and Deploying to Android Emulator

#### - Updating localhost to the IP address of your computer

Find out the IP address of your computer. On a Mac, go to System Preferences->Network to find the IP address of your network adapter. If you are using a Microsoft Windows based machine, you can use the instructions available at  http://windows.microsoft.com/en-us/windows/find-computers-ip-address#1TC=windows-7 to find your machine's IP address.
Open services.js, and change the localhost in the following line to the IP address of your computer:
	
		.constant("baseURL", "http://<Your Machine's IP Address>:3000/")

For example, if your IP address is 192.168.1.121, then the above line should be as follows:
		
		.constant("baseURL", "http://192.168.1.121:3000/")

Save the changes.
Make sure that your json-server is up and running


#### - Configure, build and Deploy to an Android Emulator

Open a terminal window and go to the conFusion folder where the Ionic application is.
Next, add the Android platform to the app by typing the following at the prompt:
	
		ionic platform add android

Then, build the app for the Android platform as follows:
	
		 ionic build android

Finally, you can deploy the app to the Android emulator by typing the following at the prompt:
	
		ionic emulate android

This will start your default Android emulator and deploy the app to the emulator, and run the app.
	
  
#### - Configure, build and Deploy to an Android Device

If you happen to have an Android device and are willing to use it for development, then configure the device to allow development on the device. The exact procedure depends on the manufacturer and model of the device. Check for these instructions either within your device manual, or online. The most common steps are :
	
1. Go to the settings menu, and scroll down to "About phone." Tap it.
2. Scroll down to the bottom again, where you see "Build number." (Your build number may vary from ours here.)
3. Tap it seven (7) times. After the third tap, you'll see a playful dialog that says you're four taps away from being a developer. (If only it were that simple, eh?) Keep on tapping, and *poof*, you've got the developer settings back.
	
Connect your Android device to the computer and make sure that it is connected to the same network(wifi) as the server machine. Then, at the command prompt, type the following:
	
		ionic run android

This should deploy the app to the device and open the app on the device.
	
***
  
## Step 5 - ngCordova
	
#### - Installing ngCordova

At the terminal prompt, making sure you are in the conFusion folder, type the following to install ngCordova:
	
		bower install ngCordova --save

Then, build the app and deploy it to the emulator or a device.
	
  
#### - Adding the Cordova Plugins

First, add the Cordova plugin for the local notifications by typing the following at the command prompt:
	
		ionic plugin add de.appplant.cordova.plugin.local-notification

Then, install the Cordova Toast plugin by typing the following at the prompt:

		ionic plugin add https://github.com/EddyVerbruggen/Toast-PhoneGap-Plugin.git
			 
Save the changes, build and deploy the application to the emulator to see the changes.
	
  
#### - Adding the Cordova Camera Plugin

First, add the Cordova camera plugin by typing the following at the command prompt:

		 ionic plugin add cordova-plugin-camera
	
Or use the following command at the command prompt, if your Cordova version is below 5.0:
	
		 ionic plugin add org.apache.cordova.camera
			 
Save the changes, build and deploy the application and see the changes.
