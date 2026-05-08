# Pastel Bakery Co - High-Fidelity Screen Designs

## Complete Screen Specifications

---

## 1. Home Dashboard

### Screen Overview
The operational heart of the app - where the chef starts every day.

### Layout Specification (375px × 812px - iPhone X)

```
┌─────────────────────────────────────────┐ 0px
│ Status Bar (System)                     │
├─────────────────────────────────────────┤ 44px
│ 🎂 Good morning, Chef              🌸   │ ← Header
│ Thursday, May 8, 2026                   │
├─────────────────────────────────────────┤ 124px
│                                         │
│ TODAY'S ORDERS (5)          View All →  │ 144px
│ ───────────────────────────────         │
│                                         │
│ ┌─────────────────────────────────────┐ │ 168px
│ │ 📱 Priya Sharma             🌸      │ │
│ │ #ORD-1234 · 10:00 AM Pickup         │ │
│ │                                     │ │
│ │ • 6" Vanilla - Pineapple            │ │
│ │ • Brownie Box (12 pcs)              │ │
│ │                                     │ │
│ │ [Pending]    ₹1,725           ⋯     │ │
│ └─────────────────────────────────────┘ │
│                                         │ 288px
│ ┌─────────────────────────────────────┐ │
│ │ 💬 Amit Verma              🌸       │ │
│ │ #ORD-1235 · 2:00 PM Delivery        │ │
│ │ ...                                 │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ (3 more cards...)                       │
│                                         │
│ TOMORROW'S ORDERS (3)       View All →  │ 520px
│ ───────────────────────────────         │
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ Order preview card...               │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ QUICK STATS                             │ 640px
│ ┌─────────────┬───────────────────────┐ │
│ │  ₹15,600    │    5 Orders           │ │
│ │  Today's    │    Pending            │ │
│ │  Revenue    │    Dispatch           │ │
│ └─────────────┴───────────────────────┘ │
│                                         │
│ ┌─────────────┬───────────────────────┐ │
│ │  Pineapple  │    3 Repeat           │ │
│ │  Cake       │    Customers          │ │
│ │  Top Seller │    This Week          │ │
│ └─────────────┴───────────────────────┘ │
│                                         │
│                                         │
│                                         │
│                [+]                      │ ← FAB at 740px
│           New Order                     │
│                                         │
│                                         │
├─────────────────────────────────────────┤ 740px
│   🏠     📅      📖      📊            │
│  Home Calendar  Menu   Reports          │
└─────────────────────────────────────────┘ 812px
```

### Detailed Element Specifications

#### Header (44px - 124px)
```
Padding: 20px 24px
Background: Linear gradient
  - Top: #FFFBF7
  - Bottom: transparent (fade to page background)

Greeting:
- Font: Playfair Display Semibold
- Size: 28px
- Color: #5C3A2E
- Line height: 36px

Date:
- Font: Inter Regular
- Size: 14px
- Color: #8B6E5F
- Margin top: 4px

Floral Decoration:
- Position: Absolute right 24px, top 24px
- Size: 48px × 48px
- Opacity: 0.25
- Color: Soft pink watercolor
```

#### Section Header ("Today's Orders")
```
Padding: 0 24px
Margin: 20px 0 12px 0
Display: Flex, space-between

Title:
- Font: Inter Semibold
- Size: 13px
- Text Transform: Uppercase
- Letter Spacing: 0.8px
- Color: #8B6E5F

Count:
- Display: Inline
- Color: #D4949A
- Background: #FFE8E8
- Padding: 2px 8px
- Border Radius: 12px
- Font: Inter Medium
- Size: 11px

"View All" Link:
- Font: Inter Medium
- Size: 13px
- Color: #D4949A
- Icon: Chevron right, 14px
```

#### Order Card (See Component Library for full spec)
```
Margin: 0 24px 12px 24px
(Follows Order Card component specification)

Additional Home-specific:
- Reveal on scroll: Stagger animation
- Entry delay: 60ms per card
- Animation: translateY(16px) → translateY(0), opacity 0 → 1
```

#### Quick Stats Grid
```
Padding: 0 24px
Margin top: 24px
Display: Grid
Grid: 2 columns × 2 rows
Gap: 12px

Stat Card:
- Follows Stat Card component spec
- Aspect Ratio: 1:1 (square-ish)
- Padding: 16px
```

