# DEFECT LOG (BUG TRACKING SUMMARY)

This log tracks all defects discovered during the execution of the Shopee Order & Checkout test suite.

---

## 1. Defect Metrics Summary

| Total Defects | Critical / Blocker | Major | Minor | Open / In Progress | Fixed / Verified |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **3** | **0** | **2** | **1** | **2 Open, 1 In Progress** | **0 Closed** |

---

## 2. Defect Tracking Matrix

| Defect ID | Summary | Module | Severity | Priority | Status | Linked Test Case | Reported Date |
|:---:|---|---|:---:|:---:|:---:|:---:|:---:|
| [**BUG_001**](BUG_001.md) | Inline validation error missing when submitting empty or invalid Citizen ID | Checkout > Shipping Address | **Major** | **High (P1)** | `Open` | `TC_10` | 2026-09-07 |
| [**BUG_002**](BUG_002.md) | Voucher minimum-spend error tooltip renders unformatted raw string placeholder `{0} VND` | Checkout > Voucher | **Major** | **Medium (P2)** | `In Progress` | `TC_34` | 2026-09-07 |
| [**BUG_003**](BUG_003.md) | SPayLater installment tenure dropdown becomes unclickable upon rotating mobile screen to landscape | Checkout > Payment Details | **Minor** | **Low (P3)** | `Open` | `TC_49` | 2026-09-07 |

---

## 3. Severity & Priority Definitions

- **Severity (Technical Impact)**:
  - **Blocker**: App crash, data corruption, entire checkout flow unusable.
  - **Critical**: Core function broken with no workaround (e.g. unable to pay via any method).
  - **Major**: Major business rule violation, incorrect financial calculations, or missing mandatory validation with potential compliance impact.
  - **Minor**: Non-blocking functional defect, layout distortion, or edge-case UI responsiveness issue with a workaround available.
  - **Trivial**: Typos, minor cosmetic blemishes, color mismatch.

- **Priority (Business Urgency)**:
  - **High (P1)**: Must fix before release.
  - **Medium (P2)**: Fix in current sprint / patch update.
  - **Low (P3)**: Fix when convenient or scheduled in future maintenance cycle.
