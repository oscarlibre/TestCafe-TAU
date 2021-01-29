# Chapter 6.2 - Debugging

#### The Debug Mode with TestCafe

In this mode, test execution is paused before the first action or assertion so that you can invoke the developer tools and the debug.
When the test execution reaches t.debug that we added already in our test, it pauses so that you can open the browser's developer tools and check the page state, DOM elements, location, their CSS, and more.
The footer displays a status report in which you can resume as test execution or skip to the next action or assertion.
For example, here we can click Resume to continue the test, Next Step, and Unlock Page.

![](https://testautomationu.applitools.com/course55/chapter6.2-img1.png)

You can also use the Unlock page switch in the footer to unlock the tested page and interact with its elements.

#### Debug Mode on Fail

We can specify to automatically enter the debug mode when a test fails with this command line parameter *--debug-on-fail*.

For example:

```
testcafe chrome tests/sample-fixture.js --debug-on-fail
```

The command line will be testcafe with the browser name, for example, chrome and passing the test file then *--debug-on-fail*.
It will be started in debug mode if the test fails, and after that, we can investigate the reason for the failure.
If this option is enabled, TestCafe pauses the test when it fails - this allows you to view the test pages and determine the cause of failure.
When you are done, click the Finish button in the footer to end the test execution.

#### Example of Debug Mode with TestCafe 

We will open our existing example with *UploadFile.js*.

In this example, we set the file to upload and add the path of the file to this function, then we clear that upload file and set it again, and after that click on the upload button.
Maybe before we click on the upload button, we need, for example, to debug or to check that the file upload already takes a file in the control or the element.
So for example, here, we can add one additional step with debug.

What's the meaning of debugging or what's the description of debugging?. *debug()* pauses the test and switches to the step-by-step execution mode.

So here we are getting into our debug mode with TestCafe.

We will select debug and then we will add parentheses because this is a function.

```javascript
import { Selector } from 'testcafe';

const fileUpload = Selector('input#file-upload');
const uploadFileButton = Selector('input#file-submit.button');

fixture("File Upload Fixture")
    .page("https://the-internet.herokuapp.com/upload");

test("File Upload test",async t =>{
    await t
        .setFilesToUpload(fileUpload,'../../upload/logo.png')
        .clearUpload(fileUpload)
        .setFilesToUpload(fileUpload,'../../upload/logo.png')
        .debug()
        .click(uploadFileButton);
});
```

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 6.2](https://testautomationu.applitools.com/testcafe-tutorial/chapter6.2.html)

   