#### Floating Action Button
```
Position: Fixed
Bottom: 88px (above tab bar + 16px)
Right: 24px
Z-index: 100

Button:
- Width: Auto (fit content)
- Height: 56px
- Padding: 16px 24px
- Background: Linear gradient #FFB5B5 → #FF9E9E
- Border Radius: 28px
- Shadow: 0 8px 24px rgba(255, 181, 181, 0.4)

Icon:
- Size: 24px × 24px
- Color: #5C3A2E
- Margin right: 8px

Text:
- Font: Inter Semibold
- Size: 16px
- Color: #5C3A2E
```

### Scroll Behavior
- **Pull to refresh:** Elastic scroll reveals refresh indicator
- **Header collapse:** Greeting shrinks to 20px text in nav bar on scroll
- **FAB hide:** Hides on scroll down, reveals on scroll up
- **Infinite scroll:** Load more past orders at bottom

### Loading State
```
- Skeleton cards (3 visible)
- Quick stats: Skeleton boxes
- Header: Loads immediately
- Animation: Shimmer wave
```

### Empty State
```
Center aligned, min-height: 400px

Illustration:
- Floating floral arrangement
- Size: 200px × 200px
- Colors: Soft pastels

Heading:
- "No orders today!"
- Playfair Display Semibold, 24px

Subheading:
- "Time to relax 🌸"
- Inter Regular, 15px, #8B6E5F

CTA:
- Primary button: "Create Your First Order"
```

---

## 2. Calendar - Month View

### Layout Specification

```
┌─────────────────────────────────────────┐ 0px
│ Status Bar                              │
├─────────────────────────────────────────┤ 44px
│ ←    May 2026    →         Today   ⋯   │ ← Header
├─────────────────────────────────────────┤ 100px
│                                         │
│  Su  Mo  Tu  We  Th  Fr  Sa            │ 120px
│                                         │
│  ┌───┬───┬───┬───┬───┬───┬───┐         │
│  │   │   │   │ 1 │ 2 │ 3 │ 4 │         │
│  │   │   │   │   │ ● │   │ ●●│         │
│  └───┴───┴───┴───┴───┴───┴───┘         │
│  ┌───┬───┬───┬───┬───┬───┬───┐         │
│  │ 5 │ 6 │ 7 │ 8 │ 9 │10 │11 │         │
│  │ ● │   │ ● │[●]│●●●│●● │ ● │         │ ← May 8 selected
│  └───┴───┴───┴───┴───┴───┴───┘         │
│  ┌───┬───┬───┬───┬───┬───┬───┐         │
│  │12 │13 │14 │15 │16 │17 │18 │         │
│  │   │ ● │   │●●●│ ● │●● │   │         │
│  └───┴───┴───┴───┴───┴───┴───┘         │
│  ┌───┬───┬───┬───┬───┬───┬───┐         │
│  │19 │20 │21 │22 │23 │24 │25 │         │
│  │ ● │   │   │ ● │●● │ ● │●● │         │
│  └───┴───┴───┴───┴───┴───┴───┘         │
│  ┌───┬───┬───┬───┬───┬───┬───┐         │
│  │26 │27 │28 │29 │30 │31 │   │         │
│  │   │ ● │●● │ ● │ ● │   │   │         │
│  └───┴───┴───┴───┴───┴───┴───┘         │
│                                         │ 420px
├─────────────────────────────────────────┤
│ May 8, 2026 (4 orders)        Day View →│ 440px
│ ─────────────────────────────────       │
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ 📱 9:00 AM Pickup                   │ │
│ │ Neha Kapoor                         │ │
│ │ #ORD-1240 · ₹1,500                  │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ 🚚 11:30 AM Delivery                │ │
│ │ Amit Verma                          │ │
│ │ #ORD-1241 · ₹2,200                  │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ (2 more cards...)                       │
│                                         │
│                                         │
│                [+]                      │
│           New Order                     │
│                                         │
├─────────────────────────────────────────┤
│   🏠     📅      📖      📊            │
│  Home Calendar  Menu   Reports          │
└─────────────────────────────────────────┘
```

### Calendar Grid Specifications

