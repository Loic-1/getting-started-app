# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: workflow.spec.js >> has title
- Location: e2e\workflow.spec.js:3:5

# Error details

```
Error: page.goto: SSL connect error
Call log:
  - navigating to "https://localhost:3000/", waiting until "load"

```

# Test source

```ts
  1 | import {test, expect} from '@playwright/test';
  2 | 
  3 | test('has title', async ({ page }) => {
> 4 |   await page.goto('https://localhost:3000/');
    |              ^ Error: page.goto: SSL connect error
  5 | 
  6 |   // Expect a title "to contain" a substring.
  7 |   await expect(page).toHaveTitle(/Todo App/);
  8 | });
```