# Chapter 4.2 - TestCafe Metadata

#### Fixture / Test Metadata Overview

TestCafe allows you to specify additional information for tests in the form of key-value metadata.
You can display this information in the reports and use them to filter tests. We can also define metadata for fixture.meta or test.meta methods.

On the fixture level, we can add meta for example, fixtureID or ticketID or taskID, and then adding the value here.

```javascript
fixture `My fixture`
    .meta('fixtureID', 'f-0001')
```

Also, we can add the author for the test with the name and the creation date (key and value.).

```javascript
fixture `My fixture`
    .meta('fixtureID', 'f-0001')
    .meta({ author: 'John', creationDate: '05/03/2018' });
```

#### Metadata with fixture and test

In the following example, we set a fixture version and the version number is 1, also we defined the production environment in the test meta level.

```javascript
fixture.meta('version','1')("First Fixture")
    .page("http://devexpress.github.io/testcafe/");

test.meta('env','production')
.page("https://devexpress.github.io/testcafe/example/")
("First Test", async t =>{
    await t
        .typeText("#developer-name","TAU")
        .click("#macos")
        .click("#submit-button");
});
```

You can run the test with specific metadata as following.

```
testcafe chrome tests/testMetaScript.js --test-meta env=production
```


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.2](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.2.html)

   