```
Container:
- Padding: 0 16px
- Margin top: 20px

Day Labels (Su, Mo, etc.):
- Font: Inter Medium, 12px
- Color: #A68976
- Text align: Center
- Margin bottom: 8px

Day Cell:
- Size: (100vw - 32px - 48px) / 7 ≈ 48px
- Aspect ratio: 1:1
- Border Radius: 8px
- Padding: 4px

Day Number:
- Font: Inter Semibold, 15px
- Color: #5C3A2E
- Text align: Center

Order Indicators (Dots):
- Position: Below number
- Dot size: 4px × 4px
- Gap: 2px
- Margin top: 2px

Single dot: #FFB5B5
Two dots: #FFB5B5 #FFB5B5
Three dots: #F4C896 #F4C896 #F4C896 (warning)

States:
- Today: Border 2px solid #FFB5B5
- Selected: Background #FFE8E8
- Other month: Opacity 0.3
- Past: Opacity 0.6
- Hover: Background #FFF5ED
```

### Day Orders Section

```
Background: #FFFBF7
Border top: 1px solid #F4E4D7
Padding: 20px 24px
Max height: 340px
Overflow: Scroll

Header:
- Font: Playfair Display Semibold, 18px
- Color: #5C3A2E
- Flex: space-between

Order Count:
- Display: inline
- Font: Inter Medium, 14px
- Color: #8B6E5F

"Day View" Link:
- Font: Inter Medium, 13px
- Color: #D4949A
- Icon: Chevron right

Order Cards (Compact):
- Height: 72px
- Simplified layout
- Icon + Time (left)
- Customer name + ID (center)
- Price (right)
```

### Capacity Warning

When day has 8+ orders:
```
Banner (Above selected day):
┌─────────────────────────────────────┐
│ ⚠️ High capacity day!               │
│ Consider spacing out orders         │
│                              [Got it]│
└─────────────────────────────────────┘

Background: #FFF9F0
Border: 1px solid #F4C896
Border Radius: 12px
Padding: 12px 16px
Margin: 0 16px 12px 16px
```

---

## 3. Calendar - Day View

### Layout Specification

```
┌─────────────────────────────────────────┐
│ ←  Thursday, May 8           ⋯    Month │
├─────────────────────────────────────────┤
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ 4 orders · ₹5,400 total             │ │
│ │ 2 Pickups · 2 Deliveries             │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ MORNING (9 AM - 12 PM)                  │
│ ───────────────────────────────         │
│                                         │
│ 9:00 AM                                 │
│ ┌─────────────────────────────────────┐ │
│ │ 🎂 Neha Kapoor              🌸      │ │
│ │ #ORD-1240 · Pickup                  │ │
│ │                                     │ │
│ │ • 8" Chocolate Truffle              │ │
│ │                                     │ │
│ │ [In Progress]   ₹1,500        ⋯     │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ 11:30 AM                                │
│ ┌─────────────────────────────────────┐ │
│ │ Order card...                       │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ AFTERNOON (12 PM - 5 PM)                │
│ ───────────────────────────────         │
│                                         │
│ 2:00 PM                                 │
│ ┌─────────────────────────────────────┐ │
│ │ Order card...                       │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ 4:30 PM                                 │
│ ┌─────────────────────────────────────┐ │
│ │ Order card...                       │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ EVENING (5 PM - 9 PM)                   │
│ ───────────────────────────────         │
│ (No orders)                             │
│                                         │
│                [+]                      │
│         Add Order for May 8             │
│                                         │
├─────────────────────────────────────────┤
│   🏠     📅      📖      📊            │
└─────────────────────────────────────────┘
```

### Summary Card (Top)
```
Padding: 0 24px
Margin: 16px 0

Card:
- Background: #FFF5ED
- Border: 1px solid #E8B4B8
- Border Radius: 12px
- Padding: 16px

Primary Stats:
- Font: Playfair Display Semibold, 20px
- Color: #5C3A2E

Secondary:
- Font: Inter Regular, 14px
- Color: #8B6E5F
- Margin top: 4px
```

### Time Block Headers
```
Font: Inter Semibold, 12px
Text Transform: Uppercase
Letter Spacing: 0.8px
Color: #A68976
Margin: 24px 24px 12px 24px
Divider: 1px solid #F4E4D7 (right side of text)
```

### Time Label
```
Font: Inter Medium, 14px
Color: #D4949A
Margin: 16px 24px 8px 24px
```

