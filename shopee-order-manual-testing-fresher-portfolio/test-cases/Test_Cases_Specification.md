# Shopee Order & Checkout – Test Case Specification

> **Project**: E-Commerce Manual Testing Portfolio – Shopee Order Journey  
> **Role**: QA / Fresher Tester  
> **Total Test Cases**: 79 | **Passed**: 75 (94.9%) | **Failed**: 3 (3.8%) | **Blocked**: 1 (1.3%)  

---

## 📊 Test Execution Summary

| Module | Sub-Module | Total Cases | High | Medium | Low | Passed | Failed | Blocked |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Cart | - | 2 | 2 | 0 | 0 | 2 | 0 | 0 |
| Checkout | UI Overview | 2 | 0 | 0 | 2 | 2 | 0 | 0 |
| Checkout | Shipping address & personal information | 6 | 3 | 3 | 0 | 5 | 1 | 0 |
| Checkout | Shop & Product Detail | 13 | 2 | 10 | 1 | 13 | 0 | 0 |
| Checkout | Shipping methods | 7 | 2 | 5 | 0 | 7 | 0 | 0 |
| Checkout | Voucher | 13 | 4 | 9 | 0 | 12 | 1 | 0 |
| Checkout | Payment Details | 9 | 4 | 5 | 0 | 8 | 1 | 0 |
| Checkout | Order Details | 9 | 6 | 3 | 0 | 9 | 0 | 0 |
| Payment Results | Order Details | 2 | 2 | 0 | 0 | 1 | 0 | 1 |
| Others | Order Details | 16 | 2 | 13 | 1 | 16 | 0 | 0 |

---

## 📋 Detailed Test Case Repository

### 🔹 Cart – -

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_01** | Verify product can be added to cart successfully | - | 1. Open product page<br>2. Click "Add to cart" | Product is added to cart without error | High | ✅ **PASSED** | - |

| **TC_02** | Verify "Buy Now" redirects to checkout page directly | - | 1. Open product page<br>2. Click "Buy Now" | Redirects immediately to checkout with correct product data | High | ✅ **PASSED** | - |

### 🔹 Checkout – UI Overview

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_03** | Verify overall layout, font consistency, element alignment, and full content display on page | - | 1. Proceed to payment page<br>2. Observe font size, style<br>3. Verify layout structure and alignment<br>4. Confirm all sections are displayed | 1. Layout is clean and aligned<br>2. Font is consistent<br>3. All content like order summary, voucher, payment method, and shipping info are displayed clearly | Low | ✅ **PASSED** | - |

| **TC_04** | Verify all interactive elements (checkboxes, toggles, dropdowns) are clickable and responsive | - | 1. Proceed to payment page<br>2. Try clicking all toggles (Shopee Coin, Voucher, etc.) | All interactive UI elements respond correctly on click/toggle and update the state accordingly | Low | ✅ **PASSED** | - |

### 🔹 Checkout – Shipping address & personal information

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_05** | Check if user sees the correct default shipping address | - | 1. Go to Checkout page | The default shipping address (name, phone, full address) is displayed correctly | High | ✅ **PASSED** | - |

| **TC_06** | Check if user can tap the adress section to update or change it | - | 1. Tap on the address section <br>2. Choose or edit an address | The app navigates to the edit screen and allows address update or selection | High | ✅ **PASSED** | - |

| **TC_07** | Verify that user can add a new address from the address selection screen | - | 1. Tap "+ Add new address" <br>2. Fill in the form <br>3. Save | New address is added and can be set as default | High | ✅ **PASSED** | - |

| **TC_08** | Verify that ID verification field appears for items that require ID | - | 1. Go to Checkout page | "ID Card Information" section is displayed beside address | Medium | ✅ **PASSED** | - |

| **TC_09** | Verify that user can tap and input ID number for required items | ID not yet provided | 1. Tap "ID Card Information" <br>2. Enter valid ID info <br>3. Save | All entered personal information (Full name, ID card number, Address) are saved and displayed as masked (e.g., ********2891) | Medium | ✅ **PASSED** | - |

