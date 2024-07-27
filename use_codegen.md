---
noteId: "f343b6304bf011ef89a8cf13d3d8d8ce"
tags: []

---

# Generating code using Playwright Codegen



1. Install Playwright

```

npm install playwright

```
2. Run Codegen

```

npx playwright codegen
```
This command will open a browser window where you can interact with your web application. As you perform actions, Playwright will generate the code for you.

3. Save the Generated Code: Once you’re done, you can save the generated code to a file and use it in your tests.

Here’s an example of what the generated code might look like.

<b>JavaScript</b>
```JavaScript


const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const context = await browser.newContext();
  const page = await context.newPage();

  // Navigate to the page
  await page.goto('https://example.com');

  // Perform actions
  await page.click('text=Example Link');
  await page.fill('input[name="example"]', 'Hello, Playwright!');

  // Close the browser
  await browser.close();
})();

```

# Codegen in VS Code

[Youtube guide](https://www.youtube.com/watch?v=LM4yqrOzmFE) 

