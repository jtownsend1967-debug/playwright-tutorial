# Write a test for the Playwright Developer page
The [Playwright Developer page](https://playwright.dev/) has many elements. Let's create a test for each element and run those tests.

## The basics
Create a new test file. Be sure to follow Playwright naming conventions. For example, `test-playwright-dev.spec.ts`. Added descriptive comments as you go. At the top of the file import the Playwright modules you want to use:
`import { test, expect } from '@playwright/test';`

## Create a convenience test
Instead of telling each test to open the test page, you can create a beforeEach test that is automatically run before each test. Not only does this save time typing, if the page address changes you only need to change it in one place. This a good practice to develop. Always thing of ways to code efficiently (and make updates easier).

Add this code to the test file:
```
// Define a test that runs before each test case
test.beforeEach(async ({ page }) => {
  // Navigate to the Playwright Developer page
  await page.goto('https://playwright.dev/');
});
```
## Create a test for the page title
The title of the page is `Playwright enables reliable end-to-end testing for modern web apps`. Let's create a test for that element. If you haven't already, read the [documentation on identifying page elements](Identify Browser Elements.md).

1 Use `Pick locator` and click the text at the top of the page: `Playwright enables reliable end-to-end testing for modern web apps`. If you have  `Copy on pick` selected, Playwright will copy the element information to the clip board.
2 Create a new test:
```test('Verify Playwright Developer page header', async ({ page }) => {
  const header = page.getByRole('heading', { name: 'Playwright enables reliable end-to-end testing for modern web apps.' });
  await expect(header).toBeVisible();
});
```

### Solve the header test failure
The first time I wrote the header test, it failed with:
```
    Locator: getByRole('heading', { name: '/Playwright Developer/' })
    Expected: visible
    Timeout: 5000ms
    Error: element(s) not found
```
The test I originally wrote was:
```
test('Verify Playwright Developer page header', async ({ page }) => {
  const header = page.getByRole('heading', { name: '/Playwright Developer/' });
  await expect(header).toBeVisible();
});
```
I got the test working by using the correct/full name of the header which I got from the browser Developer tools.
```
test('Verify Playwright Developer page header', async ({ page }) => {
  const header = page.getByRole('heading', { name: 'Playwright enables reliable end-to-end testing for modern web apps.' });
  await expect(header).toBeVisible();
});
```
For me, I learn more from test failures than any other process. The hardest part of test development is not writing the tests but figuring out why they don't work!

## Verify the Get Started button
The next element of the page is the `Get Started` button.

For this test we want to verify that the button exists and clicking it goes to the correct URL.
1 Create a new test for the `Get Started button`:
```
test('Verify "Get Started" button functionality', async ({ page }) => {
  const getStartedButton = page.getByRole('link', { name: 'Get Started' });
  await expect(getStartedButton).toBeVisible();
  await getStartedButton.click();
  await expect(page).toHaveURL('https://playwright.dev/docs/intro');
});
```
The test starts by assigning the attributes of the `Get Started` button to a variable, in this case `getStartedButton`. It is a good practice to use variables in this way. It saves typing and if the information needs to change, you only need to change it in one place.
The next test line verifies that the button is visible. If the button was not visible, it could indicate a problem with this page. Usually tests need to verify that the thing exists and it does what is is supposed to do.
Once you have verified that the button is visible, the test clicks the button. Followed by verify the button does the correct thing: in this case, go to the provided URL.


### Solve the Get Started button failure.
The first time I wrote the test, the test failed:
```
  1 failed
    [chromium] › tests\test-playwright-dev.spec.ts:19:5 › Verify "Get Started" button functionality 
```

This test failed:
```
test('Verify "Get Started" button functionality', async ({ page }) => {
  const getStartedButton = page.getByRole('link', { name: 'Get Started' });
  await expect(getStartedButton).toBeVisible();
  await getStartedButton.click();
  await expect(page).toHaveURL(/.*getting-started/);
});
```
I fixed the problem by changing the `toHaveURL` statement to:
```
await expect(page).toHaveURL('https://playwright.dev/docs/intro');
```
The full, working test, is:
```
test('Verify "Get Started" button functionality', async ({ page }) => {
  const getStartedButton = page.getByRole('link', { name: 'Get Started' });
  await expect(getStartedButton).toBeVisible();
  await getStartedButton.click();
  await expect(page).toHaveURL('https://playwright.dev/docs/intro');
});
```
