# SyncMarket
You can manage your application's version update or get your market information more simply.<br>
This Library used [Jsoup](https://jsoup.org/).

![kakaotalk_20170202_213907914](https://cloud.githubusercontent.com/assets/24237865/22550481/9fd478da-e993-11e6-9ca5-cfcff0e2dd26.jpg)

 
## Including in your project
#### build.gradle
```java
repositories {
  mavenCentral() // or jcenter() works as well
}

dependencies {
  compile 'com.skydoves.syncmarket:syncmarket:1.0.3'
}
```

#### or Maven
```xml
<dependency>
  <groupId>com.skydoves.syncmarket</groupId>
  <artifactId>syncmarket</artifactId>
  <version>1.0.3</version>
</dependency>
```
    
## Usage
#### Permission
Need below permissions in AndroidManifest.xml
```xml
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
```

#### Initialize
Next you have to call initialize method as below as follows
```java
SyncMarket.Initialize(this);
```

#### Useage
and then use like this
```java
SyncMarket.getMarketVersion() 
```

That's it!

#### Note
If you call "get...()" Method, then return your published app's information from Google Play Store.<br>
From : **https://play.google.com/store/apps/details?id= + (packageName)**

If your application is not published yet or not connected internet, then return **null**.

#### Method list
```java
SyncMarket.getMarketVersion(); // get the last published version from Google Play Store
```

```java
SyncMarket.isVersionEqual(); // check is this application version equal the last published version?
```
```java
SyncMarket.getMarketDownloads(); // get downloads range from Google Play Store
```
```java
SyncMarket.getMarketRecentChange(); // get recent change list from Google Play Store
```
```java
SyncMarket.getMarketRecentChangeArray(); // get the last published date from Google Play Store as string array
```
```java
SyncMarket.getMarketOperatingSystems(); // get require minimum device api level from Google Play Store
```
```java
SyncMarket.getMarketPublishedDate(); // get the last published date from Google Play Store
```
```java
SyncMarket.getMarketUrl(); // get url application's url
```
```java
SyncMarket.gotoMarket(); // intent your application's Google Play Store Page
```
```java
SyncMarket.isNetworkAvailable(); // check is network is available? 
```
#### Proguard rules for release
```java
-keep public class org.jsoup.** {
	public *;
}
```

# License
```xml
Copyright 2017 skydoves

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
