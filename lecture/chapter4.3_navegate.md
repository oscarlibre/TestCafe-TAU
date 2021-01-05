# Chapter 4.3 - TestCafe Navigate

#### navigateTo()

This method navigates to a specific URL and the parameter is a URL. Also, it can be a file or anything else.

```javascript
fixture('Navigate Example')
.page('https://devexpress.github.io/testcafe/example/')

test('navigate test',async t => {
    await t 
      .navigateTo("http://www.google.com");
})
```

So the test would start by navigating to the URL page https://devexpress.github.io/testcafe/example/, and after that, we'll redirect to the google URL.

Runnning the test and check what happened.

```
testcafe chrome tests/navigateTest.js
```

#### test.page vs navigateTo()
This is different from the test.page because *test.page* overrides the page inside the fixture,  *navigateTo()*  will open the URL inside the fixture, and after that, navigate to the URL inside the test case.


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.3](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.3.html)

   
