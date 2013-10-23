#### Build & Run

- `gradle clean ; gradle assembleDebug ; gradle assembleTest`

--

- `adb install -r ./testapp/build/apk/testapp-test-unaligned.apk`
- `adb install -r ./testapp/build/apk/testapp-debug-unaligned.apk`
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

Test results for GoogleInstrumentationTestRunner$BridgeTestRunner=
Time: 0.0

OK (0 tests)
```