| **TC_10** | Verify error is shown if ID info is incomplete or invalid | - | 1. Tap "ID Card Information" <br>2. Enter invalid data <br>3. Save | Error message appears, preventing user from continuing | Medium | ❌ **FAILED** | [BUG_001](../bug-reports/BUG_001.md) |

### 🔹 Checkout – Shop & Product Detail

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_11** | Verify shop name is displayed | - | 1. Go to Checkout<br>2. Observe shop name display | Shop name is visible and styled properly | Low | ✅ **PASSED** | - |

| **TC_12** | Verify shop mall badge appears for Shopee Mall shop | - | 1. Go to Checkout<br>2. Observe shop badge | "Mall" badge displayed next to shop name | High | ✅ **PASSED** | - |

| **TC_13** | Verify tapping arrow icon beside shop name navigates to shop's homepage | - | 1. Tap arrow icon beside shop name | Redirects to shop page | High | ✅ **PASSED** | - |

| **TC_14** | Verify listing data on product view | - | 1. Go to Checkout<br>2. Observe product summary block | Image, name, price, and quantity all shown clearly | Medium | ✅ **PASSED** | - |

| **TC_15** | Verify correct calculation of subtotal per product | - | 1. Go to Checkout<br>2. Observe product subtotal | Subtotal displayed properly | Medium | ✅ **PASSED** | - |

| **TC_16** | Verify presence and toggle of "Fashion insurance" checkbox | - | 1. Observe checkbox<br>2. Tap to select | Checkbox toggles correctly, displays additional fee if selected | Medium | ✅ **PASSED** | - |

| **TC_17** | Verify insurance fee is added to total when checkbox is selected | - | 1. Tap checkbox<br>2. Observe total cost update | Total cost increases by insurance fee (if applicable) | Medium | ✅ **PASSED** | - |

| **TC_18** | Verify available shop voucher is displayed and selectable | - | 1. Tap "Shop voucher"<br>2. Select voucher<br>3. Observe discount | Voucher is applied, discount reflected in total | Medium | ✅ **PASSED** | - |

| **TC_19** | Verify user cannot select shop voucher if cart does not meet conditions | Cart total: 200.000đ<br>Voucher: -50k for orders ≥ 300.000đ | 1. Add products not meeting condition<br>2. Tap "Shop voucher" | Voucher is shown as disabled/grayed out, and cannot be selected | Medium | ✅ **PASSED** | - |

| **TC_20** | Verify shop voucher auto-applied when all conditions are met | Cart total: 500.000đ<br>Voucher: -50k for orders ≥ 300.000đ | 1. Add multiple eligible products to cart<br>2. Go to Checkout | Voucher is automatically selected and discount shown in total | Medium | ✅ **PASSED** | - |

| **TC_21** | Verify user can enter message to shop | - | 1. Tap "Message to shop"<br>2. Type message | Message input is accepted and saved with order | Medium | ✅ **PASSED** | - |

| **TC_22** | Verify message input has reasonable character limit | Long message (300+ chars) | 1. Input long message | System truncates or prevents message over allowed limit | Medium | ✅ **PASSED** | - |

| **TC_23** | Verify user can access E-receipt request form for international order | - | 1. Add international item to cart<br>2. Proceed to checkout<br>3. Tap "Request E-Receipt" | E-Receipt form appears with all necessary input fields | Medium | ✅ **PASSED** | - |

### 🔹 Checkout – Shipping methods

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_24** | Verify user can select only one shipping method | - | 1. View shipping methods<br>2. Select one option<br>3. Try selecting another | Only one option can be selected at a time; previous selection is replaced | High | ✅ **PASSED** | - |

| **TC_25** | Check if user cannot select a shipping method | - | 1. Proceed to checkout with a cart that has no valid shipping method (e.g., remote location or restricted item)<br>2. Observe shipping section | System displays appropriate message and disables "Place Order" button | High | ✅ **PASSED** | - |

