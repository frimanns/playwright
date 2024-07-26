# Playwright and Python

I have experienced that the following works best using PowerShell

# Installation


First, you need to install Playwright and the necessary browser binaries

```markdown
pip install playwright  
 playwright install  
```


# Basic Usage

```python

from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    page = browser.new_page()
    page.goto("https://example.com")
    print(page.title())
    browser.close()


```

# Asynchronous Usage
If you prefer using async/await, you can do so as well:

```python
import asyncio
from playwright.async_api import async_playwright

async def main():
    async with async_playwright() as p:
        browser = await p.chromium.launch(headless=False)
        page = await browser.new_page()
        await page.goto("https://example.com")
        print(await page.title())
        await browser.close()

asyncio.run(main())

```

# Running Tests
Playwright can also be used with Pytest for writing tests. Install the Pytest plugin


```python
pip install pytest-playwright

```
Create a test file, for example, test_example.py:

```python
from playwright.sync_api import Page, expect

def test_example(page: Page):
    page.goto("https://example.com")
    expect(page).to_have_title("Example Domain")

```

Run your tests with:

```python
pytest
```

