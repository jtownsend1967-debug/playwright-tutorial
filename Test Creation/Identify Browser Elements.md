# Identify Browser Elements
To create a Playwright test you need to understand what is on the page you are testing. A web page can contain static text, images, buttons etc. To create tests you will need the details of every element you want to test.

## Manual examine a web page
To get started, examine a [simple web page](http://www.uitestingplayground.com/click). Look over the page and note the elements on the page. What is something that you can click on? Is there any images on the page? Is there any static (caN't be clicked) on the page?

Your browser can give you details about each item on the page. You can use this information to select buttons, links etc. 

1 In the upper right of the browser, select the three dots. From the list select More tools->Developer tools. The browser will open new windows to the right of the page you are viewing. If you are familiar with HTML, you will see that code by clicking the `Elements` tab.
2 To the left of `Elements`, click `Select an element on the page to inspect it`.
3 Hover over the button in the middle of the page.

Among other information, the pop-up shows the name of the button: `Button That Ignores DOM Click Event`. You could use this name when creating a Playwright test that clicks this button. Hover over the `UITAP` link at in the top left of the page. Note the role is listed as `link`. Hover over each element and note the information provided.

## Use Pick locator
While manually investigating UI elements is a useful skill, Playwright can grab the relevant information and copy it to a test file.

1 From the Playwright tools, select `Pick locator`. Navigate to this [simple web page](http://www.uitestingplayground.com/click).
2 Once Playwright has launched the browser, click the `Button That Ignores DOM Click` button.
3 In the PLAYWRIGHT console in VS Code, you should see `getByRole('button', { name: 'Button That Ignores DOM Click' })`

Note this is the same information you saw using the browser development tools but for convenience, the information is copied to VS Code.
