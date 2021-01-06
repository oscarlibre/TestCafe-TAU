# Chapter 4.4 - Working with iFrames

#### How to work with iFrames and TestCafe

Test steps:

- Open the URL http://the-internet.herokuapp.com/iframe
- Go to inside the iFrame
- Remove the existing content
- Add new content

```javascript
import {Selector} from 'testcafe';

const iframeName = Selector('iframe#mce_0_ifr');
const textArea = Selector('body#tinymce.mce-content-body');

fixture("Iframe Fixutre")
.page("https://the-internet.herokuapp.com/iframe");

test("iFrame test", async t =>{
    await t
        .switchToIframe(iframeName)
        .click(textArea)
        .pressKey('ctrl+a delete')
        .typeText(textArea,'Hello from TAU')
        .expect(textArea.innerText).contains('TAU')
        .switchToMainWindow();
});
```


#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.4](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.4.html)

   
