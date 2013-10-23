#### Build & Run

- `gradle clean ; gradle assembleDebug`
- `gradle clean ; gradle assembleTest`

--

- `adb install -r ./testapp/build/apk/testapp-test-unaligned.apk`
- `adb install -r ./testapp/build/apk/testapp-debug-unaligned.apk`
- `adb shell am instrument -w com.google.android.apps.common.testing.ui.testapp.test/com.google.android.apps.common.testing.testrunner.GoogleInstrumentationTestRunner`

--

- `adb shell pm list instrumentation`
