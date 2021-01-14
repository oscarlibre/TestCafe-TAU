# Chapter 4.7 - Hooks

#### How to use TestCafe Hooks overview

TestCafe allows you to specify functions that are executed before a fixture when a test is started or after it's finished. Test hooks override fixture hooks.
If a test runs in several browsers, test hooks are executed in each browser. You can specify a hook for each test in a fixture with the *fixture.beforeEach* or *fixture.afterEach* methods.
So here is an example for a fixture - where you have a fixture with the title, a page with a URL, and we have beforeEach and this is the hook.


```javascript
fixture("First Fixture")
    .page("http://devexpress.github.io/testcafe/")
    .beforeEach(async t =>{
        await t
            .setTestSpeed(0.1)
            .setPageLoadTimeout(0);
    });

test
.page("https://devexpress.github.io/testcafe/example/")
("First Test", async t =>{
    await t
        .typeText("#developer-name","TAU")
        .click("#macos")
        .click("#submit-button");
});

test
.page("https://devexpress.github.io/testcafe/example/")
("Second Test", async t =>{
    await t
        .typeText("#developer-name","TAU")
        .click("#macos")
        .click("#submit-button");
});
```

So this means that before each test in our fixture - because we have two - we will do these three things: maximize the window, set the test speed, and set the page time load.


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![TestCafe - Fixture.beforeEach Method](https://devexpress.github.io/testcafe/documentation/reference/test-api/fixture/beforeeach.html)

![TestCafe - Fixture.afterEach Method ](https://devexpress.github.io/testcafe/documentation/reference/test-api/fixture/aftereach.html)

![Source chapter 4.7](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.7.html)

   
