#### Build & Run

- `gradle clean ; gradle assembleDebug ; gradle assembleTest`

--

- `adb install -r ./testapp/build/apk/testapp-debug-unaligned.apk`
- `adb install -r ./testapp/build/apk/testapp-test-unaligned.apk`
- `adb shell am instrument -w com.google.android.apps.common.testing.ui.testapp.test/com.google.android.apps.common.testing.testrunner.GoogleInstrumentationTestRunner`

--

- `adb shell pm list instrumentation`
- `adb shell pm list packages -3 google`


```
$ adb shell pm list instrumentation`
instrumentation:com.google.android.apps.common.testing.ui.testapp.test/com.google.android.apps.common.testing.testrunner.GoogleInstrumentationTestRunner
 (target=com.google.android.apps.common.testing.ui.testapp)

$ adb shell pm list packages -3 google
package:com.google.android.apps.common.testing.ui.testapp.test
package:com.google.android.apps.common.testing.ui.testapp

$ adb shell am instrument -w com.google.android.apps.common.testing.ui.testapp.test/com.google.android.apps.common.testing.testrunner.GoogleInstrumentationTestRunner
```

```
Error: duplicate files during packaging of APK /build/apk/testapp-test-unaligned.apk
	Path in archive: LICENSE.txt
	Origin 1: /test_libs/hamcrest-integration-1.1.jar
	Origin 2: /test_libs/hamcrest-library-1.1.jar


$ zip -d ./testapp/test_libs/hamcrest-integration-1.1.jar LICENSE.txt
deleting: LICENSE.txt

> Duplicate files copied in APK LICENSE.txt
  	File 1: /Users/staffhome/Desktop/appium/testappProject/testapp/test_libs/hamcrest-library-1.1.jar
  	File 2: /Users/staffhome/Desktop/appium/testappProject/testapp/test_libs/hamcrest-library-1.1.jar

$ zip -d ./testapp/test_libs/hamcrest-library-1.1.jar LICENSE.txt
deleting: LICENSE.txt
```