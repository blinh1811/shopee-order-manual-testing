# TEST PLAN – SHOPEE ORDER & CHECKOUT FLOW

| Attribute | Details |
|---|---|
| **Document ID** | TP-SHOPEE-ORD-001 |
| **Standard** | IEEE 829-2008 Standard for Software Test Documentation |
| **Project** | Shopee E-Commerce Mobile/Web Checkout System |
| **Target Release** | Version 3.14.0 (Candidate Release) |
| **Author** | QA / Fresher Tester |
| **Date** | September 2026 |
| **Status** | Approved / Baseline |

---

## 1. Introduction & Objectives

### 1.1 Purpose
This Test Plan defines the scope, strategy, objectives, resources, schedule, and deliverables for verifying the **Order and Checkout Workflow** of the Shopee e-commerce platform.

### 1.2 Testing Objectives
- Ensure high reliability and accuracy in the order lifecycle: Cart item selection $\rightarrow$ Checkout summary $\rightarrow$ Address resolution $\rightarrow$ Logistics selection $\rightarrow$ Voucher & Coin discounts $\rightarrow$ Payment processing $\rightarrow$ Order confirmation.
- Validate that all financial calculations (subtotals, multi-tier voucher discounts, coins deduction, shipping fees, insurance fees, and grand total) are 100% mathematically correct without rounding anomalies.
- Guarantee that negative conditions, input edge cases, expired vouchers, and invalid data inputs are gracefully intercepted with user-friendly validation messages.
- Verify seamless multi-seller / multi-shop order splitting and separate logistics options.

---

## 2. Test Scope

### 2.1 In-Scope (Features to be Tested)
1. **Cart Interaction**:
   - Single & bulk item selection, "Buy Now" direct checkout redirection.
2. **Checkout Overview & UI Responsiveness**:
   - Element alignment, responsiveness across viewports, dynamic toggles, section expansion.
3. **Shipping Address & Identity Verification**:
   - Default address rendering, inline address editing, new address entry, Citizen ID / Passport validation for regulated products.
4. **Shop & Product Details Breakdown**:
   - Product variation tags, price changes, out-of-stock warning, shop-level subtotal calculations.
5. **Logistics & Shipping Options**:
   - Express, Standard, Economy channel selection, delivery time estimates, shipping fee updates.
6. **Promotions, Vouchers & Shopee Coins**:
   - Free shipping vouchers, percentage and flat-rate shop vouchers, minimum spend criteria, voucher stackability rules, Shopee Coin balance deduction.
7. **Payment Channels & Details**:
   - Cash on Delivery (COD), ShopeePay wallet, SPayLater installment options, Linked Bank / Credit Card options, billing address selector.
8. **Invoicing & E-Receipts**:
   - Personal vs. Company VAT invoice request forms, Tax ID validation, default billing persistence.
9. **Multi-Shop Checkout**:
   - Multi-merchant split orders, independent voucher application per shop, multi-channel shipping fee aggregation.

### 2.2 Out-of-Scope (Features Not Tested)
- Core banking mainframe authorization & settlement networks (mocked in test environment).
- Physical warehouse packaging, picking, and fleet dispatch logistics tracking.
- Stress testing under extreme flash-sale peak load (> 100,000 requests/sec - handled by dedicated Performance QA team).
- Hardware security module (HSM) penetration testing.

---

## 3. Test Strategy & Methodology

### 3.1 Test Levels
- **Functional Testing**: Validating business requirements against expected user journeys.
- **Integration Testing**: Verifying cross-module data flow (Voucher Engine $\leftrightarrow$ Cart $\leftrightarrow$ Payment Service).
- **Regression Testing**: Ensuring bug fixes do not introduce side effects into core ordering calculations.
- **Exploratory Testing**: Unscripted testing targeting edge conditions and unusual user interaction sequences.

