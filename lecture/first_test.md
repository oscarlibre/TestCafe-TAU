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


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)


![Source chapter 3.1](https://testautomationu.applitools.com/testcafe-tutorial/chapter3.1.html)
   
