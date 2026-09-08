# BUG REPORT TEMPLATE (JIRA / AZURE DEVOPS STYLE)

Use this template to record defects discovered during test execution.

---

```markdown
## [BUG-ID] Brief, concise, and descriptive bug summary

- **Project**: Shopee Order & Checkout Flow
- **Reported By**: QA / Fresher Tester
- **Date Reported**: YYYY-MM-DD
- **Environment**: 
  - Platform: [Web Chrome / Android App / iOS App]
  - OS Version: [e.g., Android 14 / Windows 11]
  - App Version / Build: [e.g., v3.14.0-build-821]
- **Severity**: [Blocker / Critical / Major / Minor / Trivial]
- **Priority**: [High (P1) / Medium (P2) / Low (P3)]
- **Status**: [New / Open / In Progress / Fixed / Retest / Closed]
- **Associated Test Case ID**: [e.g., TC_10]
- **Component / Module**: [e.g., Checkout > Shipping Address]

---

### Description
A clear explanation of what went wrong and under what circumstances.

### Preconditions
- Prerequisites needed before executing the steps (e.g., user logged in, specific cart state).

### Steps to Reproduce
1. Navigate to ...
2. Click on ...
3. Enter invalid value ...
4. Submit the form ...

### Expected Result
What the application should have done according to the business requirement / functional specification.

### Actual Result
What the application actually did (error behavior, crash, incorrect calculation, missing validation).

### Evidence / Attachments
- Screenshots with red highlight boxes
- Screen recordings (.mp4 / .webm)
- Network console logs / HTTP response payloads

### Impact & Workaround
- **User Impact**: How this bug affects the customer or revenue.
- **Workaround**: Is there any temporary way for the user to bypass this issue?
```
