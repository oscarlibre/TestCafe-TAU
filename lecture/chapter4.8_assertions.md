# Chapter 4.8 - Assertions

#### Assertions with TestCafe

TestCafe provides a comprehensive set of assertions that are based on a behavior-driven development style or BDD style.

```javascript
await t.expect (actual).eql(expected, message, options);
```

We have await with the test controller *t.expect()*, after that, we add the actual result inside the brackets. Then we need to check that the actual results are equal to the expected one.
*.equal()* takes in parameters expected, message, and options if we wanted to add anything else.

You can specify the assertion query timeout in test code, with the *options.timeout option*.

Let's see the following example:

```javascript
await t.expect(Selector('#elementId').innerText).eql('text', 'check element text', {timeout: 500});
```

Here we are selecting *'#elementId* from the web application and getting the element's inner text. Then we assert the inner text inside this element is equal to the text and the message "check element text".
and pass the time out 500 milliseconds.

####  What are the other methods that TestCafe supports for assertions?

We have different and a huge number of assertions methods with TestCafe like:

    - deep equal
    - not deep equal
    - ok
    - not ok
    - contains
    - not contains
    - type of
    - not type of
    - greater than
    - greater than or equal to
    - less than or equal to
    - within
    - not within
    - match
    - not match

We can use all of them in our tests to verify that the test output is as expected.

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.8](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.8.html)
