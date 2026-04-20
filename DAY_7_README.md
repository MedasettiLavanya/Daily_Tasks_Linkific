Day 7 - System Testing & Integration Testing

 Objective
The objective of Day 7 is to understand and perform System Testing and Integration Testing on a real-time demo application.  
Additionally, basic API testing using Postman was performed by executing 10+ REST API requests.

---

 Application Used
SauceDemo Website
https://www.saucedemo.com/

Testing Types Covered

System Testing
System testing was performed to validate the complete application end-to-end in a production-like environment, covering both functional and non-functional scenarios.

Integration Testing
Integration testing was performed to validate the interaction and data flow between modules such as:
- Login Module → Inventory Module
- Inventory Module → Cart Module
- Cart Module → Checkout Module
- Checkout Module → Order Confirmation Module
- Menu Module → Logout Module

API Testing (Postman)
Since SauceDemo does not provide public APIs, API testing was performed using Reqres API (public REST API platform) to practice request/response validation.

API Base URL:  
https://reqres.in/

---

Deliverables Completed

System Test Plan
- Prepared a system test plan document including scope, environment, entry/exit criteria, and testing types.

Integration Test Strategy
- Created integration test strategy document with integration points, approach, and test data.

Integration Test Cases (50+)
- Created and documented 55+ integration test cases covering end-to-end flows.

API Testing with Postman (10+ Requests)
Executed 11 API requests using Postman including:
- GET
- POST
- PUT
- PATCH
- DELETE  
Validated response status codes and JSON response body.

Test Execution Results
Test cases were executed manually and results were recorded with status (Pass/Fail).

Tools Used
- Chrome Browser
- Google Sheets / Excel
- Postman
- GitHub

Test Data Used (SauceDemo)
Valid Credentials:
- Username: `standard_user`
- Password: `secret_sauce`

Invalid User:
- Username: `locked_out_user`
- Password: `secret_sauce`

Summary
Day 7 activities helped in understanding the difference between system testing and integration testing.  
End-to-end workflows were validated on SauceDemo and API testing practice was completed using Postman with Reqres REST API.

---
