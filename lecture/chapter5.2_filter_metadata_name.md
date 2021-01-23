# Chapter 5.3 - Filter Tests by Metadata and Name

#### Filter Tests and Fixtures By Metadata Overview

It is possible to run tests whose metadata contains specific values by using the *--test-meta* argument to do this.

For example:


```
testcafe chrome ./my-tests/ --test-meta device=mobile,env=production
```

Or by the fixture metadata:

```
testcafe chrome ./my-tests/ --fixture-meta device=mobile,env=production
```


####  Filter Tests and Fixtures By Name Overview

One additional feature from TestCafe that we can use is the *-t* or *--test* command line argument, or in the *runner.filter* method  if we have a runner class to run a test by name.

For example:

```
testcafe safari ./tests/samplefixture.js -t "Click a label"
```

If we have a runner class, we can add the browser name, the source of the file that we need to run.

And here also, we can specify .filter and add as a test name the value as a string.

And then we can add *.run()*.

Here is an example:

```javascript
await runner
    .browsers('safari')
    .src('./tests/samplefixture.js')
    .filter(testName => testName === 'Click a label')
    .run();
```

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 5.3](https://testautomationu.applitools.com/testcafe-tutorial/chapter5.3.html)

   
