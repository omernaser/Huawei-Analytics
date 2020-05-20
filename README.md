# Huawei Xamarin Analytics Demo

## Contents
- Introduction
- Installation Guide
- React-Native Example Method Definition
- Configuration Description
- Licensing and Terms

## 1. Introduction

The demo project is an example that aims to demonstrate how the HUAWEI Analytics Kit SDK for Xamarin can be used.

The Xamarin SDK wraps the Android SDK with Managed Callable Wrappers through the usage of Android Bindings Library projects. It provides the same APIs as the native SDK.

The Xamarin SDK libraries are described as follows:

- Library .DLL files: These are the files enable the usage of the native Android SDK interfaces. Once generated, these files can be referenced & used directly in a Xamarin.Android project.

## 2. Installation Guide

Before using the Xamarin SDK code, ensure that Visual Studio 2019 is installed with "Mobile development with .NET" support.

### Summary
- Download the SDK and its dependencies
- Generate the binding libraries
- Copy the libraries into the demo project
- Create an application in the AppGalleryConnect platform, configure the application retrieve **agconnect-services.json** file
- Sign your application and register the SHA-256 fingerprint on the AppGallery Connect platform
- Run & debug your app

### 2.1 Huawei Xamarin Analytics Library
You can retrieve the library from developer.huawei.com

