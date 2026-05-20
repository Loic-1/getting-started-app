# Instructions

- Following Playwright test failed.
- Explain why, be concise, respect Playwright best practices.
- Provide a snippet of code with the fix, if possible.

# Test info

- Name: workflow.spec.js >> has title
- Location: e2e\workflow.spec.js:3:5

# Error details

```
Error: page.goto: SSL_ERROR_UNKNOWN
Call log:
  - navigating to "https://localhost:3000/", waiting until "load"

```

# Page snapshot

```yaml
- generic [ref=e2]:
  - generic [ref=e3]:
    - heading "Secure Connection Failed" [level=1] [ref=e5]
    - paragraph [ref=e6]: An error occurred during a connection to localhost:3000. SSL received a record that exceeded the maximum permissible length.
    - paragraph [ref=e7]: "Error code: SSL_ERROR_RX_RECORD_TOO_LONG"
    - list [ref=e9]:
      - listitem [ref=e10]: The page you are trying to view cannot be shown because the authenticity of the received data could not be verified.
      - listitem [ref=e11]: Please contact the website owners to inform them of this problem.
    - paragraph [ref=e12]:
      - link "Learn more…" [ref=e13] [cursor=pointer]:
        - /url: https://support.mozilla.org/1/firefox/150.0.2/WINNT/en-US/connection-not-secure
  - button "Try Again" [active] [ref=e15]
```

# Test source

```ts
  1 | import {test, expect} from '@playwright/test';
  2 | 
  3 | test('has title', async ({ page }) => {
> 4 |   await page.goto('https://localhost:3000/');
    |              ^ Error: page.goto: SSL_ERROR_UNKNOWN
  5 | 
  6 |   // Expect a title "to contain" a substring.
  7 |   await expect(page).toHaveTitle(/Todo App/);
  8 | });
```