### Navigation
- Swipe left: Next day
- Swipe right: Previous day
- Header arrows: Navigate days
- "Month" button: Return to month view

---

## 4. New Order Form - Step 1 (Customer Info)

### Layout Specification

```
┌─────────────────────────────────────────┐
│ ×  New Order                       1/4  │
├─────────────────────────────────────────┤
│ ●───○───○───○                           │ ← Progress
│                                         │
│ Customer Information                    │
│                                         │
│ Customer Name *                         │
│ ┌─────────────────────────────────────┐ │
│ │ Priya Sharma                        │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Phone Number *                          │
│ ┌─────────────────────────────────────┐ │
│ │ +91 98765 43210                     │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ 💝 Repeat Customer                  │ │
│ │ Priya has ordered 3 times before    │ │
│ │                     View History →  │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ ☐ Add to quick contacts                │
│                                         │
│                                         │
│                                         │
│                                         │
│                                         │
│                                         │
│              [Next →]                   │
│                                         │
├─────────────────────────────────────────┤
│ (Keyboard area)                         │
└─────────────────────────────────────────┘
```

### Form Specifications

```
Container:
- Background: #FFFBF7
- Padding: 24px
- Presented as: Bottom sheet (iOS) or Full screen (Android)

Close Button (×):
- Position: Top-left
- Size: 44px × 44px
- Icon: 24px, #8B6E5F
- Tap: Show discard confirmation

Progress Indicator (1/4):
- Position: Top-right
- Font: Inter Medium, 14px
- Color: #A68976

Progress Dots:
- Margin: 20px 0
- (See component library)

Section Title:
- Font: Playfair Display Semibold, 24px
- Color: #5C3A2E
- Margin bottom: 24px

Form Fields:
- (Follow Text Input component)
- Gap: 20px

Repeat Customer Banner:
- Background: Linear gradient #FFF0F5 → #FFF8F3
- Border: 1px solid #FFB5B5
- Border Radius: 12px
- Padding: 16px
- Icon: 💝 emoji, 24px
- Font: Inter Medium, 14px
- Link: "View History", #D4949A

Checkbox:
- (Follow Checkbox component)
- Margin top: 16px

Next Button:
- Position: Fixed bottom (above keyboard)
- Width: calc(100% - 48px)
- Margin: 0 24px 24px 24px
- (Follow Primary Button component)
```

### Validation
- Required fields show red border if empty on "Next" tap
- Phone validates format: +91 XXXXX XXXXX
- Shake animation for errors

---

## 5. New Order Form - Step 3 (Select Items)

### Layout Specification

```
┌─────────────────────────────────────────┐
│ ←  Select Items                    3/4  │
├─────────────────────────────────────────┤
│ ●───●───●───○                           │
│                                         │
│ Search products...                      │
│ ┌─────────────────────────────────────┐ │
│ │ 🔍                                  │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ VANILLA CAKES                    🌸     │
│ ───────────────────────────────         │
│                                         │
│ ┌─────────────┬─────────────────────┐   │
│ │ [Image]     │     [Image]         │   │
│ │             │                     │   │
│ │ Pineapple   │     Blueberry       │   │
│ │ ₹850 / ₹1500│     ₹850 / ₹1500    │   │
│ │ 6" | 8"     │     6" | 8"         │   │
│ │ [- 1 +]     │     [- 0 +]         │   │
│ └─────────────┴─────────────────────┘   │
│                                         │
│ ┌─────────────┬─────────────────────┐   │
│ │ Caramel     │     Rasmalai        │   │
│ │ Butterscotch│                     │   │
│ │ ...         │     ...             │   │
│ └─────────────┴─────────────────────┘   │
│                                         │
│ CHOCOLATE CAKES                   🍫    │
│ ───────────────────────────────         │
│                                         │
│ (Products grid...)                      │
│                                         │
│ ┌─────────────────────────────────────┐ │ ← Sticky
│ │ 2 items selected              ₹1,725 │ │
│ │              [Review Order →]       │ │
│ └─────────────────────────────────────┘ │
├─────────────────────────────────────────┤
│   🏠     📅      📖      📊            │
└─────────────────────────────────────────┘
```

### Product Selection Grid

