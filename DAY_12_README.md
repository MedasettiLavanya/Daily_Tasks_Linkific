# Day 12 - Selenium WebDriver Basics (Java)

 Status
 Approved

---

Learning Objectives
- Understand Selenium WebDriver fundamentals
- Learn how to locate web elements using different locator strategies
- Perform basic user actions (click, sendKeys, clear, getText, etc.)
- Handle different element types (checkbox, radio, dropdown, links, images)
- Build basic automation flows like login and add-to-cart

---

 Topics Covered

Selenium WebDriver Setup
- Imported Selenium libraries in Maven project
- Initialized WebDriver (ChromeDriver)
- Opened browser using Selenium
- Navigated to a URL using `driver.get()`
- Understood:
  - `driver.close()` → closes current browser window
  - `driver.quit()` → closes all windows and ends session

---
 Locators Learned (All Types)
Selenium locators used to identify web elements:

| Locator Type | Example |
|------------|---------|
| By ID | `By.id("username")` |
| By Name | `By.name("password")` |
| By Class Name | `By.className("btn")` |
| By Tag Name | `By.tagName("input")` |
| By Link Text | `By.linkText("Login")` |
| By Partial Link Text | `By.partialLinkText("Log")` |
| By CSS Selector | `By.cssSelector("input#user-name")` |
| By XPath | `By.xpath("//button[@id='login-button']")` |

---

 Locator Strategy Rules Followed
- Preferred **ID** locator whenever available
- Used **CSS Selector** for faster and stable element selection
- Used **Relative XPath** instead of Absolute XPath
- Avoided unstable locators whenever possible

---

 WebElement Actions Practiced
The following WebDriver actions were practiced:

- `sendKeys()` → Enter input text
- `click()` → Click button/link
- `clear()` → Clear input field
- `getText()` → Fetch visible text
- `getAttribute()` → Fetch attribute value
- `isDisplayed()` → Check visibility
- `isEnabled()` → Check enabled state
- `isSelected()` → Check checkbox/radio selected status

---

- Select specific option

### ✔ Dropdown
Handled using `Select` class:
```java
Select s = new Select(driver.findElement(By.id("dropdown")));
s.selectByVisibleText("Option 1");
