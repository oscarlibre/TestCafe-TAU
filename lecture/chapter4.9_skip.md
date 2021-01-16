# Chapter 4.9 - Skip Test

#### Skip tests overview

we can skip tests with one single configuration. TestCafe allows you to specify a test or a fixture to skip when tests run.

Use the *fixture.skip* and *test.skip* methods for this.


```javascript
fixture.skip `Fixture 1`; // All tests in this fixture are skipped

test('Fixture 1 - Test 1', ()  => {});
test('Fixture 1 - Test 2', () => {});

fixture `Fixture 2`;

test('Fixture 2 - Test 1', () => {});
test.skip('Fixture 2 - Test 2', () => {}); //This test is skipped
test('Fixture 2 - Test 3', () => {});
```

So, writing *fixture.skip* means that all the tests inside Fixture 1 are skipped. So tests 'Fixture 1 - Test 1' and 'Fixture 1 - Test 2' will be skipped.
'Fixture 2 - Test 1' will be run because it does not include a skip, but 'Fixture 2 - Test 2' will be skipped because here we are mentioning test.skip. 

####  fixture.only and test.only

If you mention *fixture.only*, that means that we will run an specific fixture only. On another hand *test.only*,  will run specific tests.

```javascript
fixture.only `Fixture 1`; 

test('Fixture 1 - Test 1', ()  => {});
test('Fixture 1 - Test 2', () => {});

fixture `Fixture 2`;

test('Fixture 2 - Test 1', () => {});
test.only('Fixture 2 - Test 2', () => {}); 
test('Fixture 2 - Test 3', () => {});
```

Only tests in 'Fixture 1' and the 'Fixture 2 - Test 2' will run because we mentioned that 'Fixture 1' would run only, so we will run both tests inside this fixture, and we will run 'Test 2' only from the 'Fixture 2'.

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.9](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.9.html)