```
Padding: 0 24px
Gap: 12px
Grid: 2 columns

Product Card (See component library for base):
- Width: (100vw - 48px - 12px) / 2

Quantity Selector:
┌───────────────┐
│  -   1   +   │
└───────────────┘

Container:
- Flex row, space-between
- Width: 100%
- Margin top: 8px

Minus Button:
- Size: 32px × 32px
- Border: 1.5px solid #E8D4C9
- Border Radius: 8px
- Icon: Minus, 16px, #8B6E5F
- Disabled when quantity = 0

Quantity:
- Font: Inter Semibold, 16px
- Color: #5C3A2E
- Min width: 32px
- Text align: Center

Plus Button:
- Size: 32px × 32px
- Background: #FFE8E8
- Border: 1.5px solid #FFB5B5
- Border Radius: 8px
- Icon: Plus, 16px, #D4949A
```

### Size Selector (Expanded State)

When product card is tapped:
```
Bottom Sheet:
┌─────────────────────────────────────┐
│           ────                      │
│                                     │
│ Pineapple Vanilla Cake              │
│                                     │
│ [Large Product Image]               │
│                                     │
│ Moist vanilla sponge with fresh     │
│ pineapple chunks...                 │
│                                     │
│ Select Size *                       │
│ ( ) 6 inch  ₹850   (600-650g)      │
│ (●) 8 inch  ₹1500  (1100-1200g)    │
│                                     │
│ Quantity                            │
│ [-  1  +]                           │
│                                     │
│ Special Instructions (Optional)     │
│ ┌─────────────────────────────────┐ │
│ │ e.g., "No nuts" or message      │ │
│ └─────────────────────────────────┘ │
│                                     │
│              [Add ₹850]             │
│                                     │
└─────────────────────────────────────┘
```

### Sticky Cart Footer

```
Position: Fixed bottom, above tab bar
Background: #FFFFFF
Border top: 1px solid #E8D4C9
Shadow: 0 -4px 16px rgba(92, 58, 46, 0.08)
Padding: 16px 24px
Z-index: 10

Content:
- Flex row, space-between

Left:
- "2 items selected" - Inter Medium, 14px, #8B6E5F
- Total price - Playfair Display Semibold, 20px, #5C3A2E

Right:
- Primary button: "Review Order →"
- Padding: 12px 20px
```

---

## 6. Menu Screen

### Layout Specification

```
┌─────────────────────────────────────────┐
│ Our Menu                       [Share]  │
├─────────────────────────────────────────┤
│ Search menu...                          │
│ ┌─────────────────────────────────────┐ │
│ │ 🔍                                  │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ [Hero Image / Brand Banner]         │ │
│ │ Handcrafted with love 🌸            │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ VANILLA CAKES                    🌸     │
│ Our signature collection                │
│                                         │
│ ┌─────────────┬─────────────────────┐   │
│ │ [Image]     │     [Image]         │   │
│ │             │                     │   │
│ │ Pineapple 💝│     Blueberry       │   │ ← 💝 = Popular
│ │ ₹850 / ₹1500│     ₹850 / ₹1500    │   │
│ │ 6" | 8"     │     6" | 8"         │   │
│ └─────────────┴─────────────────────┘   │
│                                         │
│ ┌─────────────┬─────────────────────┐   │
│ │ Caramel     │     Rasmalai        │   │
│ │ Butterscotch│                     │   │
│ │ ...         │     ...             │   │
│ └─────────────┴─────────────────────┘   │
│                                         │
│ (More rows...)                          │
│                                         │
│ CHOCOLATE CAKES                   🍫    │
│ Rich and indulgent                      │
│                                         │
│ (Products grid...)                      │
│                                         │
│ BROWNIES                          💝    │
│ (Products...)                           │
│                                         │
│ CHEESECAKES                       🧈    │
│ (Products...)                           │
│                                         │
├─────────────────────────────────────────┤
│   🏠     📅      📖      📊            │
└─────────────────────────────────────────┘
```

### Hero Banner

```
Height: 200px
Background: Linear gradient
  - Start: #FFF5ED
  - End: #FFE8E8
Border Radius: 0 0 24px 24px
Padding: 32px 24px
Position: Relative

Decorative:
- Large floral: 120px, top-right, opacity 0.3
- Small florals: Scattered, various sizes

Text:
- Font: Cormorant Garamond Regular
- Size: 24px
- Style: Italic
- Color: #5C3A2E
- Text align: Center
```

