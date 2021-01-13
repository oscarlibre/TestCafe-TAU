# Chapter 4.5 - Set Test Speed and Set Page Timeout, Drag and Hover

#### How to change the test speed

The *setTestSpeed()*  function  specifies the speed of the test execution and we are passing the speed as a number, being 1 the fastest speed (the default value), if we add the value 0.01 this is the slowest one.


```javascript
import { Selector } from 'testcafe';

fixture `Speed Test Fixture`
    .page `http://devexpress.github.io/testcafe/example/`;

const nameInput = Selector('#developer-name');

test(`Set Test Speed Test`, async t => {
    await t
        .setTestSpeed(0.1)
        .typeText(nameInput, 'Peter')
        .typeText(nameInput, ' Parker');
});
```

####  How to set the page load timeout

Before navigating, we can call *setPageLoadTimeout()*, which specifies the amount of time within which TestCafe waits for the *window.load* event to fire before starting the test.

```javascript
fixture("Set page timeout Fixture")
    .page("http://devexpress.github.io/testcafe/");

test("set page timeout Test", async t =>{
    await t
    .setPageLoadTimeout(0)
    .navigateTo('http://devexpress.github.io/testcafe/');
});
```


####  How to drag an element to a specific offset using TestCafe

The *drag()* method allows dragging an element to a specific offset using TestCafe. In the following example the offsets X and Y are related to the mouse pointer,
the value 360 is the position and add 0, then add the offsets (offsetX:10 and offsetY:10).

```javascript
import { Selector } from 'testcafe'; 

const triedCheckbox = Selector('label').withText("I have tried TestCafe");
const slider = Selector('#slider'); 

fixture ('Drag Test')
.page('https://devexpress.github.io/testcafe/example/');

test('Drag Testcase', async t =>{
 await t
    .setTestSpeed(0.01)
    .click(triedCheckbox)
    .drag(slider,360,0,{offsetX:10, offsetY:10}); 
});
```


####  How to use hover with TestCafe

The *hover()* method put mouse pointer over a webpage element, so we need to pass the element, in our case  it's an input with the ID "populate".

```javascript
fixture("Hover Fixture")
.page("https://devexpress.github.io/testcafe/example/");

test('Hover test', async t => {
    await t
        .setTestSpeed(0.1)
        .hover('input#populate');
});
```

#### Resources

![TestCafe - Organize Tests](https://devexpress.github.io/testcafe/documentation/guides/basic-guides/organize-tests.html)

![Source chapter 4.6](https://testautomationu.applitools.com/testcafe-tutorial/chapter4.6.html)

   
