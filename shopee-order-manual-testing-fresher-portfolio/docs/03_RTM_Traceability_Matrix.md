# REQUIREMENTS TRACEABILITY MATRIX (RTM)

The Requirements Traceability Matrix (RTM) establishes forward and backward traceability between business requirements, test design artifacts, and test execution outcomes. It ensures that 100% of functional requirements have corresponding test cases and monitors quality status across modules.

---

## 1. Traceability Overview

| Total Functional Requirements | Total Test Cases Designed | Execution Coverage | Pass Rate | Open Defects |
|:---:|:---:|:---:|:---:|:---:|
| **10 Key Modules** | **79 Test Cases** | **100%** | **94.9% (75/79)** | **3 Defects** |

---

## 2. Requirements to Test Cases Mapping

| Req ID | Requirement / Feature Description | Test Scenario | Associated Test Cases | Priority | Status | Defect ID |
|:---:|---|---|---|:---:|:---:|:---:|
| **REQ-01** | **Cart Management & Direct Checkout**<br>Support adding items to cart and direct "Buy Now" flow. | TS-01: Cart Flow | `TC_01`, `TC_02` | High | ✅ Passed | - |
| **REQ-02** | **Checkout UI & Element Responsiveness**<br>Ensure consistent layout, clear typography, and responsive toggles. | TS-02: UI Overview | `TC_03`, `TC_04` | Low | ✅ Passed | - |
| **REQ-03** | **Shipping Address & Identity Verification**<br>Default address rendering, edit/add address, Citizen ID validation. | TS-03: Address & ID | `TC_05`, `TC_06`, `TC_07`, `TC_08`, `TC_09`, `TC_10` | High / Med | ❌ Failed (`TC_10`) | `BUG_001` |
| **REQ-04** | **Shop & Product Details Breakdown**<br>Display shop badge, product variation, price, item quantity adjustments. | TS-04: Products | `TC_11`, `TC_12`, `TC_13`, `TC_14`, `TC_15`, `TC_16`, `TC_17`, `TC_18`, `TC_19`, `TC_20`, `TC_21`, `TC_22`, `TC_23` | High / Med | ✅ Passed | - |
| **REQ-05** | **Logistics & Shipping Channels**<br>Express, Standard, and Economy selection with dynamic fee calculation. | TS-05: Shipping | `TC_24`, `TC_25`, `TC_26`, `TC_27`, `TC_28`, `TC_29`, `TC_30` | High / Med | ✅ Passed | - |
| **REQ-06** | **Promotions, Vouchers & Discounts**<br>Platform vouchers, shop vouchers, free shipping, stacking rules, spend limits. | TS-06: Vouchers | `TC_31`, `TC_32`, `TC_33`, `TC_34`, `TC_35`, `TC_36`, `TC_37`, `TC_38`, `TC_39`, `TC_40`, `TC_41`, `TC_42`, `TC_43` | High / Med | ❌ Failed (`TC_34`) | `BUG_002` |
| **REQ-07** | **Payment Methods & Financial Channels**<br>COD, ShopeePay, SPayLater installments, Credit/Debit cards, bank transfer. | TS-07: Payment | `TC_44`, `TC_45`, `TC_46`, `TC_47`, `TC_48`, `TC_49`, `TC_50`, `TC_51`, `TC_52` | High / Med | ❌ Failed (`TC_49`) | `BUG_003` |
| **REQ-08** | **Order Financial Summary & Coin Redemption**<br>Price calculation: subtotal + shipping - vouchers - coins + insurance. | TS-08: Order Details | `TC_53`, `TC_54`, `TC_55`, `TC_56`, `TC_57`, `TC_58`, `TC_59`, `TC_60`, `TC_61` | High / Med | ✅ Passed | - |
| **REQ-09** | **Order Placement & Gateway Confirmation**<br>Processing "Place Order", handling payment responses and confirmation. | TS-09: Order Placement | `TC_62`, `TC_63` | High | ⚠️ Blocked (`TC_62`) | - |
| **REQ-10** | **Multi-Shop Splitting & E-Invoicing (VAT)**<br>Splitting orders across sellers, separate vouchers, e-invoicing form submission. | TS-10: Multi-Shop & VAT | `TC_64`, `TC_65`, `TC_66`, `TC_67`, `TC_68`, `TC_69`, `TC_70`, `TC_71`, `TC_72`, `TC_73`, `TC_74`, `TC_75`, `TC_76`, `TC_77`, `TC_78`, `TC_79` | High / Med | ✅ Passed | - |

---

## 3. Coverage Analysis

$$\text{Test Coverage} = \frac{\text{Number of Tested Requirements}}{\text{Total Requirements}} = \frac{10}{10} = 100\%$$

$$\text{Execution Rate} = \frac{\text{Executed Test Cases}}{\text{Total Test Cases}} = \frac{79}{79} = 100\%$$

$$\text{Pass Rate} = \frac{\text{Passed Test Cases}}{\text{Total Test Cases}} = \frac{75}{79} = 94.94\%$$
