# Chapter 6.1 - Wait Mechanism

#### The Wait Mechanisms with TestCafe

We have different mechanisms with TestCafe for the wait, for actions, or with selectors or assertions.
TestCafe has a built-in automatic waiting mechanism, and it doesn't require a dedicated API to wait for redirects or page elements to appear.
These mechanisms work when TestCafe performs test actions, evaluates assertions and selectors, sends requests, and navigates the browser.

#### The Wait Mechanism for Actions

TestCafe automatically waits for the target element to become visible when an action is executed.
Then, TestCafe tries to evaluate the specific selector multiple times within the timeout. If the element doesn't appear, the test will fail.
When a selector is executed, TestCafe waits for the target node to appear in the DOM until the selector timeout expires.
As we mentioned previously, we can use the timeout option to specify the selector timeout in the test code. 
To set the timeout when you launch tests, pass it to the *runner.run* API method or the *--selector-time* command-line option.

#### The Wait Mechanism for Selectors

When using a selector, TestCafe automatically waits for the element to appear in the DOM.

With our code that we are using already in the previous demos, for example:


```javascript
import { Selector } from 'testcafe';

fixture `My fixture`
    .page `https://devexpress.github.io/testcafe/example`;

const nameInput = Selector('#developer-name');

test('My test', async t => {

    // Waits for '#developer-name' to appear in the DOM
    const nameInputElement = await nameInput();
 }
```

Here in our test, you're already using await nameInput() - and this is waiting for the developer input or the name input to appear in the DOM without any additional APIs or without any additional libraries.
TestCafe keeps trying to evaluate the selector until the element appears in the DOM, or the timeout passes.
You can additionally require that TestCafe should wait for an element to become visible. Use the *visibilityCheck* selector option for this.

For example:

```javascript
// Waits for '#developer-name' to appear in the DOM and become visible.
const nameInputElement = await nameInput.with({ visibilityCheck: true })();
```
That means that we should wait until, or TestCafe should wait until the element is displayed or is visible in the DOM.

#### The Wait Mechanism for Assertions

TestCafe assertions use a Smart Assertion Query mechanism that is activated when you pass a selector property or a client function as an actual value.

TestCafe keeps recalculating the actual value until it matches the expected value or the assertion timeout passes.

#### The Wait Mechanism for Redirects

When an action triggers a redirect, TestCafe automatically waits for the server to respond.

The test continues if the server doesn't respond within 15 seconds.

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![TestCafe - Built-In Wait Mechanisms](https://devexpress.github.io/testcafe/documentation/guides/concepts/built-in-wait-mechanisms.html)

![Source chapter 6.1](https://testautomationu.applitools.com/testcafe-tutorial/chapter6.1.html)

    
