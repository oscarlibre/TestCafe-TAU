# Chapter 3 - Getting Started with TestCafe

#### Async/await functions
- Async
  - Stands for asynchronous
  - It is a function that always returns a promise
  - Async ensures that the function returns a promise and wraps the non-promises in it.
- Await
  - It makes JavaScript wait until the promise settles and then go with the result.
- We use async with the test controller. 
- We use await with selectors, actions, assertions, verifications, redirect the pages, and all the things that we can do with TestCafe.


#### Fixtures
- TestCafe tests must be organized into categories called fixtures.
- To declare the test fixtures use a fixture function

Here we have the fixture and MyFixture is the title or the name of the fixture. After that, we can add one or more tests inside or with this fixture. We are passing async, which will help us after that is running parallel tests.
*t* a test controller, or an object from the test controller, which will control our test to be able to run in the browsers. Then, we are adding our test code inside this test. And if you have another or additional test case, it will be here or we can add one or more test cases inside one file. So 'Test 1' and 'Test 2' are our test names, and we are passing async, or asynchronous test controller.

```javascript
fixture `MyFixture`;

test('Test1', async t => {
    /* Test 1 Code */
});

test('Test2', async t => {
    /* Test 2 Code */
});
```

#### The Test Controller
We need to pass it as a parameter for each test. And it handles, or this test function accepts this controller to be able to run this test.
A test controller exposes the test API's methods and passing to each function that can run server-side test code.

Use a test controller to:
- Call test actions
- Handle browser dialogs
- Use the wait functions
- Execute assertions

#### First Test

We started with the fixture and adding the fixture name, passing it the page or the URL, or the application under tests that we will use.
Then we are writing our first test with a test name and asynchronous test controller. And after that, with the test controller, we are using 'await' to be handled or to automatically handle the ways for the element to be displayed or to be initialized in the DOM, with a type of script action for the text box, with the click with the radio button, and the click for the submit button.

```javascript
fixture("First Fixture")
    .page("https://devexpress.github.io/testcafe/example/");
test("First Test", async t => {
    await t
        .typeText('#developer-name','TAU')
        .click('#macos')
        .click('#submit-button');
});
```   
For running our test, we are using TestCafe. And after that, we are using the browser name - for example, we will use Chrome. Then we will select the test - the firstTest.js file inside the tests folder:

```
testcafe chrome tests/firstTest.js
```

or 

```
npx testcafe chrome tests/firstTest.js
```




#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 3.1](https://testautomationu.applitools.com/testcafe-tutorial/chapter3.1.html)

![Source chapter 3.2](https://testautomationu.applitools.com/testcafe-tutorial/chapter3.2.html)
   
