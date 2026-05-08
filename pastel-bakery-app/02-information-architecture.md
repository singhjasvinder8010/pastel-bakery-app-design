# Pastel Bakery Co - Information Architecture

## App Structure Overview

```
Pastel Bakery Co App
│
├── 🏠 Home Dashboard (Default landing)
│   ├── Today's Orders
│   ├── Tomorrow's Orders
│   ├── Quick Stats Widget
│   ├── Quick Actions (+ Add Order)
│   └── Dispatch Queue
│
├── 📅 Calendar
│   ├── Month View
│   ├── Day View
│   ├── Order Density Indicators
│   ├── Capacity Warnings
│   └── New Order Creation
│
├── 📖 Menu
│   ├── Product Categories
│   │   ├── Vanilla Cakes
│   │   ├── Chocolate Cakes
│   │   ├── Brownies
│   │   └── Cheesecakes
│   ├── Product Details
│   ├── Share Menu
│   │   ├── PDF Export
│   │   ├── WhatsApp Image
│   │   └── Instagram Story
│   └── Quick Order from Menu
│
├── 📊 Reports & Analytics
│   ├── Monthly Overview
│   ├── Revenue Trends
│   ├── Best Sellers
│   ├── Customer Insights
│   ├── Platform Breakdown
│   └── Custom Date Range
│
└── ⚙️ Settings (Future Phase)
    ├── Profile
    ├── Business Info
    ├── Notification Preferences
    └── App Customization
```

---

## Primary Navigation

**Bottom Tab Bar** - 4 main sections (always visible)

```
┌─────────────────────────────────────────────────────┐
│                                                     │
│                  Content Area                       │
│                                                     │
├─────────────────────────────────────────────────────┤
│   🏠        📅         📖         📊              │
│  Home    Calendar    Menu    Reports              │
└─────────────────────────────────────────────────────┘
```

