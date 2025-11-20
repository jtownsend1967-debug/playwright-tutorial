# What should you know before working with Playwright?
Before stating your Playwright journey you should have basic knowledge of at least on scripting language and understand the elements of a browser page.

## What Scripting Language?
Familiarity with any scripting language will get you started with Playwright. While Playwright is most-often written with the TypeScript language, scripting languages are similar as are basic programming concepts.

If you are already familiar with basic programming concepts such as variables, iteration, logic statements, data structures and functions you should be able to pick up TypeScript. Almost every scripting tutorial will assume that you already know basic programming concepts. Work through some on-line tutorials and make sure you understand these basic concepts. Look for a tutorial that allows you to write code directly in the browser.

If you are starting from scratch with scripts, you might as well start with TypeScript. It is a in demand language and extremely useful. Other popular scripting languages are Python and JavaScript. TypeScript and JavaScript are very similar so any JavaScript experience will be an advantage.

## Browser Elements
If you have ever used a browser then you have seen seen the different kinds of UI elements.
* Buttons such as login, submit or continue.
* Text and number fields. Blank boxes where you an type words or number. E.g. a password or user name.
* Images such a corporate logos.
* Static text such as instructions, warranties and end user agreements.
* Drop down menus that allow you to pick for a set list.
* Check boxes that let you select between one or more items.
* Radio buttons that let you select a single item from a list

## VS Code
VS Code, a free development environment from Microsoft, is used by many companies for many scripting projects. All of the lessons and information I provide assumes a basic knowledge of VS Code.

### VS Code Extensions
Before you can create or run any Playwright tests, you need to install the required VS Code Extensions.

1 On the left side of the VS Code window, look for the gear icon. It will say `Manage` if you hover over it.
2 Click the gear icon and select `Extensions`.
3 Search for `Playwright` and install the official Microsoft extensions.

For my setup, I installed:
* Playwright Test for VSCode (with Assertion)
* Playwright Code Snippets
* Playwright Test for VSCode
* Playwright Snapshot Helpers
* Rayrun Playwright Test Snippets
* Playwright Test Runner

With these extensions I was able to run my first (simple) Playwright test. I suggest you start with these extensions. Once you have some familiarity with Playwright you may want to install other VS Code extensions.

One tip: do not rely on AI tools. While helpful, you will learn more by figuring it out yourself.

### Playwright VS Code Setup.
1 From the VS Code Command Palette (View->Command Palette) type `Test: Install Playwright' and hit enter.
2 Select thr three web browser options (Chromium, Firefox and WebKit).
3 Leave `Use JavaScript' unchecked. Instead, VS Code will use Typescript.
4 Select `Add Github Actions recipe` and hit enter.
