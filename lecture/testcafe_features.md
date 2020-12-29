# Chapter 4 - TestCafe Features

#### Specify the Start Webpage Overview

You can specify the webpage where all the tests in a fixture begin with the fixture.page function.

In this case, the start page of the test will be the URL that we specified with the fixture.

```javascript
fixture `MyFixture`
    .page `https://devexpress.github.io/testcafe/example/`;
test('Test1', async t => {
    // Starts at http://devexpress.github.io/testcafe/example
});
```

For example, here we are adding a .page, or a fixture.page function, and passing the URL for the application under test. That means all the tests will use the page from the fixture. This is the first case.

In the second case, we can specify the start with a page with the test.page.

```javascript
fixture `MyFixture`
    .page `https://devexpress.github.io/testcafe/example/`;
test
    .page `https://devexpress.github.io/testcafe/blog/`;
    ('My test', async t => {
    // Starts at http://devexpress.github.io/testcafe/blog/
});
```

You can specify a start page for individual tests with a test.page function that overrides the fixture.page.

In this case, if you are passing a page with this URL with the fixture, that means that all the tests will use it until we use the test.page and this URL will override the previous URL with the fixture. So we need to take care of this one - test.page will override the fixture.page.

#### Specify the Start Webpage Demo

In this demo, we will learn how to specify the start webpage with the test cases. We will continue working with our previous example - webPage.js.

As we mentioned in our slides, we can pass the page with the fixture, but that means that all the tests inside this fixture or with this fixture will use the same page - but what if we have one test and we need to use a specific URL for this test?

So in our demo, we will copy this URL for example - [https://devexpress.github.io/testcafe/example/](https://devexpress.github.io/testcafe/example/) - and then go to the test, and like fixture.page webpage, we can add test.page, and here we have a page. Then we can pass the URL as a string with test.page and pass the example. And then, for example, here, we can just open the main page for testcafe, and after that with our test, we are overriding this page and opening the example to be able to continue with the test case.

```javascript
fixture("First Fixture")
    .page("http://devexpress.github.io/testcafe/");

test.page("https://devexpress.github.io/testcafe/example/")
("First Test", async t =>{
    await t
        .typeText("#developer-name","TAU")
        .click("#macos")
        .click("#submit-button");
});
```

We can run our test with testcafe on the command line with Chrome browser, with our tests package and  webPage.js

```
testcafe chrome tests/webPage.js
```

After that, we can run our test.

Testcafe will initialize and run the local server, redirect to the URL, and we will notice that we will redirect to the example URL, not the main URL for that fixture webpage and the test is successful.

For example, also, if we can change the fixture.page - maybe we can add the Google website and save the changes - we'll be able to ensure that we are redirected to the test.page URL.


```javascript
fixture("First Fixture")
    .page("http://www.google.com");

test.page("https://devexpress.github.io/testcafe/example/")
("First Test", async t =>{
    await t
        .typeText("#developer-name","TAU")
        .click("#macos")
        .click("#submit-button");
});

```


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.1](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.1.html)

   
