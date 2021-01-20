# Chapter 5.1 - Test Execution

#### The supported browsers with TestCafe

TestCafe is designed to support most modern browser and it detects the popular browsers installed on a local computer.

TestCafe is actively tested with these browsers:

  - Google Chrome with different versions, with Stable, Beta development, or Dev, and the Canary
  - Internet Explorer 11 or above
  - Microsoft Edge Legacy or Chromium-based
  - Mozilla Firefox
  - Safari
  - Google Chrome mobile
  - Safari mobile


The following command will give the list of the browsers that are supported in our machine. 

```
testcafe --list-browsers
```

Also, we can run our tests on all the local browsers using the following command:

```
testcafe all tests
```

The following example will execute the test *firstTest.js* and it will open three instances together on different browsers:

```
testcafe firefox,chrome,safari tests/firstTest.js
```

#### Skipping web application errors

Sometimes there are JavaScript errors inside the web application itself, not in our test code. if you face this problem, you can add this option *--skip-js-errors.*


```
testcafe all tests/firstTest.js --skip-js-errors
```


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 5.1](https://testautomationu.applitools.com/testcafe-tutorial/chapter5.1.html)

   