| **TC_26** | Verify that available shipping methods are displayed after entering valid shipping address | - | 1. Go to checkout<br>2. Enter valid shipping address<br>3. Scroll to Shipping Method section | A list of available shipping methods is displayed based on location | Medium | ✅ **PASSED** | - |

| **TC_27** | Verify correct shipping fee is displayed based on the selected shipping method | - | 1. Select each shipping method<br>2. Observe the fee displayed | Shipping fee updates correctly based on selected method | Medium | ✅ **PASSED** | - |

| **TC_28** | Verify default shipping method is selected if user does not choose | - | 1. Go to checkout<br>2. Skip shipping method step<br>3. Continue to payment | A default shipping method is pre-selected (e.g., cheapest or standard shipping) | Medium | ✅ **PASSED** | - |

| **TC_29** | Verify certain shipping methods are disabled for unsupported locations | - | 1. Enter restricted shipping address<br>2. Observe available shipping methods | Only applicable shipping methods are displayed; restricted methods are hidden or disabled | Medium | ✅ **PASSED** | - |

| **TC_30** | Verify shipping methods are reloaded when user changes the shipping address | - | 1. Enter address in Vietnam → observe shipping options<br>2. Change address to US → observe update | Shipping methods update automatically according to new location | Medium | ✅ **PASSED** | - |

### 🔹 Checkout – Voucher

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_31** | Verify that user can apply both Shopee voucher and Free shipping voucher simultaneously | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Select valid voucher<br>4. Select valid free shipping voucher<br>5. Confirm | Voucher is applied; discount is reflected in total price | High | ✅ **PASSED** | - |

| **TC_32** | Check if user cannot apply a voucher | - | 1. Go to the Payment page<br>2. Enter an invalid or expired voucher code<br>3. Click "Apply" or equivalent button | System displays error message and does not apply any discount | High | ✅ **PASSED** | - |

| **TC_33** | Verify user can remove an applied voucher | - | 1. Go to the Payment page<br>2. Apply a valid voucher<br>3. Deselect applied voucher | 1. Voucher is removed successfully<br>2. Discount is revoked<br>3. Total price updates accordingly | Medium | ✅ **PASSED** | - |

| **TC_34** | Verify user sees recommended voucher on top of the list | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Observe | Voucher with "Recommended" tag is prioritized in the list | Medium | ❌ **FAILED** | [BUG_002](../bug-reports/BUG_002.md) |

| **TC_35** | Verify user can't select voucher when usage limit is reached | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Observe | Voucher shows progress bar full and can't be selected | High | ✅ **PASSED** | - |

| **TC_36** | Verify expired voucher is no longer available after expiration date | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Observe the "Unavailable vouchers" section | Expired voucher is removed or moved to "Unavailable vouchers" | High | ✅ **PASSED** | - |

| **TC_37** | Verify user sees correct discount details on each voucher | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Observe | Voucher displays accurate text | Medium | ✅ **PASSED** | - |

| **TC_38** | Verify user can select only one voucher per type (Discount or shipping) | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Select one free shipping voucher<br>4. Try to select another free shipping voucher | Selecting a new voucher replaces the previous one of the same type | Medium | ✅ **PASSED** | - |

| **TC_39** | Verify user can select voucher based on payment methods | - | 1. Go to checkout<br>2. Tap "Shopee Voucher" section<br>3. Read the voucher conditions | Only vouchers matching the selected payment method are selectable | Medium | ✅ **PASSED** | - |

| **TC_40** | Verify user always has one default voucher | - | 1. Go to checkout<br>2. Observe "Shopee Voucher" section | One voucher is pre-selected | Medium | ✅ **PASSED** | - |

| **TC_41** | Verify user can apply Shopee Coin to reduce order total | - | 1. Go to checkout<br>2. Toggle "Use Shopee Coin" | Coin amount is deducted; new total displayed | Medium | ✅ **PASSED** | - |

