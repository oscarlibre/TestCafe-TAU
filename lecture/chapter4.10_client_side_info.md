# Chapter 4.10 - Working with Client-Side Info

#### Working with Client-Side Info

TestCafe also supports woringk with client-side information or client-side scripts.

You can create client functions that can return any serializable value from the client-side, such as the current URL or custom data calculated by a client script.

For example, in this code snippet, we are checking the page URL.


```javascript
import { ClientFunction } from 'testcafe';

fixture `My Fixture`
    .page `http://devexpress.github.io/testcafe/example`;

//Returns the URL of the current web page
const getPageUrl = ClientFunction(() => window.location.href);

test('Check the page URL', async t => {
    await t
        .typeText('#developer-name', 'John Smith')
        .click('#submit-button') //Redirects to the 'Thank you' page
        .expect(getPageUrl()).contains('thank-you'); //Checks if the current page URL contains the 'thank-you' string
});
```
With ClientFunction, we can get *window.location.href*, which will get us that current page URL. And we use this constant in our method then expect that *getPageURL* contains "thank-you".

So with different examples, we can use the client-side to get any data or any custom data calculation from the client-side script. We are not hitting any server-side code, but it's only from the browser and from the client-side script.

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.10](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.10.html)
