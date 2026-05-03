# 🔐 Day 16 — Security Testing Basics

![Security Testing](https://img.shields.io/badge/Security-Testing-red)
![OWASP](https://img.shields.io/badge/OWASP-Top%2010%202021-blue)
![ZAP](https://img.shields.io/badge/OWASP-ZAP%202.17.0-green)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> **Day 16 of 30-Day QA Testing Challenge**  
> Topic: Security Testing Basics using OWASP ZAP, Chrome DevTools & Manual Testing

---

## 📌 What I Learned Today

- ✅ What security testing is and why it matters
- ✅ Security testing vs functional testing
- ✅ Types of security testing (Vulnerability Scan, Pentest, Audit, Risk Assessment)
- ✅ Tester's role in security — threat modeling, abuse cases, shift-left
- ✅ OWASP Top 10 (2021) — all 10 vulnerabilities explained
- ✅ Common vulnerabilities — SQLi, XSS, CSRF, Broken Auth, Data Exposure, Misconfiguration
- ✅ Basic security tests — Auth, Authorization, Input Validation, Session, Error Handling, HTTPS
- ✅ Security testing tools — OWASP ZAP, Burp Suite, SQLMap, Nikto
- ✅ How to run automated scan with OWASP ZAP
- ✅ How to check cookie flags and security headers using DevTools

---

## 🛠️ Tools & Technologies

| Tool | Version | Purpose |
|------|---------|---------|
| OWASP ZAP | 2.17.0 | Automated security scanner |
| Chrome DevTools | Built-in | Cookie flags & security headers |
| Manual Testing | — | Auth, XSS, SQL injection payloads |
| demo.testfire.net | — | Deliberately vulnerable demo banking app |

---

## 📚 Concepts Covered

### Security Testing vs Functional Testing

| Aspect | Functional Testing | Security Testing |
|--------|-------------------|-----------------|
| Question | Does it work? | Can it be exploited? |
| User mindset | Normal user | Malicious attacker |
| Scenarios | Happy path, error cases | Abuse cases, attack vectors |
| Goal | Features work correctly | System cannot be compromised |

> 💡 A feature can work perfectly functionally but still be insecure. Both are always needed together!

---

### OWASP Top 10 (2021)

| ID | Vulnerability | Severity | One-line Summary |
|----|--------------|----------|-----------------|
| A01 | Broken Access Control | 🔴 Critical | Users access unauthorized resources or data |
| A02 | Cryptographic Failures | 🔴 Critical | Sensitive data exposed — weak/missing encryption |
| A03 | Injection (SQL, XSS) | 🔴 Critical | Malicious code via unsanitized inputs |
| A04 | Insecure Design | 🟠 High | Security flaws baked into architecture |
| A05 | Security Misconfiguration | 🟠 High | Insecure defaults, missing headers |
| A06 | Vulnerable Components | 🟠 High | Outdated libraries with known vulnerabilities |
| A07 | Authentication Failures | 🔴 Critical | Broken login, session, credential management |
| A08 | Software & Data Integrity | 🟠 High | No verification of updates or data integrity |
| A09 | Logging & Monitoring Failures | 🟡 Medium | Breaches go undetected — no logging |
| A10 | Server-Side Request Forgery | 🟠 High | Server fetches internal resources for attacker |

---

### Common Vulnerabilities

#### 1. SQL Injection (SQLi)
```
Normal:  SELECT * FROM users WHERE username='john' AND password='abc'
Attack:  username = ' OR '1'='1
Result:  Always true → Login bypassed without valid credentials!
```
- **Where:** Login forms, search boxes, URL parameters, API endpoints
- **Test payload:** `' OR '1'='1`
- **OWASP:** A03

#### 2. Cross-Site Scripting (XSS)
```
Payload:  <script>alert(document.cookie)</script>
Result:   Script saved in DB → runs in every visitor's browser → cookies stolen!
```
- **Where:** Comment sections, search boxes, profile fields
- **Test payload:** `<script>alert(1)</script>`
- **OWASP:** A03

#### 3. Cross-Site Request Forgery (CSRF)
```
1. You are logged into bank (session cookie active)
2. Attacker's site has: <img src="bank.com/transfer?to=attacker&amt=5000">
3. Browser sends request WITH your session cookie → money transferred!
```
- **Test:** Remove CSRF token → resubmit → if it works = vulnerable
- **OWASP:** A01

#### 4. Broken Authentication
- No rate limiting → brute force attack possible
- Session not invalidated after logout
- Weak passwords accepted (123456, password)
- **OWASP:** A07

#### 5. Sensitive Data Exposure
- Passwords stored in plain text or weak MD5 hash
- Sensitive data transmitted over HTTP
- API returns more data than needed
- **OWASP:** A02

#### 6. Security Misconfiguration
```
Missing security headers to always check:
✅ X-Frame-Options          → prevents clickjacking
✅ Content-Security-Policy  → prevents XSS
✅ Strict-Transport-Security → enforces HTTPS
✅ X-Content-Type-Options   → prevents MIME sniffing
```
- **OWASP:** A05

---

## 🧪 Test Execution Results

**Target:** http://demo.testfire.net (Altoro Mutual — HCL Technologies deliberately vulnerable demo site)  
**Total Executed:** 11 | **Passed:** 6 | **Failed:** 5 | **Pass Rate:** 55%

### Authentication Tests

| Test Case ID | Title | Tool | Status | Result |
|-------------|-------|------|--------|--------|
| TC-AUTH-001 | Valid login with correct credentials | Manual | ✅ PASS | Logged in and redirected to dashboard |
| TC-AUTH-002 | Login rejected with invalid credentials | Manual | ✅ PASS | Error message appeared |
| TC-AUTH-003 | Account lockout after 5 failed attempts | Manual | ❌ FAIL | Account NOT locked — brute force possible! |

### Input Validation Tests

| Test Case ID | Title | Tool | Status | Result |
|-------------|-------|------|--------|--------|
| TC-INPUT-001 | SQL injection in login form | Manual | ✅ PASS | Login rejected with SQL payload |
| TC-INPUT-003 | XSS in search box | Manual | ❌ FAIL | Alert popup appeared — XSS confirmed! |

### Session Management Tests

| Test Case ID | Title | Tool | Status | Result |
|-------------|-------|------|--------|--------|
| TC-SESSION-004 | Cookie HttpOnly flag | DevTools | ✅ PASS | HttpOnly flag enabled ✅ |
| TC-SESSION-005 | Cookie Secure flag | DevTools | ✅ PASS | Secure flag enabled ✅ |
| TC-SESSION-006 | Cookie SameSite flag | DevTools | ✅ PASS | SameSite = Medium ✅ |

### Security Misconfiguration Tests

| Test Case ID | Title | Tool | Status | Result |
|-------------|-------|------|--------|--------|
| TC-MISCONFIG-001 | X-Frame-Options header | DevTools | ❌ FAIL | Header missing! |
| TC-MISCONFIG-002 | Content-Security-Policy header | DevTools | ❌ FAIL | Header missing! |
| TC-MISCONFIG-003 | Strict-Transport-Security header | DevTools | ❌ FAIL | Header missing! |

---

## 🚨 Security Findings

| # | Finding | Severity | OWASP | Recommendation |
|---|---------|----------|-------|----------------|
| 1 | No account lockout after failed logins | 🔴 Critical | A07 | Implement lockout after 5 failed attempts |
| 2 | XSS confirmed in search box | 🟠 High | A03 | Sanitize all inputs server-side. Add CSP header. |
| 3 | X-Frame-Options header missing | 🟡 Medium | A05 | Add `X-Frame-Options: DENY` to all responses |
| 4 | Content-Security-Policy missing | 🟡 Medium | A05 | Implement strict Content-Security-Policy header |
| 5 | Strict-Transport-Security missing | 🟡 Medium | A05 | Add HSTS header to enforce HTTPS |

---

## ⚡ OWASP ZAP — How I Used It

### What is ZAP?
ZAP sits between your browser and the web app — recording all traffic and scanning for vulnerabilities automatically.

```
Without ZAP:  Browser → Internet → Website
With ZAP:     Browser → ZAP → Internet → Website
                          ↓
                  Scans every request & response
                  Reports vulnerabilities in Alerts tab
```

### Running Automated Scan
```
1. Open OWASP ZAP 2.17.0
2. Quick Start → Automated Scan
3. URL to attack: http://demo.testfire.net
4. Click Attack
5. Wait 15-20 minutes
6. Review Alerts tab → High / Medium / Low / Info
7. Report → Generate Report → HTML
```

### Passive vs Active Scan

| | Passive Scan | Active Scan |
|--|-------------|-------------|
| What | Watches traffic only | Sends attack payloads |
| Risk | Zero | Low (test sites only!) |
| Speed | Fast | Slow but thorough |
| When | Always safe | Test environments only |

---

## 📊 Overall Security Coverage

| Area | Test Cases Written | Executed | Pass | Fail |
|------|-------------------|----------|------|------|
| Authentication | 8 | 3 | 2 | 1 |
| Authorization | 6 | 0 | — | — |
| Input Validation | 8 | 2 | 1 | 1 |
| Session Management | 6 | 3 | 3 | 0 |
| Misconfiguration | 4 | 3 | 0 | 3 |
| **Total** | **32** | **11** | **6** | **5** |

---

## 📁 Project Structure

```
Day16-Security-Testing/
│
├── 📄 README.md                           ← You are here
│
├── 📋 Documents
│   ├── OWASP_Top10_Understanding.docx     ← All 10 vulnerabilities explained
│   ├── Security_Test_Cases.docx           ← 32 test cases with steps & expected results
│   └── Security_Testing_Checklist.docx   ← 76-item security verification checklist
│
├── 🧪 Test Execution
│   └── Security_Test_Execution.xlsx       ← Executed test cases with Pass/Fail & evidence
│
└── 📊 ZAP Scan Results
    └── ZAP_Scan_Report.html               ← OWASP ZAP automated scan report
```

---

## ⚙️ How to Run These Tests

### Prerequisites
```bash
# Download OWASP ZAP
https://www.zaproxy.org/download/

# No installation needed for target site
http://demo.testfire.net

# Demo credentials
Username: jsmith
Password: Demo1234
```

### Running ZAP Automated Scan
```
1. Open OWASP ZAP
2. Select "No" when asked to persist session → Click Start
3. Click "Automated Scan" in Quick Start tab
4. Enter URL: http://demo.testfire.net
5. Click "Attack" and wait for scan to complete
6. Review findings in Alerts tab
7. Generate HTML report: Report → Generate Report
```

### Checking Cookie Flags (DevTools)
```
1. Open browser → navigate to demo.testfire.net → login
2. Press F12 → Application tab
3. Storage → Cookies → click site domain
4. Check flags: HttpOnly ✅ | Secure ✅ | SameSite ✅
```

### Checking Security Headers (DevTools)
```
1. Press F12 → Network tab
2. Refresh page (F5)
3. Click first request in the list
4. Check Response Headers section
5. Look for: X-Frame-Options, CSP, HSTS, X-Content-Type-Options
```

> ⚠️ **Important:** Only run security tests on applications you own or have **explicit written permission** to test. Never test production or third-party systems!

---

## 💡 Key Lessons Learned

1. **Security ≠ separate from QA** — security testing is part of every tester's job
2. **XSS confirmed on demo site** — `<script>alert(1)</script>` in search triggered alert
3. **No account lockout = Critical bug** — brute force attack possible on demo.testfire.net
4. **Cookie flags matter** — HttpOnly + Secure + SameSite correctly set = good practice
5. **Missing security headers** — 3 critical headers missing = easy misconfiguration finding
6. **ZAP finds in minutes** what would take a manual tester days
7. **Tester's mindset shift** — functional tester asks "does it work?" security tester asks "can it be broken?"

---

## 🗓️ Challenge Progress

| Day | Topic | Status |
|-----|-------|--------|
| Day 13 | API Testing | ✅ Done |
| Day 14 | API Automation | ✅ Done |
| Day 15 | Performance Testing | ✅ Done |
| **Day 16** | **Security Testing Basics** | ✅ Done |
| Day 17 | Advanced Security Testing | 🔜 Next |

---

## 🔗 Resources

- [OWASP Top 10](https://owasp.org/Top10/)
- [OWASP ZAP Official Docs](https://www.zaproxy.org/)
- [Altoro Mutual Demo Site](http://demo.testfire.net)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security)
- [SSL Labs SSL Test](https://www.ssllabs.com/ssltest/)
- [Security Headers Checker](https://securityheaders.com/)

---


