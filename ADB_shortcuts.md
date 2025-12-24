## ADB settings

### Hide system bars
```
adb shell settings put global policy_control immersive.full=*
```

### Show system bars again
```
adb shell settings put global policy_control null
```

### Show / collapse status bar / notification bar
```
adb shell cmd statusbar expand-notifications
adb shell cmd statusbar expand-settings
adb shell cmd statusbar collapse
```

## Open screens through ADB

### open device admin page
```
adb shell am start -n com.android.settings/.DeviceAdminSettings
```

### open "App info" page for an app
```
adb shell am start -a android.settings.APPLICATION_DETAILS_SETTINGS -d package:<package_name>
```
Example:
```
adb shell am start -a android.settings.APPLICATION_DETAILS_SETTINGS -d package:com.avievinson.vobble
```
```
adb shell am start -a android.settings.APPLICATION_DETAILS_SETTINGS -d package:com.avievinson.vobble.vobbledeviceupdater
```

### Start an app
```
adb shell monkey -p <package_name> 1
```
Example:
```
adb shell monkey -p com.avievinson.vobble 1
```
```
adb shell monkey -p com.avievinson.vobble.vobbledeviceupdater 1
```
### Set density
Example - set to 240
```
adb shell wm density 240
```


## Get data through ADB

### Get `versionCode` and `versionName`
```
adb shell dumpsys package <package_name> | grep -e "versionCode\|versionName"
```
Example:
```
adb shell dumpsys package com.avievinson.vobble | grep -e "versionCode\|versionName"
```
```
adb shell dumpsys package com.avievinson.vobble.vobbledeviceupdater | grep -e "versionCode\|versionName"
```