### 3.2 Test Design Techniques Applied
- **Equivalence Partitioning (EP)**: Segmenting input data (valid vs. invalid postal codes, phone numbers, Tax IDs).
- **Boundary Value Analysis (BVA)**: Minimum order spend thresholds, voucher discount caps, maximum coin redemption limits.
- **Decision Table Testing**: Voucher stacking matrix (Platform Voucher + Shop Voucher + Free Shipping).
- **State Transition Testing**: Order status transitions (Draft $\rightarrow$ Pending Payment $\rightarrow$ Placed $\rightarrow$ Paid).
- **Error Guessing**: Double-clicking "Place Order", network disconnection mid-transaction, expired session token during checkout.

---

## 4. Test Environment & Test Data

### 4.1 Test Environment Specifications
- **Staging / QA Sandbox**: `https://staging-checkout.shopee.local`
- **Client Platforms**:
  - Web: Google Chrome (Latest), Mozilla Firefox (Latest), Apple Safari (iOS).
  - Mobile Devices: Android 14 (Samsung Galaxy S23, Xiaomi 13), iOS 17 (iPhone 14 Pro, iPhone 13).
- **Test Management Tools**: Jira, Confluence, Microsoft Excel, GitHub.

### 4.2 Test Data Requirements
- Pre-configured buyer accounts: New user (0 coins), Regular buyer (10,000 coins), VIP buyer (with SPayLater approved credit limit).
- Multiple test merchants: Domestic shop, Official Mall shop, Cross-border shop requiring Citizen ID verification.
- Promotional vouchers: Active vouchers, expired vouchers, exhausted usage limit vouchers, conditional minimum-spend vouchers (e.g. Min spend 250,000 VND).

---

## 5. Entry & Exit Criteria

### 5.1 Entry Criteria
- Build version deployed successfully to the QA environment with zero blocker compilation errors.
- Requirements and business rules documentation approved and baselined.
- Test accounts, merchant inventories, and promotion test data seeded in database.
- Test plan and test scenarios signed off.

### 5.2 Exit Criteria
- 100% of planned test cases executed (79/79 TCs).
- Minimum Test Pass Rate $\ge 90\%$ (Current actual: **94.9%**).
- 0 Blocker (P1) or Critical (P2) bugs remaining unaddressed or unmitigated.
- All identified defects documented with complete reproduction steps, severity, priority, and screenshots in the Defect Log.
- Test Execution Summary Report compiled and reviewed.

---

## 6. Suspension & Resumption Criteria

- **Suspension Criteria**: If any Blocker defect prevents access to the Checkout page or crashes the checkout flow across all test devices, testing will be suspended.
- **Resumption Criteria**: Testing will resume once development releases a verified hotfix build addressing the blocking issue.

---

## 7. Deliverables

| Phase | Deliverable |
|---|---|
| **Planning** | Test Plan Document (`01_Test_Plan.md`) |
| **Design** | Test Scenarios (`Test_Scenarios.md`), Test Case Repository (`Shopee_Order_Testcase.xlsx`, `Test_Cases_Specification.md`), RTM (`03_RTM_Traceability_Matrix.md`) |
| **Execution** | Defect Log (`Defect_Log.md`), Individual Bug Reports (`BUG_001.md`, `BUG_002.md`, `BUG_003.md`) |
| **Closure** | Test Execution Summary Report (`Test_Execution_Summary_Report.md`) |

---

## 8. Risk Management

| Risk ID | Risk Description | Likelihood | Impact | Mitigation Strategy |
|:---:|---|:---:|:---:|---|
| **R-01** | Third-party payment gateway sandbox latency or downtime | Medium | High | Use mock payment gateway simulator for primary checkout functional validation. |
| **R-02** | Promotion engine timing drift during voucher expiration tests | Low | Medium | Mock server system clock via test configuration parameters. |
| **R-03** | Missing ID documentation for cross-border items | Medium | Low | Maintain synthesized dummy Citizen ID dataset compliant with checksum validation rules. |