### Category Section Header

```
Padding: 0 24px
Margin: 32px 0 12px 0

Title:
- Font: Playfair Display Semibold
- Size: 22px
- Color: #5C3A2E
- Inline emoji: 24px

Description:
- Font: Inter Regular
- Size: 14px
- Color: #8B6E5F
- Margin top: 4px
```

### Share Menu Sheet

```
Bottom Sheet:
┌─────────────────────────────────────┐
│           ────                      │
│                                     │
│ Share Menu                          │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 📄 PDF Document                 │ │
│ │ Formatted menu with prices      │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 📱 WhatsApp Image               │ │
│ │ Single image, easy to share     │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 📸 Instagram Story              │ │
│ │ Vertical format, 9:16           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 🔗 Share Link                   │ │
│ │ Live web version                │ │
│ └─────────────────────────────────┘ │
│                                     │
│            [Cancel]                 │
│                                     │
└─────────────────────────────────────┘

Option Cards:
- Background: #FFFBF7
- Border: 1px solid #F4E4D7
- Border Radius: 12px
- Padding: 16px
- Gap: 16px
- Hover: Background #FFF5ED

Icon:
- Size: 32px
- Color: Matches emoji tone

Title:
- Font: Inter Semibold, 16px
- Color: #5C3A2E

Description:
- Font: Inter Regular, 13px
- Color: #8B6E5F
- Margin top: 2px
```

---

## 7. Reports & Analytics

### Layout Specification

```
┌─────────────────────────────────────────┐
│ Reports                    ← May 2026 → │
├─────────────────────────────────────────┤
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │           ₹45,600                   │ │
│ │       Total Revenue                 │ │
│ │   ↑ 12% from last month             │ │
│ │                                     │ │
│ │   32 Orders  ·  18 Repeat (56%)     │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Revenue Trend                           │
│ ┌─────────────────────────────────────┐ │
│ │     [Line Chart]                    │ │
│ │                                     │ │
│ │     Week-by-week revenue            │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Best Sellers                            │
│ ┌─────────────────────────────────────┐ │
│ │ 1. 6" Pineapple Cake        12 sold │ │
│ │ 2. Brownie Box               9 sold │ │
│ │ 3. Classic Truffle           7 sold │ │
│ │ 4. Rasmalai Cake             5 sold │ │
│ │ 5. Cookies & Cream           4 sold │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Platform Breakdown                      │
│ ┌─────────────────────────────────────┐ │
│ │                                     │ │
│ │       [Donut Chart]                 │ │
│ │                                     │ │
│ │ 📱 Instagram    45%                 │ │
│ │ 💬 WhatsApp     30%                 │ │
│ │ 💝 Repeat       15%                 │ │
│ │ 📞 Phone        10%                 │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ 💡 Insights                             │
│ ┌─────────────────────────────────────┐ │
│ │ 🎂 Cupcakes performed 35% better   │ │
│ │    this month                       │ │
│ └─────────────────────────────────────┘ │
│ ┌─────────────────────────────────────┐ │
│ │ 📆 Weekends drive highest custom   │ │
│ │    cake orders                      │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Busiest Day                             │
│ Saturday, May 15 (7 orders)             │
│                                         │
├─────────────────────────────────────────┤
│   🏠     📅      📖      📊            │
└─────────────────────────────────────────┘
```

### Revenue Summary Card (Top)

```
Background: Linear gradient
  - Start: #FFF8F3
  - End: #FFF0F5
Border: 1px solid rgba(255, 181, 181, 0.3)
Border Radius: 16px
Padding: 24px
Margin: 16px 24px 24px 24px
Text align: Center

Main Value:
- Font: Playfair Display Semibold, 48px
- Color: #5C3A2E
- Letter spacing: -1px

Label:
- Font: Inter Medium, 15px
- Color: #8B6E5F
- Margin top: 4px

Change Indicator:
- Font: Inter Semibold, 14px
- Color: #7A9475 (positive)
- Icon: ↑ arrow, 16px
- Margin top: 8px

Secondary Stats:
- Font: Inter Regular, 14px
- Color: #8B6E5F
- Margin top: 12px
- Separator: "·" character
```

### Chart Containers