| **TC_42** | Verify max usable Coin is capped according to policy | - | 1. Have 10,000 Xu<br>2. Try to use all on a small order | Only max allowed (e.g. 5% or 20K Xu) is used | Medium | ✅ **PASSED** | - |

| **TC_43** | Verify user can't use Shopee coin if account has 0 coin | - | 1. Go to checkout<br>2. Try enabling Coin toggle | Toggle is disabled or shows tooltip | Medium | ✅ **PASSED** | - |

### 🔹 Checkout – Payment Details

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_44** | Verify user can view available payment methods | - | 1. Go to Checkout screen<br>2. Tap "Payment Method" section | Payment methods are displayed | High | ✅ **PASSED** | - |

| **TC_45** | Verify tapping "View All" shows full list of payment methods | - | 1. On Checkout screen, tap "View All" next to Payment Method<br>2. Observe the screen | All available payment methods (ShopeePay, Linked Bank, SPayLater, Credit/Debit Card, NAPAS, COD, etc.) are displayed | High | ✅ **PASSED** | - |

| **TC_46** | Verify user can switch between payment methods | - | 1. Tap "Payment Method"<br>2. Select different method (e.g., switch from VCB to ShopeePay wallet)<br>3. Tap Confirm | Selected method is updated correctly on checkout screen | Medium | ✅ **PASSED** | - |

| **TC_47** | Verify user can't use unactivated payment methods | - | 1. Go to Checkout page with an order ready to be paid<br>2. Tap on "Payment Method" section<br>3. Observe the list of available payment methods<br>4. Attempt to select an unactivated payment method | 1, Unactivated payment methods are disabled, greyed out, or hidden<br>2. If selectable, user is redirected to activation page or shown a prompt to activate first<br>3. Payment cannot proceed using unactivated methods | Medium | ✅ **PASSED** | - |

| **TC_48** | Verify ShopeePay and Linked Bank info display correctly | - | 1. Tap ShopeePay section -> Check balance and "Top Up"<br>2. Tap Linked Bank Account -> Expand to view linked cards | 1. ShopeePay shows balance + "Top Up"<br>2. Linked bank section expands to show linked cards and "Link Bank" option | Medium | ✅ **PASSED** | - |

| **TC_49** | Verify SPayLater behavior for active/inactive state | - | 1. If inactive, check SPayLater -> See "Activate Now"<br>2. If active, tap -> View installment options | 1. Inactive: "Activate Now" button is visible<br>2. Active: Installment options (e.g., 2X, 3X, 6X) are displayed | Medium | ❌ **FAILED** | [BUG_003](../bug-reports/BUG_003.md) |

| **TC_50** | Verify card-based payment methods and promo display | - | 1. Tap Credit/Debit Card or NAPAS section<br>2. View listed cards and promotions | Promotions (e.g., 30,000đ Off - VPBank) are shown on eligible cards NAPAS cards starting with 9704 can be selected | Medium | ✅ **PASSED** | - |

| **TC_51** | Verify fallback/other payment options (COD, Apple Pay) | - | 1. Scroll to bottom of "Payment Method" screen | 1. "Cash on Delivery" is available for selection<br>2. Apple Pay is shown but disabled if not supported | High | ✅ **PASSED** | - |

| **TC_52** | Verify selected payment method is remembered across orders | - | 1. Go to Checkout screen of Order A<br>2. Select a payment method (e.g., ShopeePay → VCB card)<br>3. Exit checkout (do not place the order)<br>4. Add another item (Order B) to cart<br>5. Go to Checkout screen of Order B | The payment method previously selected is automatically shown as the default option | High | ✅ **PASSED** | - |

### 🔹 Checkout – Order Details

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_53** | Verify system calculates total item cost correctly | - | 1. Add multiple items to cart<br>2. Proceed to checkout | "Merchandise Subtotal" reflects the correct sum of item prices | High | ✅ **PASSED** | - |

