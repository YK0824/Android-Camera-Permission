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
