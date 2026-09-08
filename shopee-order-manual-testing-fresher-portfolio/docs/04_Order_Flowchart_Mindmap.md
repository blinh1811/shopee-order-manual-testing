# ORDER FLOWCHART & QA TESTING MINDMAP

Visual diagrams illustrating the Shopee E-Commerce ordering workflow, functional decomposition, and error-handling paths.

---

## 1. End-to-End Order & Checkout Flowchart

```mermaid
flowchart TD
    Start([User browsing product]) --> Action{User Action}
    Action -->|"Add to Cart"| Cart[Cart Page]
    Action -->|"Buy Now"| Checkout[Checkout Page]

    Cart --> SelectItems[Select item checkboxes]
    SelectItems --> Proceed[Click 'Checkout']
    Proceed --> Checkout

    subgraph Checkout_Verification [Checkout Verification & Configuration]
        Checkout --> AddrCheck{Valid Address?}
        AddrCheck -->|No| AddAddr[Add / Edit Shipping Address]
        AddAddr --> AddrCheck
        AddrCheck -->|Yes| CrossBorder{Cross-border item?}
        
        CrossBorder -->|Yes| CheckID{Citizen ID Verified?}
        CheckID -->|No| InputID[Input 12-digit Citizen ID]
        InputID --> CheckID
        CheckID -->|Yes| ShipMethod[Select Shipping Channel: Standard/Express/Economy]
        CrossBorder -->|No| ShipMethod

        ShipMethod --> VoucherSection[Select Shopee & Shop Vouchers]
        VoucherSection --> CoinToggle[Toggle Shopee Coins Redemption]
        CoinToggle --> InvoiceOption{Request VAT Invoice?}
        
        InvoiceOption -->|Yes| FillTax[Fill Company/Personal Tax Information]
        FillTax --> PayMethod[Select Payment Method]
        InvoiceOption -->|No| PayMethod
        
        PayMethod --> RecalcTotal[System Recalculates Order Grand Total]
    end

    RecalcTotal --> PlaceOrderBtn[Click 'Place Order']
    
    subgraph Order_Processing [Order Execution & Gateway Processing]
        PlaceOrderBtn --> PayChoice{Payment Type}
        PayChoice -->|COD| ConfirmOrder[Order Created: Status 'To Ship']
        PayChoice -->|ShopeePay| WalletAuth[Biometric / PIN Verification]
        PayChoice -->|Credit Card / Bank| GatewayAuth[3D-Secure OTP Authorization]
        PayChoice -->|SPayLater| CreditCheck[Check Available SPayLater Limit]
        
        WalletAuth --> AuthCheck{Success?}
        GatewayAuth --> AuthCheck
        CreditCheck --> AuthCheck
        
        AuthCheck -->|Yes| ConfirmOrder
        AuthCheck -->|No| FailScreen[Display Payment Error & Allow Retry]
        FailScreen --> PayMethod
    end

    ConfirmOrder --> EndNode([Order Confirmation & Tracking Notification])
```

---

## 2. Functional Decomposition Mindmap

```mermaid
mindmap
  root((Shopee Order Testing))
    Cart & Buy Now
      Add single / multiple items
      Quantity adjustments
      Instant Buy Now redirection
    Shipping & Address
      Default address selection
      Inline address editing
      New address form validation
      Cross-border Citizen ID verification
    Shop & Items
      Multi-seller product grouping
      Variation & SKU display
      Stock availability warnings
      Shop-level subtotals
    Logistics Options
      Standard Express
      Instant / Express Delivery
      Economy Shipping
      Delivery insurance option
    Discounts & Promotions
      Platform discount vouchers
      Shop discount vouchers
      Free shipping subsidies
      Shopee coins redemption
    Payment Processing
      Cash on Delivery COD
      ShopeePay e-wallet
      Credit / Debit Card 3D-Secure
      SPayLater installments
    Invoicing & VAT
      Personal e-receipt
      Company tax invoice
      Default billing persistence
```

---

## 3. Voucher Stacking & Price Calculation Logic

```mermaid
flowchart LR
    Subtotal[Item Subtotal] --> PlusShip[+ Shipping Fee]
    PlusShip --> PlusIns[+ Product / Shipping Insurance]
    PlusIns --> MinusShopVoucher[- Shop Voucher Discount]
    MinusShopVoucher --> MinusPlatformVoucher[- Platform Voucher Discount]
    MinusPlatformVoucher --> MinusShipVoucher[- Free Shipping Subsidy]
    MinusShipVoucher --> MinusCoins[- Shopee Coins: max 50% total]
    MinusCoins --> FinalTotal[= Grand Total Amount Due]
```