| **TC_54** | Verify shipping fee is calculated based on items & address | - | 1. Add item to cart<br>2. Change delivery address<br>3. Proceed to checkout | "Shipping Subtotal" updates according to shipping policy per address | High | ✅ **PASSED** | - |

| **TC_55** | Verify shipping voucher applies discount to shipping fee | - | 1. Add item to cart<br>2. Apply free shipping voucher | "Shipping Discount Subtotal" shows correct deduction based on voucher | High | ✅ **PASSED** | - |

| **TC_56** | Verify product/shipping voucher applies correctly to total | - | 1. Add items to cart<br>2. Apply both Shopee voucher and shipping voucher | 1. Both Shopee discount voucher and Free Shipping voucher are applied simultaneously.<br>2. Total price reflects accurate deduction of item discount and shipping subsidy.<br>3. Detailed discount breakdown is clearly displayed in the Order Summary section. | High | ✅ **PASSED** | - |

| **TC_57** | Verify total payable amount is calculated correctly | - | 1. Add items<br>2. Apply voucher(s)<br>3. Proceed to checkout | "Total Payment" = Total item cost + shipping fee - total voucher discount | Medium | ✅ **PASSED** | - |

| **TC_58** | Verify total savings are displayed correctly | - | 1. Add discount-eligible items<br>2. Apply available vouchers | "Saved" = total discount (product + shipping + promotion) | Medium | ✅ **PASSED** | - |

| **TC_59** | Verify total stays unchanged when ineligible voucher is applied | - | 1. Add items not meeting voucher condition<br>2. Try to apply voucher | Voucher not applied, voucher discount remains unchanged | Medium | ✅ **PASSED** | - |

| **TC_60** | Verify that when user enables the "Use Shopee Coins" toggle, the system deducts the Shopee Coins from the total payment amount | - | 1. Go to the payment page<br>2. Enable the "Use Shopee Coins" toggle<br>3. Observe the Total Payment amount | The total payment amount is reduced by the amount of Shopee Coins applied, without exceeding the allowed limit | High | ✅ **PASSED** | - |

| **TC_61** | Verify "Place Order" button places order successfully | - | 1. Add items<br>2. Proceed to checkout<br>3. Click "Place Order" | Order is submitted, redirected to order confirmation page | High | ✅ **PASSED** | - |

### 🔹 Payment Results – Order Details

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_62** | Verify that user can successfully place an order after clicking "Place Order" | - | 1. Go to Checkout page<br>2. Ensure all required fields (shipping, payment) are valid<br>3. Click "Place Order" button | 1. System processes the order<br>2. Redirects to Order Confirmation page or Payment Gateway (depending on payment type)<br>3. Order ID is generated and shown<br>4. Confirmation notification is sent to user | High | ⚠️ **BLOCKED** | - |

| **TC_63** | Verify that user cannot place order if account balance is insufficient (excluding COD) | - | 1. Go to Checkout page<br>2. Select ShopeePay or other prepaid method<br>3. Ensure account has insufficient balance<br>4. Click "Place Order" | 1. System blocks the transaction<br>2. Show error (e.g., "Insufficient balance. Please top up to continue.")<br>3. User remains on Checkout page<br>4. Order is not created or processed | High | ✅ **PASSED** | - |

### 🔹 Others – Order Details

| ID | Summary | Test Data | Steps | Expected Result | Priority | Status | Defect |
|:---:|---|---|---|---|:---:|:---:|:---:|
| **TC_64** | Verify all products under same shop are displayed separately | Product Ax2, Product Bx1 from a same shop | 1. Go to Checkout<br>2. View product list under shop | Each product (A and B) is shown with image, name, price, and quantity | Medium | ✅ **PASSED** | - |

| **TC_65** | Verify subtotal per product and total per shop | Product A: 199.000đ x2<br>Product B: 250.000đ x1 | 1. Go to Checkout<br>2. Observe per-product subtotal and total per shop | A: 398.000đ<br>B: 250.000đ<br>Shop total: 648.000đ | Medium | ✅ **PASSED** | - |

