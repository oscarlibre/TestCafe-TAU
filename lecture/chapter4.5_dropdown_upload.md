# Chapter 4.5 - Working with DropDownlist and Upload File

#### How to work with drop-down lists with TestCafe

In this demo, we select the option "Both" from the drop-down list with ID "preferred-interface".


```javascript
import {Selector} from 'testcafe';

const interfaceSelect = Selector('select#preferred-interface');
const interfaceOptions = interfaceSelect.find('option');

fixture("Select element from Dropdownlist")
.page("https://devexpress.github.io/testcafe/example/");

test('select element test', async t =>{
    await t
    .click(interfaceSelect)
    .click(interfaceOptions.withText('Both'));
});

```

####  How to upload a file with TestCafe

On this example we have one function for uploading files is called *setFilesToUpload()*, it automatically waits until the file is uploaded to the server. 
Also, we need to add the path of the target fil to upload, then we click on the *uploadFileButton*.

```javascript
import { Selector } from 'testcafe';

const fileUpload = Selector('input#file-upload');
const uploadFileButton = Selector('input#file-submit.button');

fixture("File Upload Fixture")
    .page("https://the-internet.herokuapp.com/upload");

test("File Upload test",async t =>{
    await t
        .setFilesToUpload(fileUpload,'../../upload/logo.png')
});
```

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.5](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.5.html)

   
