# AndroidConfigGradle

### buildToolsVersion
> It always a best practice to use latest buildToolsVersion

Definition: `buildToolsVersion` is the version of the compilers (aapt, dx, renderscript compiler, etc...) that you want to use. `buildToolsVersion` only affect the compilers -> **it will not affect the application**

Using gradle > 3.0, we don't need to specific the `buildToolsVersion` because each gradle have a default `buildToolsVersion` (but we still able to config it)

https://stackoverflow.com/a/24523113/5381331

### compileSdkVersion
Definition:  The API that your app will use

Example: If you set the `compileSdkVersion` 25, your app will use the code of `SDK 25`. That code may different to `SDK24` (example some function will change/remove or some bug is fixed).

### targetSdkVersion
Definition:  The target feature that you app need to use

Example: If you set `targetSdkVersion`  >= 23 (Android 6(Marshmallow)), in your app you need to request runtime permission programmatically
If you set `targetSdkVersion`  < 23, you don't need to request it. However, user still able to disable your app permissions in Settings ( when user disable, you app will not crash but it not work well).
More details (after test) , when user disable your app permissions, android system will display a warning like "This application is design for older Android version, disable this permissions will make this app not working"

We can check the `Platform Highlights` to know which feature have added after each release here
https://developer.android.com/guide/topics/manifest/uses-sdk-element.html
