
# Debugging a test and error handling.
For this exercise we will build on the first-test-from-scratch test:

```
import { test, expect } from '@playwright/test';


test('test', async ({ page }) => {
  await page.goto('http://www.uitestingplayground.com/click');
  await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click();
});
```
## Error Handling
Tests will fail and when that happens you want to handle that failure gracefully and provide some information about how the test failed. Using error handling for all tests is a good habit to get into. It will save lots of frustration latter.

Error handling, typically called try/catch tells your test what to try and what to do if the test fails.

Modified with try/catch, the first-test-from-scratch test becomes:
```
test('test', async ({ page }) => {
  await page.goto('http://www.uitestingplayground.com/click');
  try {
    await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click({ timeout: 0 });
  } catch (e) {
    console.log('Final click failed');
  }
});
```
Try the test and make sure it runs.

## Break the test
A great way to get experience fixing a broken test is to intentionally breaking a working test.

In the test, change `Button That Ignores DOM Click'` to  `Checkbox That Ignores DOM Click'`. 

Run the test. It should eventually fail with `Final click failed`TEST RESULTS`.

In this example, the failures is pretty easy to spot since you just created the bug!

Often troubleshooting a test failure is more complicated. This is where debugging comes in.

## Debugging a failing test
Debugging allows you to walk through each line of code, step by step.

1 To the left of `await page.goto('http://www.uitestingplayground.com/click');`, to the left of line number `5`, click. You should now see a red dot at that line number. This tells VS Code where to start stepping through the code.
2 Right-click on the red X icon to the left of the test and select `Add Breakpoint` There should now be a red dot next to the line number.
3 Right-click the red X and select `Debug Test`.

The test should start to run then stop at line 5. A simple check at this point is to copy/past `http://www.uitestingplayground.com/click` into a browser and make sure the page loads. Alternatively, you can control+click the URL in VS Code and it will open in your default browser.

If the correct page opened then it is not that line that failed. To go to the next line, select Run->Step Over. VS Code will skip over `try` and stop at `await page.getByRole('button', { name: 'Checkbox That Ignores DOM Click' }).click({ timeout: 0 });`. Since you already have the page open, is there a button called `Checkbox That Ignores DOM Click`? The button is actually called `Button That Ignores DOM Click`.

Select Run->Stop Debugging to stop the test now that you found the error. Fix the name of the button and run the test again to verify it now works.

Debugging skills are extremely important and time saving. It is worth the time to get comfortable with debugging your tests. As tests get more complicated, debugging will be your best friend.
