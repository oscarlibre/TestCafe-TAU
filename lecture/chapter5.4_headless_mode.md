# Chapter 5.4 - Headless Mode

#### Run Tests with TestCafe in Headless Mode Overview

Headless mode is very useful when we are running CI servers and we don't need to open and consume resources on our machines.

So TestCafe allows you to run tests in Google Chrome and the Mozilla Firefox without a visible UI shell in headless mode (Chrome headless and Firefox headless)

Use the :headless parameter to launch a browser in headless mode.

For example, with Firefox, we can run:

```
testcafe firefox:headless ./tests/
```

...or with chrome:

```
testcafe chrome:headless ./tests/
```

So headless mode with TestCafe only supports Chrome and Firefox to be able to run our tests without any UI or any GUI interface.


####  Use Chromium Device Emulation Overview

You can run tests with Chromium's built-in device emulator in Google Chrome, Chromium, and Chromium-based Microsoft Edge with emulation browser parameter and specifying the target device with the device parameter.

For example:

```
testcafe "chrome:emulation:device=iphone X" ./tests/sample-fixture.js
```

The previous example will run a test with chrome and emulating the device "iphone X".



#### Resources

![Run Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/run-tests.html)

![Simulate Mobile Devices with Device Mode in Chrome DevTools ](https://developers.google.com/web/tools/chrome-devtools/device-mode/)

![Source chapter 5.4](https://testautomationu.applitools.com/testcafe-tutorial/chapter5.4.html)
   