| **TC_66** | Verify correct shop-level total after applying voucher | Shop voucher: -10k | 1. Apply shop voucher<br>2. Observe shop total | Discount applied | Medium | ✅ **PASSED** | - |

| **TC_67** | Verify insurance applies to each product individually if applicable | Insurance = +5k per product | 1. Check "Fashion insurance"<br>2. Observe additional cost per product | Insurance fee = 5k x 2 products = 10k added to total | Medium | ✅ **PASSED** | - |

| **TC_68** | Verify clear separation between products when multiple exist | - | 1. View layout on Checkout page | Proper spacing, line breaks, and separation between product rows | Medium | ✅ **PASSED** | - |

| **TC_69** | Verify user can choose between Personal and Company billing type | - | 1. Open E-Receipt form<br>2. Observe "Type" section<br>3. Tick one option | Only one option can be selected at a time; selection is retained | Medium | ✅ **PASSED** | - |

| **TC_70** | Verify user can submit valid e-receipt request and all form fields work as expected | - | 1. Open e-receipt request form<br>2. Observe "Type" section and tick Personal or Company<br>3. Leave Full Name, Address, Email blank → Submit<br>4. Enter invalid email format → Submit<br>5. Enter valid data in all fields → Submit | 1. Only one Type option (Personal/Company) can be selected at a time<br>2. Error messages shown for required fields<br>3. Error shown for invalid email<br>4. Form submits successfully with valid data<br>5. Confirmation message shown | Medium | ✅ **PASSED** | - |

| **TC_71** | Verify user can set current information as default personal billing info | - | 1. Fill in info<br>2. Toggle "Set as default Personal billing information" | Toggle works as expected, and info saved for future checkouts if ON | Medium | ✅ **PASSED** | - |

| **TC_72** | Verify user can successfully submit valid E-Receipt request | - | 1. Fill in all fields correctly<br>2. Tap "Submit Request" | Confirmation shown | Medium | ✅ **PASSED** | - |

| **TC_73** | Verify e-invoice is delivered to email within 7 working days | - | 1. Submit request<br>2. Check inbox within 7 working days (Mon–Fri, excluding Sat/Sun) | E-invoice is received within time frame; delayed only if over weekend or holiday | Medium | ✅ **PASSED** | - |

| **TC_74** | Verify default billing info is pre-filled if "Set as default" was used before | - | 1. Open E-Receipt form again after prior default save<br>2. Observe field values | Form is auto-filled with saved default info | Medium | ✅ **PASSED** | - |

| **TC_75** | Verify that clicking on the "General Transaction Terms" link redirects the user to Shopee's help website | - | 1. Go to the payment page<br>2. Scroll to the bottom near the "Place Order" button<br>3. Click on the "General Transaction Terms" hyperlink | 1. A new tab or window opens<br>2. The user is redirected to Shopee's official help page showing the General Transaction Terms | Low | ✅ **PASSED** | - |

| **TC_76** | Verify multiple shop sections are displayed when purchasing from >1 shop | - | 1. Add products from multiple shops into cart<br>2. Proceed to checkout | Payment page shows separate sections for each shop with shop name, items, and shipping method | High | ✅ **PASSED** | - |

| **TC_77** | Verify user can select different shipping methods for each shop | - | 1. On Payment page, locate shipping method per shop<br>2. Try selecting different options per shop | Each shop allows independent selection of shipping method | Medium | ✅ **PASSED** | - |

| **TC_78** | Verify user can apply different vouchers per shop if available | - | 1. On Payment page, apply shop-specific voucher for each store individually | 1. Voucher is applied to correct shop only<br>2. Total amount reflects per shop discounts | Medium | ✅ **PASSED** | - |

| **TC_79** | Verify total price includes subtotal, shipping fee, and discount per shop | - | 1. On payment page, observe the breakdown per shop<br>2. Check if total is calculated correctly | 1. Each shop shows correct subtotal<br>2. Grand total is the sum of all shop subtotals + fees - discounts | High | ✅ **PASSED** | - |
