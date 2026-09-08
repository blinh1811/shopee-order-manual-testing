# TEST SCENARIOS SPECIFICATION

This document outlines high-level test scenarios covering the Shopee Order & Checkout journey, mapped directly to the individual test case specifications in [`Test_Cases_Specification.md`](../test-cases/Test_Cases_Specification.md).

---

## Scenario Summary Table

| Scenario ID | Module | Scenario Description | Test Objective | Covered Test Cases |
|:---:|---|---|---|:---:|
| **TS_01** | Cart & Buy Now | Validate adding products to cart and direct checkout execution | Ensure items seamlessly transition from catalog to order funnel | `TC_01` - `TC_02` |
| **TS_02** | Checkout UI | Verify layout integrity, typography, and interactive controls | Ensure visual hierarchy and responsive interactive states | `TC_03` - `TC_04` |
| **TS_03** | Shipping Address & ID | Validate address display, editing, and mandatory Citizen ID rules | Verify delivery routing accuracy and customs compliance | `TC_05` - `TC_10` |
| **TS_04** | Product & Shop Details | Validate shop separation, variation labels, and pricing | Ensure item variations, stock status, and subtotals are accurate | `TC_11` - `TC_23` |
| **TS_05** | Shipping Methods | Validate shipping channel options, delivery estimates, and fees | Ensure logistics rates and delivery times calculate correctly | `TC_24` - `TC_30` |
| **TS_06** | Promotions & Vouchers | Validate voucher eligibility, stacking rules, and spend limits | Ensure multi-tier promotional discounts compute accurately | `TC_31` - `TC_43` |
| **TS_07** | Payment Methods | Validate payment selection (COD, ShopeePay, SPayLater, Cards) | Ensure payment channel rules and installment options function | `TC_44` - `TC_52` |
| **TS_08** | Order Financial Calculation | Validate full order subtotal, discount, fee, and coin equations | Guarantee 100% mathematical precision in grand total | `TC_53` - `TC_61` |
| **TS_09** | Order Confirmation | Validate "Place Order" execution, duplicate submission guard, and confirmation | Ensure transaction integrity and order dispatch notification | `TC_62` - `TC_63` |
| **TS_10** | Multi-Shop & E-Invoicing | Validate multi-merchant split orders and company tax receipt requests | Verify B2B/B2C invoice form submission and cross-shop separation | `TC_64` - `TC_79` |

---

## Detailed Scenario Breakdown

### TS_01: Cart Management & Instant Checkout
- **Scope**: Adding items to shopping bag, quantity modifiers, and the direct "Buy Now" CTA.
- **Key Scenarios**:
  - `TS_01_01`: Add product with selectable variations (Color, Size) into cart (`TC_01`).
  - `TS_01_02`: Click "Buy Now" on product detail page; verify instantaneous redirection to Checkout page bypassing the Cart (`TC_02`).

### TS_02: Checkout Page UI & Element Responsiveness
- **Scope**: Visual consistency, section division, element responsiveness across mobile & web viewports.
- **Key Scenarios**:
  - `TS_02_01`: Verify typography, contrast ratios, and alignment across all order sections (`TC_03`).
  - `TS_02_02`: Verify responsiveness and touch targets of toggles, checkboxes, and modal triggers (`TC_04`).

### TS_03: Shipping Address & Identity Verification
- **Scope**: Address display, modification modal, and regulatory identity verification.
- **Key Scenarios**:
  - `TS_03_01`: Verify pre-population of user's default shipping address (`TC_05`).
  - `TS_03_02`: Select alternate saved address or input a newly created address (`TC_06`, `TC_07`).
  - `TS_03_03`: Trigger mandatory Citizen ID verification for imported/cross-border items (`TC_08`, `TC_09`, `TC_10`).

### TS_04: Shop & Product Details Verification
- **Scope**: Shop-level grouping, item details, variations, and message to seller.
- **Key Scenarios**:
  - `TS_04_01`: Verify seller verification badges (Shopee Mall, Preferred Seller) (`TC_11`, `TC_12`).
  - `TS_04_02`: Verify SKU thumbnail, title, chosen variation text, and unit pricing (`TC_13` - `TC_17`).
  - `TS_04_03`: Verify optional "Message for Seller" text input and character limit (`TC_18` - `TC_23`).

### TS_05: Shipping Options & Logistics Channels
- **Scope**: Logistics providers, channel tiers (Standard, Express, Economy), and delivery insurance.
- **Key Scenarios**:
  - `TS_05_01`: Switch between available logistics tiers and observe instantaneous fee adjustments (`TC_24` - `TC_27`).
  - `TS_05_02`: Verify estimated delivery date range display (`TC_28`, `TC_29`).
  - `TS_05_03`: Verify free shipping threshold logic and shipping voucher application (`TC_30`).

### TS_06: Promotions, Discounts & Vouchers
- **Scope**: Platform vouchers, shop-exclusive vouchers, free shipping coupons, coin redemption.
- **Key Scenarios**:
  - `TS_06_01`: Apply valid promotional voucher code manually and via list selection (`TC_31`, `TC_32`).
  - `TS_06_02`: Validate error handling for expired codes, fully redeemed codes, and minimum spend boundaries (`TC_33` - `TC_36`).
  - `TS_06_03`: Verify stacking behavior when combining Platform + Shop + Shipping vouchers (`TC_37` - `TC_43`).

### TS_07: Payment Methods & Gateway Options
- **Scope**: Cash on Delivery (COD), ShopeePay wallet, SPayLater, Credit/Debit card, Linked Bank.
- **Key Scenarios**:
  - `TS_07_01`: Select COD and verify eligibility criteria (order amount $\le 5,000,000$ VND) (`TC_44`, `TC_45`).
  - `TS_07_02`: Select ShopeePay and verify real-time wallet balance display and top-up prompt (`TC_46` - `TC_48`).
  - `TS_07_03`: Select SPayLater and verify installment tenure choices (1, 3, 6, 12 months) (`TC_49`, `TC_50`).
  - `TS_07_04`: Verify billing address synchronization with shipping address (`TC_51`, `TC_52`).

### TS_08: Financial Summary & Total Recalculation
- **Scope**: Total formula precision: $\text{Subtotal} + \text{Shipping} - \text{Discounts} - \text{Coins} + \text{Insurance}$.
- **Key Scenarios**:
  - `TS_08_01`: Verify mathematical accuracy across all line items (`TC_53` - `TC_56`).
  - `TS_08_02`: Apply Shopee Coins and verify 50% max order cap rule (`TC_57` - `TC_59`).
  - `TS_08_03`: Verify debounce and double-click prevention on order submission button (`TC_60`, `TC_61`).

### TS_09: Order Placement & Processing Results
- **Scope**: Gateway redirect, order ID generation, confirmation push notification.
- **Key Scenarios**:
  - `TS_09_01`: Order success: verify unique Order ID creation and inventory stock deduction (`TC_62`).
  - `TS_09_02`: Order failure: verify clear error messaging when card is declined or wallet balance is insufficient (`TC_63`).

### TS_10: Multi-Shop Splitting & Corporate Invoicing
- **Scope**: Orders containing products from $\ge 2$ independent sellers, VAT tax invoice requests.
- **Key Scenarios**:
  - `TS_10_01`: Verify distinct shop order blocks with independent shipping channel selection (`TC_64` - `TC_68`, `TC_76` - `TC_79`).
  - `TS_10_02`: Complete VAT e-invoicing form for Personal vs Company billing (`TC_69` - `TC_74`).
  - `TS_10_03`: Verify external legal terms hyperlink navigation (`TC_75`).
