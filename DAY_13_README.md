# Day 13 - Selenium Automation Framework (POM + TestNG + Utilities + Advanced Handling)

## 📌 Status
✅ Completed (Core Framework + Concepts Practiced)  
⚠️ Reporting verification + final polishing pending

---

## 🎯 Day 13 Objective
Day 13 focused on moving from **basic Selenium scripts** to a structured **Automation Framework**.

The main goal was to build an industry-style framework using:
- **Page Object Model (POM)**
- **TestNG test execution**
- **Reusable utility classes**
- **Configuration handling**
- **Advanced Selenium scenario handling**

This day is important because it teaches how automation is actually implemented in real companies.

---

## 🛠 Tools & Technologies Used
- **Java**
- **Selenium WebDriver**
- **TestNG**
- **Maven**
- **ChromeDriver**
- **Eclipse IDE**
- **GitHub (Version Control)**

---

## 📚 Key Concepts Learned & Implemented

---

# 1️⃣ Page Object Model (POM) Implementation

## ✅ What is POM?
Page Object Model is a Selenium design pattern where each web page is represented as a **Java class**.

That class contains:
- Web element locators (`By`)
- Page actions (methods like click, sendKeys)

## ✅ Why POM is used?
POM makes automation:
- more readable
- reusable
- easy to maintain
- scalable for multiple test cases

## 🔥 Example: LoginPage class structure
- Locators:
  - username textbox
  - password textbox
  - login button
- Methods:
  - enterUsername()
  - enterPassword()
  - clickLogin()

### ✔ POM Rule Followed
- Page classes do NOT contain `main()` method
- Execution should happen only inside TestNG test classes

---

# 2️⃣ Test Layer (TestNG) Implementation

## ✅ What is Test Layer?
Test layer is where we write actual test scenarios such as:
- login flow
- checkout flow
- add to cart flow

These tests call the page methods from POM classes.

## 🧪 Example Flow Automated
Checkout flow implemented using:
- LoginPage
- ProductPage
- CartPage
- CheckoutPage

## 🧠 Why TestNG is used?
TestNG provides:
- annotations (`@Test`, `@BeforeMethod`, `@AfterMethod`)
- assertions
- suite execution using testng.xml
- reporting and listeners support

---

# 3️⃣ BaseTest Design (Framework Foundation)

## ✅ What is BaseTest?
BaseTest is a common class used for:
- launching browser
- initializing WebDriver
- navigating to application URL
- closing browser after execution

This avoids repeating driver setup in every test class.

### Typical BaseTest includes:
- `@BeforeMethod` setup
- `@AfterMethod` teardown

---

# 4️⃣ Configuration Handling (config.properties)

## ✅ What is config.properties?
A `config.properties` file is used to store all reusable configuration data like:
- application URL
- browser name
- credentials
- timeout values

### Example config.properties:
```properties
url=https://www.saucedemo.com
browser=chrome


username=standard_user
password=secret_sauce
timeout=10
