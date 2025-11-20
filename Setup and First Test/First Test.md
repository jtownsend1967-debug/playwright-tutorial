# Run your first test
Even if you don't know Typescript yet or understand the different kinds of browser elements, you can still run the provided sample test (``example.specs.ts).

From the `Explorer` (View->Explorer) you can see the Playwright files that VS Code created. Look for a file called `example.spec.ts` (A TypeScript file) and double click it.

## First test breakdown
While this first test is very simple, it give a good overview of what Playwright tests look like.

`import { test, expect } from '@playwright/test';` This line tells VS Code to use the `test` and `expect` components from Playwright. This is a common start for pretty much any script. There are bits and pieces that Playwright provides and you need to tell VS Code which one's you want to use.

`test('has title', async ({ page }) => {}` Each Playwright test is a TypeScript function. In this case, the test is called `has title`. This is just a label for this test. It does not control how or what the test does but you should get in the habit of using descriptive test names. The test itself is between the two parentheses `()`.

` console.log('Navigating to Playwright website');` This line sends a message to the VS Code Test Results terminal. It does not affect the how the test is run but like the title provides basic information about the tests. Sending messages to the terminal can be really useful for investigating test failures. 

`await page.goto('https://playwright.dev/');` You will need to tell Playwright what browser page you want to go to. This is the same information that you enter into a browser address or URL bar. Note the use of `await`. You don't want to try to rum the test until the browser gets to the requested page. Think wait until when you see `wait`.

`// Expect a title "to contain" a substring.` The `//` means that this line is a comment. Playwright will completely ignore comments. They are strictly for humans reading your code. I tend to use lots of comments. It really helps when you come back to code that you haven't look at in awhile. Note: keep your comments PG-rated. I have often come across comments that were meanspirited and not appropriate for work.

`await expect(page).toHaveTitle(/Playwright/);` This is the actual test. Note the use of `await` (i.e. wait until) and `expect`, which was imported at the top of the script. `expect` is what you are testing for at this stage of the test. Real-world test will have multiple `expect` statements. Each test needs at least one. In this case, the test will pass if the page contains the text `Playwright`. Note the use of `/` before and after `Playwright`. The forward slashes indicates that this is a regular expression. Regular expressions (often called reg ex) is a way to flexibly search for text and numbers.

## Setting up the browser
Before you can run a test, you need to tell Playwright which browser to run.

1 Select the test tube icon on the left. It will say `Testing` if you hover over the icon.
2 Look for the section called `PLAYWRIGHT`. You will see sections called `TOOLS`, `Projects`, `SETUP` etc.
3 Under `PROJECTS` select `chromium`. This is a test version of the Chrome browser.
4 Under `SETTINGS` make sure `Show browser` is unchecked. Playwright does not actually need to display a browser to run a test. It won't affect the test to show the browser but leave it off for simplicity.

## Run the test
1 From `example.spec.ts` look for a green arrow or green checkbox next to `test('has title', async ({ page }) => {}`.
2. Click the arrow of checkbox.
3. If everything worked correctly, you should see `1 passed` in the `TEST RESULTS` terminal. You will also see the test results in the `TEST EXPLORER`.

You can run all the tests in `example.spec.ts` by either clicking each green arrow or checkbox in the code or by clicking the green arrow or green checkbox in `TEST EXPLORER`.

