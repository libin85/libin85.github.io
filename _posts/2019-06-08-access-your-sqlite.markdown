---
title:  "Access SQLite database from an Android device"
date:   2019-05-20 20:30:00
comments: true
categories: [Xamarin]
tags: [Xamarin, SQLite]
---
SQLite has been one of the most popular databases among software developers for almost two decades. Since its inception in year 2000, it has been the go-to option for building small to medium size applications that don't require a full-blown database like SQL Server or MySQL. What I really like about SQLite is that the database can be served from the disk directly and does not need any installation.

But what makes SQLite popular among mobile developers is it being pretty light weight, and that it comes in-built in both Android and iOS devices. There are several tools available to view/manage data in SQLite. The one that I use day to day is [DB Browser for SQLite][dbBrowser]. In todays post, we are going to look at how we can pull the database from an Android APK and  view its data. 

##### **Open the ADB Command Prompt**

| IDE                | Options                                                    |
| ------------------ | ---------------------------------------------------------- |
| Visual Studio 2019 | `Tools Menu` -> `Android` ->  `Android ADB Command Prompt` |
| Visual Studio Mac  | `Tools Menu` -> `SDK Command Prompt`                       |
{:.table-striped}

##### **To connect to your device, run the following command**
```kotlin
adb shell  
```
`Note: Make sure your android device is connected to the computer.`

##### **Then connect to the APK installed on device** 
```kotlin
run-as com.companyname.appname    //com.companyname.appname is your apk package name.
cd files                          //to move to files folder where the db exists.
ls                                //this command will list all the files in this folder.
```
`Note: You can find the apk package name in the Android Manifest file.`

Once we are in the `files` folder, look for the SQLite database here. The database file name would have extension of either `db3` or `sqlite3`  

##### **Copy to the sdcard**.
Now we have located the db file, we can copy it to any location in the sd card. Please ensure that the location in the sdcard exists. 
```kotlin
cp sample.db3 /sdcard/download/sample.db3
```
##### **Copy db to your computer**.
Once the file has been copied to the sdcard, we can exit the adb shell by running the exit command twice and then we are ready to copy the file to our computer. 
```kotlin
exit                              // to exit out of the apk package. 
exit                              //to exit out of the adb shell.
adb pull /sdcard/download/sample.db3 C:/users/libin/desktop/sample.db3             
``` 

Now we should have the sqlite database in our computer. We can now use our favourite sqlite tool to view the data.

Happy Coding!!

[dbBrowser]: https://sqlitebrowser.org/
{% include disqus.html %}