# Create a test automatically
While you should be comfortable writing a test by hand, you can also record your actions in a Browser and Playwright will translate that into a test. A combination of recorded tests and hand writing tests is  efficient and powerful.

## Record some your interaction with a web page.
1 Create an empty test file. From `PLAYWRIGHT` right-click `tests` and select `New File`. Give the file a descriptive name such as `test-record.spec.ts`.
2 From `Testing`, the test tube icon, look for `Record new` under `TOOLS`. A browser should now open. Note: this is not your default browser but a browser connected to Playwright. Enter the URL `http://www.uitestingplayground.com/click`.
3 Click the button, reload the page and click the button again.
4 Click the red stop button at the top of the browser page.

You should now have a test that looks like this:
```
import { test, expect } from '@playwright/test';

test('test', async ({ page }) => {
  await page.goto('http://www.uitestingplayground.com/click');
  await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click();
  await page.goto('http://www.uitestingplayground.com/click');
  await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click();
});
```
Right-click the green checkbox and select `Run test'. Does the test run without errors? Once you have the basic steps recorded you can use the code as is or modify it with, for example, some error handling.
