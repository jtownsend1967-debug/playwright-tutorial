# Setup of VS Code and Playwright
VS Code is a free download from Microsoft. It is supported on Windows and Mac. I'm running VS Code on Windows but the Mac version is very similar. 

## Download VS Code
1 Visit the [VS Code download page](https://code.visualstudio.com/download) and download the appropriate version for your computer.
2 Follow the installation instructions.

If you have ever installed an application, this should be straightforward. You will want the ability to run VS Code from the command line (or Mac terminal). Make sure you select the `Add to PATH option`. You will need to quit and re-open the terminal before you can use VS Code. To verify that VS Code will run from the terminal, type `code` and hit enter. A copy of VS Code should launch.

 ## Setup VS Code for Playwright
The [official Playwright sight](https://playwright.dev/docs/getting-started-vscode) has detailed information about setting up VS Code for Playwright development.

 ### Setup Node.js
[Node.js](https://nodejs.org/en) allows you to run scripts that are typically run in a browser from the command line. You don't need to know much about Node.js to create and run Playwright tests but it does need to be installed and working.

The installation is straightforward but after installation make sure you can run Node.js from the terminal. Type `node -v` and it should show the version of Node.js that you are running.

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

### Playwright VS Code Setup.
1 From the VS Code Command Palette (View->Command Palette) type `Test: Install Playwright' and hit enter.
2 Select thr three web browser options (Chromium, Firefox and WebKit).
3 Leave `Use JavaScript' unchecked. Instead, VS Code will use Typescript.
4 Select `Add Github Actions recipe` and hit enter.
