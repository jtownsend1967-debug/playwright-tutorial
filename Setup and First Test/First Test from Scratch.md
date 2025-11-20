# Create a test from scratch
Step by step instructions for creating a test from scratch. This is a very simple test but is a good place to start.

1 From the `PLAYWRIGHT` view, hover over the text `PLAYWRIGHT` and to the right you should see a document icon with a plus sign. 
2 You should see an empty text box under `tests`. Use the name `test-first.spec.ts`. Playwright scripts have a naming convention. File names must end with `.spec.ts` or `.test.ts`. Note: this file name is pretty generic. Get in the habit of using descriptive file names. Hit enter to select the file name.
3 Open the file just created.

## Write the test
1 Create an import statement at the top of the file. This tells Playwright what bits and pieces you want to use. Most test will need, at the very least, `test` and `expect`:

`import { test, expect } from '@playwright/test';`

2 At this point VS Code will prompt you with a ghosted out code suggestion. While code suggestions are really handy, for this exercise just hit Escape whenever VS Code makes a suggestion.
3 Create the test by typing:
```
test('test', async ({ page }) => {

});
```
4 The test steps will go between the parentheses. Add each line below. Make sure each line is indented. It is a good habit to always indent code lines. It makes reading the code much easier:

` await page.goto('http://www.uitestingplayground.com/click');` This tells Playwright which web page to test.
`await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click();` This tells Playwright to click a button called `Button That Ignores DOM Click`.

The final test should look like this:
```
import { test, expect } from '@playwright/test';


test('test', async ({ page }) => {
  await page.goto('http://www.uitestingplayground.com/click');
  await page.getByRole('button', { name: 'Button That Ignores DOM Click' }).click();
});
```

5 Click the green arrow or green checkbox in the file. The test should run and hopefully pass.