```
Margin: 0 24px 24px 24px
Background: #FFFBF7
Border: 1px solid #F4E4D7
Border Radius: 16px
Padding: 20px

Title:
- Font: Inter Semibold, 16px
- Color: #5C3A2E
- Margin bottom: 16px

Chart:
- Height: 240px (line/bar)
- Size: 200px (donut)
- (Follow chart specifications from component library)
```

### Best Sellers List

```
Each Item:
- Padding: 12px 0
- Border bottom: 1px solid #F4E4D7
- Last item: No border

Number:
- Font: Playfair Display Semibold, 18px
- Color: #D4949A
- Width: 28px

Name:
- Font: Inter Medium, 15px
- Color: #5C3A2E
- Flex: 1

Count:
- Font: Inter Regular, 14px
- Color: #8B6E5F
- Right aligned
```

### Insight Cards

```
Background: Linear gradient
  - Start: #FFF8F3
  - End: #FFFBF7
Border Left: 3px solid #FFB5B5
Border Radius: 8px
Padding: 16px
Margin: 0 24px 12px 24px

Icon:
- Emoji: 24px
- Float left
- Margin right: 12px

Text:
- Font: Inter Medium, 14px
- Color: #5C3A2E
- Line height: 22px
```

---

## 8. Order Details Screen

### Layout Specification

```
┌─────────────────────────────────────────┐
│ ←  Order Details                   ⋯   │
├─────────────────────────────────────────┤
│                                         │
│ ┌─────────────────────────────────────┐ │
│ │ [Pending]          #ORD-1234        │ │
│ │                                     │ │
│ │ May 8, 2026 · 2:00 PM              │ │
│ │ Pickup · Birthday                   │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Customer                                │
│ ┌─────────────────────────────────────┐ │
│ │ PS  Priya Sharma                    │ │
│ │     +91 98765 43210                 │ │
│ │                                     │ │
│ │     [📞 Call]  [💬 Message]        │ │
│ │                                     │ │
│ │     💝 Repeat Customer (3 orders)   │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Order Details                           │
│ ┌─────────────────────────────────────┐ │
│ │ Platform        📱 Instagram        │ │
│ │ Occasion        🎂 Birthday         │ │
│ │ Ordered On      May 5, 2026         │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Items                                   │
│ ┌─────────────────────────────────────┐ │
│ │ 1× 6" Vanilla - Pineapple           │ │
│ │    ₹850                             │ │
│ │                                     │ │
│ │ 1× Brownie Box (12 pcs)             │ │
│ │    Hazelnut topping                 │ │
│ │    ₹875                             │ │
│ ├─────────────────────────────────────┤ │
│ │ Subtotal                     ₹1,725 │ │
│ │ Total                        ₹1,725 │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Special Instructions                    │
│ ┌─────────────────────────────────────┐ │
│ │ "Write 'Happy Birthday Ananya'      │ │
│ │  with pink frosting"                │ │
│ └─────────────────────────────────────┘ │
│                                         │
│ Timeline                                │
│ ┌─────────────────────────────────────┐ │
│ │ ● Order Created                     │ │
│ │   May 5, 2026 · 3:45 PM             │ │
│ │                                     │ │
│ │ ○ In Progress                       │ │
│ │   (Not started)                     │ │
│ │                                     │ │
│ │ ○ Ready for Pickup                  │ │
│ │   (Pending)                         │ │
│ │                                     │ │
│ │ ○ Completed                         │ │
│ │   (Pending)                         │ │
│ └─────────────────────────────────────┘ │
│                                         │
│          [Mark as Complete]             │
│                                         │
├─────────────────────────────────────────┤
│ (Safe area)                             │
└─────────────────────────────────────────┘
```

### Status Header

```
Background: Gradient based on status
  - Pending: #FFF9F0 → #FFF8F3
  - In Progress: #F5F8FF → #FFF8F3
  - Completed: #F0F5EF → #FFF8F3

Border Radius: 16px
Padding: 20px
Margin: 16px 24px

Status Badge:
- Position: Top-left
- (Follow badge component)

Order ID:
- Position: Top-right
- Font: Inter Medium, 14px
- Color: #A68976

Date/Time:
- Font: Inter Regular, 16px
- Color: #5C3A2E
- Margin top: 24px

Type:
- Font: Inter Regular, 14px
- Color: #8B6E5F
- Separated by "·"
```

### Section Cards

