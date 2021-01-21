# Chapter 5.2 - Run Tests in Parallel

#### Run Tests in Parallel With TestCafe

TestCafe allows to execute tests concurrently. In concurrent mode, TestCafe invokes multiple instances of each browser.
These instances constitute the pool of browsers against which tests run concurrently. For example, each test runs in the first available instance.

To enable concurrency, use *-c* or *--concurrency* with the command line.

```
testcafe -c 3 chrome tests/test.js
```

This command invokes three Chrome instances and runs tests concurrently, 3 is the number of instances needed to run from Chrome. After that, we are passing our test file.

The concurrency with TestCafe means that we are running or splitting the test with different concurrency. We are not repeating the test with the same or with each instance. This is the main idea or main point about concurrency or parallelization with TestCafe.

We can also use concurrency when testing against multiple browsers. For example:


```
testcafe -c 4 safari,firefox tests/test.js
```

This means that we will open four instances of Safari and four instances of Firefox browsers and run our tests (the concurrent test execution is not supported in Microsoft Edge).


####  TestCafe Live Mode

Live mode ensures TestCafe and the browsers remain active while you work on tests.
You can see test results instantly because the tests are restarted when you make changes.
We can use *-L* or *--live flag* to enable live mode from the command line interface.

For example:

```
testcafe chrome tests/test.js -L
```

Before we run our test, maybe we can just return it to the command line or the terminal, and here we have different commands.

![](https://testautomationu.applitools.com/course55/chapter5.2-img6.png)

Tests now are working in live mode. So from the terminal, you can click on:

- Ctrl+S to stop the test run
- Ctrl+R to restart the test run
- Ctrl+W to enable or disable watching files
- Ctrl+C to quit the live mode and close the browsers


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 5.2](https://testautomationu.applitools.com/testcafe-tutorial/chapter5.2.html)

   