### Icon Treatments
- Active: Pink (#FFB5B5) with filled icon
- Inactive: Muted brown (#A68976) with outline icon
- Label: Always visible (small)
- Active indicator: Subtle glow, no heavy underline

---

## Screen Hierarchy

### Level 1: Bottom Tabs
- Home Dashboard
- Calendar
- Menu
- Reports

### Level 2: Full-Screen Views
- Individual Order Details
- New Order Form
- Product Detail
- Monthly Report Details

### Level 3: Overlays
- Bottom Sheets (Quick Actions)
- Modals (Confirmations)
- Toasts (Success/Error feedback)

---

## Navigation Patterns

### Pattern 1: Tab-Based
Used for: Main sections
Behavior: Tap bottom tab → Instant switch

### Pattern 2: Stack-Based
Used for: Drill-down flows
Behavior: 
- Tap card → Slide in detail view
- Back button (top-left) → Slide back
- Swipe right edge → Go back

### Pattern 3: Modal/Sheet
Used for: Quick actions, forms
Behavior:
- Slide up from bottom
- Drag down to dismiss
- Backdrop tap to close

---

## Screen-by-Screen Breakdown

---

## 1. Home Dashboard

### Purpose
Mission control for the bakery chef - see everything important at a glance.

### Layout Structure
```
┌─────────────────────────────────────┐
│ 🎂 Good morning, Chef               │ ← Greeting + Time
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ Today's Orders (5)              │ │ ← Section Header
│ │ ───────────────────────────     │ │
│ │ ┌─────────────────────────────┐ │ │
│ │ │ Order Card 1                │ │ │ ← Swipeable
│ │ └─────────────────────────────┘ │ │
│ │ ┌─────────────────────────────┐ │ │
│ │ │ Order Card 2                │ │ │
│ │ └─────────────────────────────┘ │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ Tomorrow's Orders (3)           │ │
│ │ ───────────────────────────     │ │
│ │ (Cards...)                      │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌───────────────┬─────────────────┐ │
│ │ Quick Stat 1  │ Quick Stat 2    │ │ ← Stats Grid
│ └───────────────┴─────────────────┘ │
│                                     │
│ [+]  New Order                      │ ← Floating Action
└─────────────────────────────────────┘
```

### Content Sections
1. **Greeting Header**
   - Dynamic: "Good morning/afternoon/evening, Chef"
   - Current date display
   - Small decorative floral

2. **Today's Orders**
   - Grouped by time (Morning pickup, Afternoon delivery, etc.)
   - Order cards (swipeable)
   - Empty state if none

3. **Tomorrow's Orders**
   - Preview of upcoming workload
   - Expandable/collapsible
   - "View all" link to Calendar

4. **Quick Stats**
   - Today's revenue
   - Pending dispatches
   - Most ordered item

5. **Floating Action Button**
   - "+ New Order" - prominent
   - Opens order creation flow

### Interactions
- Swipe left on order → Reveal "Complete" action
- Tap order card → View full order details
- Tap Quick Stat → View detailed analytics
- Pull to refresh → Update orders

### States
- **Loading:** Skeleton cards with shimmer
- **Empty:** "No orders today! Time to relax 🌸"
- **Error:** Gentle error message with retry

---

## 2. Order Card (Component)

### Card Anatomy
```
┌─────────────────────────────────────────┐
│ [Platform Icon] Customer Name      🌸   │ ← Header
│ #ORD-1234 · 2:00 PM Pickup             │ ← Meta
├─────────────────────────────────────────┤
│ • 6" Vanilla Cake - Pineapple          │ ← Items
│ • Brownie Box (12 pcs)                 │
├─────────────────────────────────────────┤
│ [Pending]  ₹2,700            ⋯ More    │ ← Footer
└─────────────────────────────────────────┘
```

### Information Display
- **Customer Name:** Heading 3
- **Order ID:** Caption with #prefix
- **Time:** Body Small with icon
- **Delivery/Pickup:** Badge
- **Items:** Bulleted list, Body Regular
- **Price:** Body Large, bold
- **Status:** Colored badge
- **Platform:** Icon (IG, WhatsApp, etc.)

### Color Coding
- **Border Left:** Colored stripe based on priority
  - Red: Urgent (< 2 hours)
  - Amber: Today
  - Green: Tomorrow
  - Blue: Future

### Swipe Actions
- Swipe Left: 
  - ✓ Mark Complete (Green)
  - ✏️ Edit (Blue)
- Swipe Right:
  - 📞 Call Customer (Teal)

---

## 3. Order Details Screen

### Structure
```
┌─────────────────────────────────────┐
│ ← Order Details              ⋯      │ ← Nav Header
├─────────────────────────────────────┤
│ Customer Information                │
│ ┌─────────────────────────────────┐ │
│ │ Name: Priya Sharma              │ │
│ │ Phone: +91 98765 43210          │ │
│ │ [Call] [Message]                │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Order Details                       │
│ ┌─────────────────────────────────┐ │
│ │ Order #ORD-1234                 │ │
│ │ Platform: Instagram             │ │
│ │ Date: May 10, 2026              │ │
│ │ Time: 2:00 PM                   │ │
│ │ Type: Pickup                    │ │
│ │ Occasion: Birthday              │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Items                               │
│ ┌─────────────────────────────────┐ │
│ │ 6" Vanilla - Pineapple    ₹850  │ │
│ │ Brownie Box (12 pcs)     ₹1850  │ │
│ │                                 │ │
│ │ Subtotal:                ₹2700  │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Special Notes                       │
│ "Write 'Happy Birthday Ananya'      │
│  with pink frosting"                │
│                                     │
│ [Mark as Complete]                  │ ← Primary Action
└─────────────────────────────────────┘
```

### Actions Available
- Edit Order
- Call/Message Customer
- Mark Complete
- View Location (if delivery)
- Delete Order (with confirmation)

---

## 4. Calendar Screen

### Views

#### Month View (Default)
```
┌─────────────────────────────────────┐
│    ← May 2026 →                     │
│                                     │
│ Su Mo Tu We Th Fr Sa                │
│              1  2  3                │
│  4  5  6  7  8  9 10                │
│ 11 ●● 13 14 ●  16 17                │ ← Dots = Orders
│ 18 19 20 21 22 23 24                │
│ 25 26 27 28 29 30 31                │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ Selected: May 12 (3 orders)     │ │
│ │ ───────────────────────────     │ │
│ │ Order Card 1                    │ │
│ │ Order Card 2                    │ │
│ │ Order Card 3                    │ │
│ └─────────────────────────────────┘ │
│                                     │
│ [+]  New Order                      │
└─────────────────────────────────────┘
```

#### Day View
```
┌─────────────────────────────────────┐
│ ← May 12, 2026                      │
│                                     │
│ Morning (9 AM - 12 PM)              │
│ ┌─────────────────────────────────┐ │
│ │ 10:00 AM Pickup                 │ │
│ │ Priya Sharma                    │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Afternoon (12 PM - 5 PM)            │
│ ┌─────────────────────────────────┐ │
│ │ 2:00 PM Delivery                │ │
│ │ Amit Verma                      │ │
│ └─────────────────────────────────┘ │
│ ┌─────────────────────────────────┐ │
│ │ 4:30 PM Pickup                  │ │
│ │ Neha Kapoor                     │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Evening (5 PM - 9 PM)               │
│ (Empty)                             │
│                                     │
│ [+]  Add Order for this day         │
└─────────────────────────────────────┘
```

### Visual Indicators
- **Order Density:** 
  - 1-2 orders: Single pink dot
  - 3-5 orders: Two pink dots
  - 6+ orders: Three pink dots (warning color)
  
- **Capacity Warning:**
  - Days with 8+ orders show amber/red background
  - Toast notification: "High capacity day! Consider spacing out orders"

### Interactions
- Tap date → Show orders for that day
- Swipe month → Change month
- Long-press date → Quick add order
- Pinch → Switch between month/week view

---

## 5. New Order Form

### Flow Structure
```
Step 1: Customer Info
  ↓
Step 2: Order Details
  ↓
Step 3: Select Products
  ↓
Step 4: Review & Confirm
```

### Step 1: Customer Information
```
┌─────────────────────────────────────┐
│ ← New Order                    1/4  │
├─────────────────────────────────────┤
│ Customer Information                │
│                                     │
│ Customer Name *                     │
│ [Text Input]                        │
│                                     │
│ Phone Number *                      │
│ [Text Input with format +91]        │
│                                     │
│ Existing Customer?                  │
│ [ ] Yes, autofill from history      │
│                                     │
│           [Next →]                  │
└─────────────────────────────────────┘
```

### Step 2: Order Details
```
┌─────────────────────────────────────┐
│ ← Order Details                2/4  │
├─────────────────────────────────────┤
│ Occasion                            │
│ [Dropdown: Birthday/Anniversary...] │
│                                     │
│ Delivery or Pickup? *               │
│ ( ) Delivery  (•) Pickup            │
│                                     │
│ [If Delivery selected:]             │
│ Delivery Address                    │
│ [Text Area]                         │
│                                     │
│ Order Date *                        │
│ [Date Picker]                       │
│                                     │
│ Time *                              │
│ [Time Picker]                       │
│                                     │
│ Platform Source *                   │
│ [Chip Selection: IG/WA/Phone...]    │
│                                     │
│           [Next →]                  │
└─────────────────────────────────────┘
```

### Step 3: Select Products
```
┌─────────────────────────────────────┐
│ ← Select Items                 3/4  │
├─────────────────────────────────────┤
│ Search products...                  │
│ [Search Bar]                        │
│                                     │
│ Vanilla Cakes                       │
│ ┌─────────────────────────────────┐ │
│ │ 6" Pineapple          ₹850      │ │
│ │ [- 1 +]                         │ │
│ └─────────────────────────────────┘ │
│ ┌─────────────────────────────────┐ │
│ │ 8" Pineapple         ₹1500      │ │
│ │ [- 0 +]                         │ │
│ └─────────────────────────────────┘ │
│                                     │
│ Chocolate Cakes                     │
│ (Products...)                       │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 2 items · ₹2700                 │ │ ← Running Total
│ └─────────────────────────────────┘ │
│                                     │
│ Special Instructions (Optional)     │
│ [Text Area]                         │
│                                     │
│           [Review →]                │
└─────────────────────────────────────┘
```

### Step 4: Review & Confirm
```
┌─────────────────────────────────────┐
│ ← Review Order                 4/4  │
├─────────────────────────────────────┤
│ Order Summary                       │
│                                     │
│ Customer                            │
│ Priya Sharma                        │
│ +91 98765 43210                     │
│                                     │
│ Details                             │
│ May 10, 2026 · 2:00 PM             │
│ Pickup · Birthday                   │
│ Via Instagram                       │
│                                     │
│ Items                               │
│ • 6" Vanilla - Pineapple     ₹850   │
│ • Brownie Box (12)          ₹1850   │
│                                     │
│ Special Notes                       │
│ "Pink frosting message"             │
│                                     │
│ ─────────────────────────────       │
│ Total:                      ₹2700   │
│                                     │
│    [Create Order]                   │
└─────────────────────────────────────┘
```

### Success State
- Gentle success animation (floating petals)
- Toast: "Order created! 🎂"
- Option: "Add to Calendar" or "View Order"
- Return to Home/Calendar

---

## 6. Menu Screen

### Structure
```
┌─────────────────────────────────────┐
│ Our Menu                     [Share]│
├─────────────────────────────────────┤
│ Search menu...                      │
│ [Search Bar]                        │
│                                     │
│ VANILLA CAKES          🌸           │
│ ┌───────────┬───────────┐           │
│ │ 6" Cake   │ 8" Cake   │           │
│ │ Pineapple │ Pineapple │           │
│ │ ₹850      │ ₹1500     │           │
│ └───────────┴───────────┘           │
│ ┌───────────┬───────────┐           │
│ │ Blueberry │ Caramel   │           │
│ │ (More...) │ Buttersc. │           │
│ └───────────┴───────────┘           │
│                                     │
│ CHOCOLATE CAKES        🍫           │
│ ┌───────────┬───────────┐           │
│ │ Classic   │ Cookies & │           │
│ │ Truffle   │ Cream     │           │
│ └───────────┴───────────┘           │
│                                     │
│ BROWNIES               💝           │
│ CHEESECAKES            🧈           │
│                                     │
└─────────────────────────────────────┘
```

### Product Card
```
┌─────────────────────┐
│ [Image Placeholder] │ ← 160px × 160px
│                     │
│ Pineapple Cake      │ ← Product Name
│ ₹850 / ₹1500        │ ← Pricing
│ 6" | 8"             │ ← Size Options
│                     │
│ [Quick Add]         │ ← Tap to add
└─────────────────────┘
```

### Product Detail
```
┌─────────────────────────────────────┐
│ ←                                   │
│                                     │
│ [Large Product Image]               │
│                                     │
│ Pineapple Vanilla Cake              │
│ Moist vanilla sponge with fresh     │
│ pineapple chunks and whipped cream  │
│                                     │
│ Sizes & Pricing                     │
│ ( ) 6 inch  ₹850   (600-650g)      │
│ (•) 8 inch  ₹1500  (1100-1200g)    │
│                                     │
│ Customizations                      │
│ [Text Input: Message on cake...]    │
│                                     │
│ [Add to New Order]                  │
└─────────────────────────────────────┘
```

### Share Menu Options
```
┌─────────────────────────────────────┐
│ Share Menu As                       │
│                                     │
│ 📄 PDF Document                     │
│    Formatted menu with prices       │
│                                     │
│ 📱 WhatsApp Image                   │
│    Single image, easy to share      │
│                                     │
│ 📸 Instagram Story                  │
│    Vertical format, branded         │
│                                     │
│ 🔗 Share Link                       │
│    Live web version                 │
│                                     │
│           [Cancel]                  │
└─────────────────────────────────────┘
```

---

## 7. Reports & Analytics Screen

### Monthly Overview (Default)
```
┌─────────────────────────────────────┐
│ ← May 2026 →                        │
├─────────────────────────────────────┤
│ ┌─────────────────────────────────┐ │
│ │ Total Revenue                   │ │
│ │ ₹45,600                         │ │
│ │ ↑ 12% from last month           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌───────────────┬─────────────────┐ │
│ │ Orders: 32    │ Repeat: 18      │ │
│ └───────────────┴─────────────────┘ │
│                                     │
│ Revenue Trend                       │
│ [Line Chart: Week by week]          │
│                                     │
│ Best Sellers                        │
│ 1. 6" Pineapple Cake (12 orders)   │
│ 2. Brownie Box (9 orders)           │
│ 3. Classic Truffle (7 orders)       │
│                                     │
│ Platform Breakdown                  │
│ [Donut Chart]                       │
│ • Instagram: 45%                    │
│ • WhatsApp: 30%                     │
│ • Repeat: 15%                       │
│ • Phone: 10%                        │
│                                     │
│ Busiest Day                         │
│ Saturday, May 15 (7 orders)         │
│                                     │
└─────────────────────────────────────┘
```

### Insights Section
```
┌─────────────────────────────────────┐
│ 💡 Insights                         │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 🎂 Cupcakes performed 35%       │ │
│ │    better this month            │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 📆 Weekends drive the highest   │ │
│ │    custom cake orders           │ │
│ └─────────────────────────────────┘ │
│                                     │
│ ┌─────────────────────────────────┐ │
│ │ 💖 Repeat customer rate up      │ │
│ │    from 12% to 18%              │ │
│ └─────────────────────────────────┘ │
└─────────────────────────────────────┘
```

### Date Range Filter
- Tap month header → Open date picker
- Quick filters: This week | This month | Last 30 days | Custom

---

## 8. Order Completion Flow

### Trigger
User swipes left on order card → Taps "Complete"

### Step 1: Confirmation
```
┌─────────────────────────────────────┐
│ Mark Order as Complete?             │
│                                     │
│ Priya Sharma                        │
│ #ORD-1234 · ₹2700                   │
│                                     │
│ [Cancel]     [Yes, Complete]        │
└─────────────────────────────────────┘
```

### Step 2: Satisfaction Rating (Optional)
```
┌─────────────────────────────────────┐
│ How did it turn out?                │
│                                     │
│ [Priya Sharma's order]              │
│                                     │
│ Rating                              │
│ ☆ ☆ ☆ ☆ ☆                          │
│                                     │
│ Notes (optional)                    │
│ [Text Area]                         │
│ "Nailed the pineapple flavor!"      │
│                                     │
│ [Skip]              [Save]          │
└─────────────────────────────────────┘
```

### Step 3: Success
- Gentle animation (checkmark + petals)
- Card fades out elegantly from list
- Toast: "Order marked complete! 🌸"

---

## Empty States

### No Orders Today
```
┌─────────────────────────────────────┐
│                                     │
│        [Floral illustration]        │
│                                     │
│    No orders today!                 │
│    Time to relax 🌸                 │
│                                     │
│    [Create New Order]               │
│                                     │
└─────────────────────────────────────┘
```

### No Analytics Yet
```
┌─────────────────────────────────────┐
│                                     │
│    [Botanical illustration]         │
│                                     │
│    Start taking orders to see       │
│    your business insights           │
│                                     │
│    [Add Your First Order]           │
│                                     │
└─────────────────────────────────────┘
```

### Menu Not Set Up
```
┌─────────────────────────────────────┐
│                                     │
│    [Cake illustration]              │
│                                     │
│    Your menu will appear here       │
│    once products are added          │
│                                     │
│    [Coming Soon]                    │
│                                     │
└─────────────────────────────────────┘
```

---

## Loading States

### Skeleton Screens
- Home: Show skeleton cards with shimmer
- Calendar: Show month grid immediately, load order dots
- Menu: Show product grid structure, load images
- Reports: Show chart placeholders, load data

### Pull to Refresh
- Elastic pull gesture
- Gentle flower spinner
- Smooth snap back

---

## Error States

### Network Error
```
┌─────────────────────────────────────┐
│                                     │
│    [Wilted flower illustration]     │
│                                     │
│    Couldn't load orders             │
│    Check your connection            │
│                                     │
│    [Try Again]                      │
│                                     │
└─────────────────────────────────────┘
```

### Action Failed
- Toast notification: "Oops! Couldn't save order"
- Option to retry
- Keep user's input (don't lose form data)

---

## Notification Strategy (Future)

### Push Notifications
- Order reminders (2 hours before)
- Daily summary (morning: "You have 5 orders today")
- Capacity warnings (when calendar fills up)
- Monthly reports ready

### In-App Notifications
- Small badge on Reports tab (new insights)
- Subtle dot on orders needing attention

---

## Data Persistence

### Local Storage
- Recent orders (last 30 days)
- Customer history
- Product catalog
- Settings

### Cloud Sync (Future)
- All orders
- Analytics data
- Menu updates
- Backup

---

## Accessibility Considerations

### Navigation
- Clear focus indicators
- Swipe gestures have button alternatives
- Voice commands (future)

### Visual
- High contrast mode option
- Text scaling support
- Clear iconography with labels

### Touch
- Large tap targets (48px minimum)
- Generous spacing between interactive elements
- Easy one-handed use

---

This information architecture creates a calm, organized, and efficient flow for the bakery chef to manage their business while maintaining the elegant, handcrafted brand aesthetic.
