# TEST EXECUTION SUMMARY REPORT

| Attribute | Details |
|---|---|
| **Document ID** | TSR-SHOPEE-ORD-001 |
| **Standard** | IEEE 829-2008 Standard for Test Summary Reporting |
| **Project** | Shopee E-Commerce – Order & Checkout Manual Testing |
| **Test Cycle** | Cycle 1 – Functional, UI & Integration Test Run |
| **App Version** | v3.14.0-rc3 |
| **Execution Date** | September 2026 |
| **Lead Tester / Author** | QA / Fresher Tester |
| **Overall QA Verdict** | **CONDITIONAL PASS (Ready for Release pending P1 Fix)** |

---

## 1. Executive Summary

This report documents the execution results and defect findings from testing the **Shopee Order & Checkout Flow**. The primary goal was to ensure the functional correctness of cart-to-order transitions, multi-tier voucher stacking, shipping fee dynamic calculations, multiple payment channels, and multi-merchant split orders.

- **Planned Test Cases**: 79
- **Executed Test Cases**: 79 (100% Execution Rate)
- **Passed**: 75 (**94.94%**)
- **Failed**: 3 (**3.80%**)
- **Blocked**: 1 (**1.26%**)
- **Total Defects Logged**: 3 (0 Blocker, 2 Major, 1 Minor)

---

## 2. Test Execution Metrics Dashboard

### 2.1 Overall Execution Status

```text
[███████████████████████████████████████████████▒▒] 94.9% Passed
```

| Metric Category | Count | Percentage |
|---|:---:|:---:|
| **Total Test Cases** | 79 | 100.0% |
| **Executed Cases** | 79 | 100.0% |
| **Passed Cases** | 75 | **94.94%** |
| **Failed Cases** | 3 | **3.80%** |
| **Blocked Cases** | 1 | **1.26%** |

### 2.2 Results Breakdown by Module

| Module Name | Sub-Module | Total | Passed | Failed | Blocked | Pass Rate |
|---|---|:---:|:---:|:---:|:---:|:---:|
| **Cart** | Cart & Buy Now | 2 | 2 | 0 | 0 | **100%** |
| **Checkout** | UI Overview | 2 | 2 | 0 | 0 | **100%** |
| **Checkout** | Shipping Address & Personal Info | 6 | 5 | 1 | 0 | **83.3%** |
| **Checkout** | Shop & Product Detail | 13 | 13 | 0 | 0 | **100%** |
| **Checkout** | Shipping Methods | 7 | 7 | 0 | 0 | **100%** |
| **Checkout** | Voucher & Promotion Engine | 13 | 12 | 1 | 0 | **92.3%** |
| **Checkout** | Payment Details | 9 | 8 | 1 | 0 | **88.9%** |
| **Checkout** | Order Financial Calculation | 9 | 9 | 0 | 0 | **100%** |
| **Payment Results** | Order Confirmation | 2 | 1 | 0 | 1 | **50.0%** |
| **Others** | Multi-Shop & Invoicing | 16 | 16 | 0 | 0 | **100%** |
| **TOTAL** | | **79** | **75** | **3** | **1** | **94.94%** |

---

## 3. Defect Analysis & Density

### 3.1 Defect Severity vs. Priority Distribution

| Severity \ Priority | High (P1) | Medium (P2) | Low (P3) | Total |
|---|:---:|:---:|:---:|:---:|
| **Critical / Blocker** | 0 | 0 | 0 | **0** |
| **Major** | 1 (`BUG_001`) | 1 (`BUG_002`) | 0 | **2** |
| **Minor / Trivial** | 0 | 0 | 1 (`BUG_003`) | **1** |
| **TOTAL** | **1** | **1** | **1** | **3** |

### 3.2 Summary of Logged Defects

1. **[`BUG_001`](../bug-reports/BUG_001.md) (High / Major)**: Inline validation error missing when submitting empty or invalid Citizen ID for cross-border clearance.
2. **[`BUG_002`](../bug-reports/BUG_002.md) (Medium / Major)**: Voucher minimum spend warning displays raw localization token `Mua thêm {0} VND` instead of calculated amount.
3. **[`BUG_003`](../bug-reports/BUG_003.md) (Low / Minor)**: SPayLater 12-month installment card unclickable on landscape view due to sticky footer button overlap.

---

## 4. Exit Criteria Evaluation

| Test Plan Criterion | Target Requirement | Actual Result | Status |
|---|---|---|:---:|
| **Test Case Execution** | 100% planned cases executed | 79 / 79 executed | ✅ **Met** |
| **Test Pass Rate** | $\ge 90\%$ | 94.94% | ✅ **Met** |
| **Critical / Blocker Bugs** | 0 open Critical/Blocker defects | 0 open Critical/Blocker defects | ✅ **Met** |
| **Defect Logging & RTM** | All defects logged with evidence & RTM updated | 100% traced to TCs and Requirements | ✅ **Met** |
| **Major Defects Resolution** | All P1 Major defects resolved | 1 P1 open (`BUG_001`) awaiting patch | ⚠️ **Pending Dev Fix** |

---

## 5. Residual Risks & Recommendations

### 5.1 Residual Risks
- **Cross-Border Customs Compliance**: If `BUG_001` is not hotfixed, invalid IDs may bypass client validation and cause high rejection rates during customs processing.
- **Blocked Payment Gateway Test (`TC_62`)**: Bank 3D-Secure SMS OTP flow could only be validated via mock simulator in the staging environment. Verification against live merchant staging sandbox is required prior to production switch.

### 5.2 QA Recommendations
1. **Merge hotfix for `BUG_001`**: Backend verification must be supplemented by immediate client-side regex checking on the 12-digit Citizen ID field.
2. **Verify localized string interpolation in `BUG_002`**: Ensure all language bundles (Vietnamese, English) correctly supply the remaining spend parameter.
3. **Production Smoke Testing**: Perform a 1-VND real test purchase using live ShopeePay and credit cards immediately post-deployment.

---

## 6. QA Sign-Off Decision

- **Recommendation**: **CONDITIONAL APPROVAL**.
- The core checkout and financial calculation engine is robust and stable. Deployment to Production Staging is approved upon release of the hotfix verifying `BUG_001`.
