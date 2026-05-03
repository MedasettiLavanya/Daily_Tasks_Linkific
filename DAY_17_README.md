 Day 17 — Usability & Compatibility Testing

![Usability Testing](https://img.shields.io/badge/Usability-Testing-blue)
![Accessibility](https://img.shields.io/badge/Accessibility-WCAG%202.1-green)
![Cross Browser](https://img.shields.io/badge/Cross--Browser-Testing-orange)
![Responsive](https://img.shields.io/badge/Responsive-Testing-purple)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

> Topic: Usability & Compatibility Testing — Cross-Browser, Responsive, and Accessibility

---

## 📌 What I Learned Today

- ✅ What usability testing is and why it matters
- ✅ 5 usability attributes (Nielsen's model)
- ✅ Usability testing methods — Think-aloud, Task analysis, A/B testing, Heuristic evaluation
- ✅ How to perform cross-browser testing on Chrome, Firefox, and Edge
- ✅ How to test responsive layouts using Chrome DevTools
- ✅ WCAG 2.1 guidelines and accessibility compliance levels
- ✅ How to run accessibility audits using Lighthouse and WAVE
- ✅ How to document all findings in professional test reports

---

## 🛠️ Tools & Technologies

| Tool | Type | Purpose |
|------|------|---------|
| Chrome DevTools | Built-in | Responsive testing + color contrast |
| Lighthouse | Built-in (Chrome) | Full accessibility + performance audit |
| WAVE | Free web tool | Accessibility error detection |
| Chrome | Browser | Primary testing browser |
| Firefox | Browser | Cross-browser layout testing |
| Edge | Browser | Cross-browser compatibility testing |

---

## 🌐 Website Tested

| Detail | Info |
|--------|------|
| Website | [Sauce Demo](https://www.saucedemo.com) |
| Login | Username: `standard_user` / Password: `secret_sauce` |
| Type | E-commerce demo site |
| Purpose | Industry-standard practice site for QA testers |

---

## 📚 Concepts Covered

### 5 Usability Attributes (Nielsen's Model)

| Attribute | Definition |
|-----------|------------|
| 🟦 User-friendliness | How easy it is for new users to accomplish basic tasks |
| 🟩 Ease of learning | How quickly users learn to use the system |
| 🟧 Efficiency of use | How fast experienced users can perform tasks |
| 🟥 Error tolerance | How well the system handles and recovers from errors |
| 🟪 User satisfaction | How pleasant the overall experience feels |

### Usability Testing Methods

| Method | Description |
|--------|-------------|
| Think-aloud protocol | User speaks thoughts while using the product |
| Task analysis | Give users tasks and measure time, clicks, errors |
| A/B testing | Compare two versions to see which performs better |
| Heuristic evaluation | Expert reviews UI against Nielsen's 10 heuristics |
| User surveys | Post-task questionnaires to measure satisfaction |

### WCAG 2.1 Compliance Levels

| Level | Description |
|-------|-------------|
| Level A | Minimum — basic accessibility requirements |
| Level AA | Standard — industry requirement for most websites |
| Level AAA | Highest — hardest to achieve fully |

---

## 🧪 Report 1 — Usability Testing Report

### Usability Checklist

| Checklist Item | Result | Observation |
|----------------|--------|-------------|
| Navigation is intuitive | ✅ Pass | Menu clearly visible, hamburger icon works |
| Clear call-to-action buttons | ✅ Pass | "Add to Cart", "Login", "Checkout" clearly labeled |
| Consistent design across pages | ✅ Pass | Same fonts, colors, layout on all pages |
| Helpful error messages | ❌ Fail | Wrong login error not descriptive or helpful |
| Mobile-friendly layout | ✅ Pass | Tested at 375px, 414px, 768px — no major breakage |
| Fast load times | ✅ Pass | Page loads under 3 seconds on hard refresh |
| Accessible to all users | ✅ Pass | Lighthouse 96/100 — WAVE 0 errors |

### Issues Found

| # | Issue | Severity |
|---|-------|----------|
| 1 | Error messages on login page are not descriptive | 🔴 High |
| 2 | 3 minor WAVE accessibility alerts found | 🟡 Low |
| 3 | Firefox could not be tested — proxy issue on local network | ⚪ Info |

**Overall Rating: Good — 6/7 Passed ✅**

---

## 🌍 Report 2 — Cross-Browser Test Results

| Check Item | Chrome | Firefox | Edge |
|------------|--------|---------|------|
| Layout / alignment | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| Fonts rendering correctly | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| Buttons and links work | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| Images load correctly | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| No JS console errors | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| CSS renders correctly | ✅ Pass | ⚪ Skipped* | ✅ Pass |
| Forms work correctly | ✅ Pass | ⚪ Skipped* | ✅ Pass |

> ⚪ *Firefox skipped due to proxy configuration issue on local network. Documented as environment issue.

---

## 📱 Report 3 — Responsive Testing Matrix

| Check Item | 1920px Desktop | 1366px Laptop | 1024px iPad Land. | 768px iPad Portrait | 414px iPhone XR | 375px iPhone SE |
|------------|:--------------:|:-------------:|:-----------------:|:-------------------:|:---------------:|:---------------:|
| Text readable? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| No horizontal scroll? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Navigation works? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Buttons tappable? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Images not stretched? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Layout not broken? | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Portrait mode ok? | N/A | N/A | ✅ | ✅ | ✅ | ✅ |
| Landscape mode ok? | N/A | N/A | ✅ | ✅ | ✅ | ✅ |

---

## ♿ Report 4 — Accessibility Audit Report

### Lighthouse Score

| Category | Score | Status |
|----------|-------|--------|
| Accessibility | 96 / 100 | ✅ Excellent |
| Passed Audits | All Green | ✅ No critical failures |

### WAVE Results

| Check | Result | Details |
|-------|--------|---------|
| WAVE Errors | 0 | ✅ No errors found |
| WAVE Alerts | 3 | ⚠️ Minor warnings |
| Contrast Errors | 0 | ✅ Color contrast acceptable |
| Keyboard Navigation | ✅ Pass | Tab key navigates correctly |
| Alt text on images | ✅ Pass | Images have alt attributes |
| Form labels | ✅ Pass | Login form labels present |

**WCAG Level Achieved: AA ✅**

---

## 📊 Overall Issues Summary

| Report | Issues Found | Severity |
|--------|-------------|----------|
| Usability | 1 — Unhelpful error messages | 🔴 High |
| Cross-Browser | 0 — No issues on Chrome and Edge | ✅ None |
| Responsive | 0 — All screen sizes passed | ✅ None |
| Accessibility | 3 — Minor WAVE alerts | 🟡 Low |
| **Total** | **4 issues** | — |

---

## ⚙️ How to Reproduce the Tests

### Cross-Browser Testing
```
1. Open https://www.saucedemo.com in Chrome, Firefox, Edge
2. Login: username = standard_user / password = secret_sauce
3. Check layout, buttons, images, and console errors (F12 → Console)
4. Note any differences across browsers
```

### Responsive Testing
```
1. Open https://www.saucedemo.com in Chrome
2. Press F12 → Ctrl+Shift+M to open device toolbar
3. Test at widths: 375, 414, 768, 1024, 1366, 1920
4. Check for horizontal scroll, broken layout, unreadable text
5. Test portrait and landscape using rotate icon
```

### Accessibility Testing
```
1. Lighthouse: F12 → Lighthouse tab → Accessibility → Analyze page load
2. WAVE: Go to wave.webaim.org → enter URL → check errors and alerts
3. Keyboard: Press Tab key → check all elements are reachable
```

---

## 💡 Lessons Learned

1. Usability testing reveals problems that **automated testing completely misses**
2. Error messages are one of the **most overlooked** usability issues
3. Chrome DevTools device toolbar simulates **all screen sizes for free** — no real device needed
4. A Lighthouse score of **90+ means good accessibility** — aim for this on every project
5. WAVE and Lighthouse **complement each other** — use both for complete coverage
6. **Firefox proxy issues** are a real-world environment problem — always document them
7. Cross-browser issues are **less common today** — Chrome and Edge both use Blink engine

---

## 📁 Project Structure

```
Day17-Usability-Compatibility-Testing/
│
├── 📄 README.md                        ← You are here
│
├── 📋 Reports/
│   ├── Report1_Usability_Testing.docx
│   ├── Report2_CrossBrowser_Results.docx
│   ├── Report3_Responsive_Matrix.docx
│   ├── Report4_Accessibility_Audit.docx
│   └── Report5_README_Checklist.docx
│
└── 📊 Screenshots/
    ├── Lighthouse_Score_96.png
    ├── WAVE_Results.png
    ├── Responsive_375px.png
    └── Responsive_768px.png
```

---

## 🗓️ Challenge Progress

| Day | Topic | Status |
|-----|-------|--------|
| Day 15 | Performance Testing | ✅ Done |
| Day 16 | Advanced JMeter | ✅ Done |
| **Day 17** | **Usability & Compatibility Testing** | ✅ Done |
| Day 18 | Security Testing | 🔜 Next |
| Day 19 | Test Automation Framework | 🔜 Upcoming |

---

## 🔗 Resources

- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [WAVE Accessibility Tool](https://wave.webaim.org)
- [Chrome Lighthouse Docs](https://developer.chrome.com/docs/lighthouse/)
- [Sauce Demo Practice Site](https://www.saucedemo.com)
- [Nielsen Norman Group — Usability](https://www.nngroup.com/articles/usability-101-introduction-to-usability/)

---
