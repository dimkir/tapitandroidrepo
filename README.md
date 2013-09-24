This readme has information about how the repository and project are organized, and also rules about publishing the app on the play store.



All the project files are inside the directory "bebak.kyle.matchit". This directory is NOT the package name for the application -- the package name, "bebak.kyle.tap_it", is specified in the manifest file and the series of directories inside the src directory. It would make more sense to make this "com.bebak.kyle.matchit", but if one changes the package name of the app it is no longer considered the same app on google play, so this package name can never change. 

In the bin directory is a compiled, unsigned, and unaligned apk file that can be installed on a device over the Android Debug Bridge for debugging. If you run the app on a device from within the Eclipse ADT, it will automatically recompile this apk and install it on the device. STRANGELY, if there is no apk file in the bin folder the ADT will not let you run the app -- you have to compile the debug apk by right clicking the root project directory > Android Tools > Export Unsigned Application Package. Also, the android:debuggable attribute in the manifest file must be set to "true" to install the app over the adb.



Inside the directory "web" are the resources for publishing the app on the play store. There are preview images, the 512 x 512 google play icon, the keystore used to sign the app (whose password only I know), and the compiled, signed, and aligned apk. Compiling an apk ready for the public is easiest to do with the ADT (File > Export > Android > Export Android Application). Just like the package name, the keystore used to sign the app CAN NEVER CHANGE. This keystore uniquely identifies the app the same as the package name does, and it must be used any time the app is updated so that the new apk is considered a new version of the same app by google play.