### 2.2 Download native Android SDK packages
The analytics SDK and its dependencies must be downloaded from the Huawei repository.
Use the following URLs to download the packages.
- [hianalytics-4.0.2.300.aar](https://developer.huawei.com/repo/com/huawei/hms/hianalytics/4.0.2.300/hianalytics-4.0.2.300.aar)
- [tasks-1.3.3.300.aar](https://developer.huawei.com/repo/com/huawei/hmf/tasks/1.3.3.300/tasks-1.3.3.300.aar)
- [update-2.0.6.300.aar](https://developer.huawei.com/repo/com/huawei/hms/update/2.0.6.300/update-2.0.6.300.aar)
- [network-grs-4.0.2.300.aar](https://developer.huawei.com/repo/com/huawei/hms/network-grs/4.0.2.300/network-grs-4.0.2.300.aar)
- [network-common-4.0.2.300.aar](https://developer.huawei.com/repo/com/huawei/hms/network-common/4.0.2.300/network-common-4.0.2.300.aar)
- [base-4.0.2.300.aar](https://developer.huawei.com/repo/com/huawei/hms/base/4.0.2.300/base-4.0.2.300.aar)
- [opendevice-4.0.1.301.aar](https://developer.huawei.com/repo/com/huawei/hms/opendevice/4.0.1.301/opendevice-4.0.1.301.aar)
- [agconnect-core-1.0.0.300.aar](https://developer.huawei.com/repo/com/huawei/agconnect/agconnect-core/1.0.0.300/agconnect-core-1.0.0.300.aar)
- [agconnect-credential-1.0.0.300.aar](https://developer.huawei.com/repo/com/huawei/agconnect/agconnect-credential/1.0.0.300/agconnect-credential-1.0.0.300.aar)
- [agconnect-https-1.0.0.300.aar](https://developer.huawei.com/repo/com/huawei/agconnect/agconnect-https/1.0.0.300/agconnect-https-1.0.0.300.aar)
- [datastore-core-1.0.0.300.aar](https://developer.huawei.com/repo/com/huawei/agconnect/datastore-core/1.0.0.300/datastore-core-1.0.0.300.aar)
- [datastore-annotation-1.0.0.300.jar](https://developer.huawei.com/repo/com/huawei/agconnect/datastore-annotation/1.0.0.300/datastore-annotation-1.0.0.300.jar)

### 2.3 Open the library project
An Android Bindings Library project for Xamarin allows the usage of only one .aar file. For this reason the library repository comes with multiple library projects. 

Open up Visual Studio 2019. Then from the menu;
	
- Click "Open a project or a solution"
- Navigate to the directory where you cloned the repository and open "XHiAnalytics-4.0.2.300.csproj".

### 2.4 Import the downloaded packages
Once you open the library project for the analytics SDK, each package you downloaded in the first step must placed under its related library project.

Inside the "Solution Explorer", expand each project and repeat the steps below:
- Right click "Jars" -> "Add" -> "Existing Item" (Shift + Alt + A)
- Navigate to the folder where you downloaded the packages and select the related .aar or .jar file.	
    
         Example: For XTasks-1.3.3.300 project, import "tasks-1.3.3.300.aar"
- Click on the package file you just imported. 
		In the **properties** window, 
			
    - set the Build Action as "LibraryProjectZip" if the file type is .aar
	- set the Build Action as "EmbeddedJar" if the file type is .jar

### 2.5 Download the common dependencies
There are some open-source dependencies that should be downloaded seperately to each necessary library project. These dependencies are downloaded by using the NuGet Package Manager console.

From the Visual Studio's toolbar, click Tools -> NuGet Package Manager -> Package Manager Console. Then perform the steps below:
- In the package manager console window, set one of the following projects as the default: 
	- XAgConnectHttps-1.0.0.300
	- XAgConnectCredential-1.0.0.300
	- XHiAnalytics-4.0.2.300
	
- Run the following commands to install the common dependencies. 
**NOTE:** Make sure you have a **stable internet connection** and if you have a proxy setting, make sure it does prevent access to the NuGet platform.

```
    Install-Package Square.OkHttp3 -Version 3.11.0
	Install-Package Xamarin.Square.OkIO -Version 1.14.0
```
		
- Repeat the steps for **each of the three projects**.

### 2.6 Build the library.
From the Visual Studio's toolbar, click "Build" -> "Build Solution" (Ctrl + Shift + B).
Once the build process is complete, generated classes should be visible in the object browser and ready to use.

(View -> Object Browser) (Ctrl + Alt + J)

### 2.7 Copy the libary .dll files
Once you build the analytics SDK library project, the generated .dll files should be copied inside the demo project.
- Copy the .dll files from "...\XHiAnalytics-4.0.2.300\bin\Debug\" or "...\XHiAnalytics-4.0.2.300\bin\Release\" depending on your build type selection.
- To the "_LibDlls" folder of the demo project. 

### 2.8 Create an application with AppGallery Connect
To be able to observe the events sent from the demo application, you need to follow the steps specified under the item 2, in the URL below.
- [Analytics Kit Pre-development Procedure](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/Development-Guide#h1-2-pre-development-procedure)


### 2.9 Place your agconnect-services.json file inside the project
Download the **agconnect-services.json** file created for your AppGallery application, by following the steps specified under the item 3.1, in the URL below.
- [Integrating the Analytics Kit SDKs](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/Development-Guide#h1-3-integrating-the-sdks)
	
Once you download your "**agconnect-services.json**" file, place it under the "Assets" folder of the demo project.

### 2.10 Open the demo project and modify AndroidManifest.xml
Open up Visual Studio 2019. Then from the menu;
- Click "Open a project or a solution"
- Navigate to the directory where the demo project resides and open "XamarinHmsHiAnalyticsDemo.csproj".

Open the "AndroidManifest.xml" file under the "Properties" folder. Then change the "package" property with package name you specified on the AppGallery Connect platform.

### 2.11 Create a signature file
If you already have a signature file generated, you can skip to the next step.

If you don't have a signature file, perform the following steps:
- Open the command line tool (using the **cmd** command) and run the **cd** command to go to the directory where **keytool.exe** is located under the **JDK** installation directory. 

    **Note:** Visual Studio comes with OpenJDK installed.

- Run the following command:

```
keytool -genkey -keystore <keystore-file> -storepass <keystore-pass> -alias <key-alias> -keypass <key-pass> -dname <dname> -keysize 2048 -keyalg RSA -validity <validity-period>
```

- In the preceding command;

    - **\<keystore-file\>** is the complete path to the app's signature file. File extension must be .jks or .keystore. For example; "D:\Android\mykeystore.jks"
    - **\<keystore-pass\>** is the password of your keystore. Requires minimum 6 characters. For example; "123456"
    - **\<key-alias\>** is the alias name of key that will be stored in your keystore. For example; "sitekitshowcase"
    - **\<key-pass\>** is the password of your key. Requires minimum 6 characters. For example; "12345"
    - **\<dname\>** is a unique identifier for the application in the keystore. For example; "o=Huawei"
    - **\<validity-period\>** Amout of days the key will be valid with this keystore. For example; "36500"

    Example:
```
keytool -genkey -keystore D:\Android\mykeystore.jks -storepass 123456 -alias sitekitshowcase -keypass 123456 -dname "o=Huawei" -keysize 2048 -keyalg RSA -validity 36500
```

### 2.12 Sign your application
You need to sign your application in order to be able to register & use your signature file in the AppGallery Connect platform. Perform the following steps:
- In the "Solution Explorer" window, right click the demo and open "Properties"
- In the window that just opened, select "Android Package Signing" from the menu on the left.
- Check the option "Sign the .APK file using the following keystore details.". Then fill out the form below with required information.

    **Note:** You should perform these steps for both **Debug** and **Release** configurations.

### 2.13 Obtaining the SHA-256 fingerprint from signature file
You need to obtain the SHA-256 Fingerprint of your signature file.

Perform the following steps:
- Open the command line tool (using the **cmd** command) and run the **cd** command to go to the directory where **keytool.exe** is located under the **JDK** installation directory. 

    **Note:** Visual Studio comes with OpenJDK installed.

- Run the following command and copy the SHA-256 fingerprint from the result.

```
keytool -list -v -keystore <keystore-file>
```
- In the preceding command;
    - **\<keystore-file\>** is the complete path to the app's signature file. For example; "D:\Android\mykeystore.jks"

    Example:
```
keytool -list -v -keystore D:\Android\mykeystore.jks
```

### 2.14 Registering the singing certificate fingerprint
The signature fingerprint should be registered on the AppGallery Connect platform.

Perform the steps below:
- Sign in to [AppGallery Connect](https://developer.huawei.com/consumer/en/service/josp/agc/index.html), click "**MyApps**" then select your application.
- From the menu on the top, click on "**Develop**" and scroll to the bottom of the page.
- Set the SHA-256 certificate fingerprint as the SHA-256 fingerprint you copied in the previous step.

### 2.15 Run & debug your application
You can now run your application and it should automatically start up on your mobile device.

You can debug the events sent from your application by the following the steps described under the item 6.3, in the URL below:
- [Access Debugging](https://developer.huawei.com/consumer/en/doc/development/HMS-Guides/Development-Guide#accessing_analytics_)

## 3. Xamarin Example method definition
No. Developer can flexibly develop projects based on the example code. 

## 4. Configure parameters.    
No.

## 5. Licensing and Terms  
Huawei Xamarin SDK uses the Apache 2.0 license.

