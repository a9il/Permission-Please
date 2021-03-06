# Permission Please V0.9
>Request Android runtime permissions from a unity game

This plug-in exists because it wasn't an easy process to use [Android runtime permissions](https://developer.android.com/training/permissions/requesting) and I didn't like it when games would ask for all kind of permissions on app launch.

This plug-in uses base code from the answer on [this stackoverflow question](https://stackoverflow.com/questions/35027043/implementing-android-6-0-permissions-in-unity3d) by [Jason Knight](https://stackoverflow.com/users/5919897/jason-knight) from [Noodlecake studios](http://www.noodlecake.com/)

## Getting Started
You can either copy the `Plugins` directory from this repo into the root of your project or download the provided unity package file `PermissionPlease.unitypackage`.

Then edit the file `AndroidManifest.xml` and remove the permissions that you don't need, make sure to only include the ones that you need.

To request a runtime permission on an Android device:
``` cs
//requests READ_EXTERNAL_STORAGE permission and calls OnPermissionCallback(bool) with the result if it was granted or not, true is supplied to enable logging.
PermissionPlease.GrantPermission(PermissionPlease.AndroidPermission.READ_EXTERNAL_STORAGE, OnPermissionCallback, true);
```
And `OnPermissionCallback` would look something like this:
```cs
private void OnPermissionCallback(bool granted)
{
    if(granted)
        print("permission granted xD");
    else
        print("permission denied :(");
}
```

> The `Java` directory is not required in the project, it's just there as a reference. It contains the Java code and a shell script (for my mac) to generate the .jar file.
>
>  it can be safely removed from the project but the `libs` directory is essential.

There are example scenes and codes to try in the project, need to test on an actual Android device [Or Emulator].



## Warning
It should work fine, but I haven't tested it a lot, submit any issues you find.

## What's next
Detect if user disabled the permission [picked don't ask again] and give an option to open settings to enable the permission 

## Special Thanks
[Noodlecake studios](http://www.noodlecake.com/)

## Author
Jafar Abdulrasoul [Jimmar]