```
Background: #FFFBF7
Border: 1px solid #F4E4D7
Border Radius: 12px
Padding: 20px
Margin: 0 24px 16px 24px

Section Title:
- Font: Inter Semibold, 15px
- Color: #5C3A2E
- Margin bottom: 16px

Customer Section:
- Avatar: 48px × 48px (large)
- Name: Playfair Display Semibold, 20px
- Phone: Inter Regular, 15px, #8B6E5F

Action Buttons:
- Flex row, gap 12px
- Secondary button style
- Icon + text
- Margin top: 16px

Order Details:
- Row layout: Label | Value
- Label: Inter Medium, 14px, #8B6E5F
- Value: Inter Regular, 15px, #5C3A2E
- Row padding: 12px 0
- Border bottom: 1px solid #F4E4D7
```

### Items List

```
Each Item:
- Padding: 16px 0
- Border bottom: 1px dashed #F4E4D7

Quantity × Name:
- Font: Inter Medium, 15px
- Color: #5C3A2E

Customization:
- Font: Inter Regular, 13px
- Color: #8B6E5F
- Margin top: 4px
- Margin left: 16px

Price:
- Font: Inter Semibold, 15px
- Color: #5C3A2E
- Right aligned

Totals:
- Padding: 16px 0
- Font: Inter Semibold, 16px
- Total: Bold, 18px
```

### Timeline

```
Vertical stepper

Each Step:
- Padding: 12px 0

Connector Line:
- Width: 2px
- Height: 32px
- Color: #F4E4D7 (inactive) or #FFB5B5 (active)
- Position: Left of circle

Circle:
- Size: 12px × 12px
- Border: 2px solid #F4E4D7 (inactive)
- Background: #FFB5B5 (active)
- Position: Left

Label:
- Font: Inter Medium, 15px
- Color: #5C3A2E (active) or #A68976 (inactive)

Timestamp:
- Font: Inter Regular, 13px
- Color: #8B6E5F
- Margin left: 24px
```

---

## 9. Splash Screen & Onboarding

### Splash Screen

```
┌─────────────────────────────────────────┐
│                                         │
│                                         │
│                                         │
│            [Large Brand Mark]           │
│                                         │
│         Pastel Bakery Co                │
│                                         │
│              🌸                         │
│                                         │
│                                         │
│                                         │
│                                         │
└─────────────────────────────────────────┘

Background: Linear gradient
  - Top: #FFF8F3
  - Bottom: #FFE8E8

Brand Mark:
- Size: 120px × 120px
- Style: Elegant logo or illustrated cupcake
- Colors: Pink gradient

App Name:
- Font: Playfair Display Semibold
- Size: 32px
- Color: #5C3A2E
- Letter spacing: 0.5px

Floral:
- Scattered small florals
- Opacity: 0.2
- Gentle fade-in animation

Duration: 2 seconds
Animation: Gentle fade in of all elements
```

### Onboarding - Slide 1

```
┌─────────────────────────────────────────┐
│                 ×                       │ ← Skip
│                                         │
│                                         │
│        [Illustration]                   │
│     Dashboard with order cards          │
│         200px × 200px                   │
│                                         │
│                                         │
│     Manage Your Orders                  │
│                                         │
│     Track every order from creation     │
│     to delivery with ease               │
│                                         │
│                                         │
│           ● ○ ○                         │ ← Indicator
│                                         │
│              [Next →]                   │
│                                         │
└─────────────────────────────────────────┘

Background: #FFFBF7

Illustration:
- Style: Elegant line art with soft colors
- Colors: Pinks, peaches, creams
- Size: 200px × 200px
- Centered

Heading:
- Font: Playfair Display Semibold, 28px
- Color: #5C3A2E
- Text align: Center
- Margin top: 32px

Description:
- Font: Inter Regular, 16px
- Color: #8B6E5F
- Text align: Center
- Line height: 24px
- Max width: 280px
- Margin: 16px auto

Page Indicator:
- 3 dots
- Active: #FFB5B5, 8px × 8px
- Inactive: #E8D4C9, 6px × 6px
- Gap: 8px

Next Button:
- Primary button
- Width: 60%
- Centered
- Margin bottom: 40px
```

---

This comprehensive screen design document provides pixel-perfect specifications for building the complete Pastel Bakery Co application with its elegant, handcrafted aesthetic.
