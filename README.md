# Android-Camera-Permission
This is before the start of the Android project, we must enable the resource permissions.  
In the Android 6.0 version, you need to open the relevant permissions before using the application.   
So in this example, the main purpose is to learn and record how to turn on the camera permissions, 
and when you refuse multiple times, the system will open the setting window, and the user can set the permissions by himself.

###### In the AndroidManifest.xml
First, you need to add camera permission.  
```java
<uses-permission android:name="android.permission.CAMERA" />
```
Before here, it is used in lower than the Android 6.0 version.  
If project higher than the Android 6.0 version, it will need more setting.  

###### In the MainAcitivity
You will need to check permission, if it was the first time to open application or didn't allow permission before.  
And then you need to request permission. Here you see.
```java
if(ActivityCompat.checkSelfPermission(this, Manifest.permission.CAMERA)
        != PackageManager.PERMISSION_GRANTED){
    ActivityCompat.requestPermissions(this,new String[]{Manifest.permission.CAMERA},1);
}
```
![image](https://github.com/YK329-24/Android-Camera-Permission/blob/main/permission_inf.PNG)

###### Check Allow
Here you can use camera source.  

###### Check Refuse
If you deny permission multiple times.The user must go to the setting interface to manually open the camera permissions.
```java
Uri uri_pack = Uri.fromParts("package", getPackageName(), null);
Intent intent = new Intent(Settings.ACTION_APPLICATION_DETAILS_SETTINGS);
intent.setData(uri_pack);
startActivity(intent);
```
![image](https://github.com/YK329-24/Android-Camera-Permission/blob/main/setting_permission_inf.PNG)

Thank you for your watching, YK's Learning and Record. My first android project.
If your have any suggestions, welcome to discuss, There are still many shortcomings, thank you for your advice.
