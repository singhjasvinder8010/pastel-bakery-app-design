# Pastel Bakery Co - User Flows

## Core User Flows

---

## Flow 1: Quick Order Check (Primary Use Case)

**Scenario:** Chef wants to quickly see what's coming up today

```
START
  ↓
Open App
  ↓
Land on Home Dashboard
  ↓
Scan Today's Orders section
  ↓
See all upcoming pickups/deliveries at a glance
  ↓
END (Task complete in < 5 seconds)
```

**Success Criteria:**
- Orders visible immediately (no loading delay)
- Time-sorted chronologically
- Status immediately clear
- No navigation needed

---

## Flow 2: Mark Order as Complete

**Scenario:** Chef finished baking an order and wants to mark it done

```
START (Home Dashboard)
  ↓
Locate order card in Today's Orders
  ↓
Swipe LEFT on order card
  ↓
"Complete" button reveals (green)
  ↓
Tap "Complete"
  ↓
Modal: "Mark Order as Complete?"
  ├→ Tap "Cancel" → Return to list
  └→ Tap "Yes, Complete"
      ↓
      Optional: "How did it turn out?"
      ├→ Tap "Skip" → Order marked complete
      └→ Rate 1-5 stars + add notes
          ↓
          Tap "Save"
          ↓
          Animation: Checkmark + floating petals
          ↓
          Card fades out elegantly
          ↓
          Toast: "Order complete! 🌸"
          ↓
          Return to Home Dashboard (order removed from list)
          ↓
END
```

**Success Criteria:**
- Swipe action is smooth and discoverable
- Confirmation prevents accidental completion
- Optional satisfaction tracking doesn't block flow
- Immediate visual feedback
- Total time: < 10 seconds

**Alternative Flow:**
```
Tap order card (instead of swipe)
  ↓
Order Details screen
  ↓
Scroll to bottom
  ↓
Tap "Mark as Complete" button
  ↓
(Same confirmation flow as above)
```

---

## Flow 3: Creating a New Order (Full Flow)

**Scenario:** Customer calls to place an order, chef needs to log it

```
START (Any screen)
  ↓
Tap floating "+ New Order" button
  OR
Tap "Add Order" in Calendar day view
  ↓
────────────────────────────────────
STEP 1: Customer Information (1/4)
────────────────────────────────────
  ↓
Form appears (bottom sheet or full screen)
  ↓
Tap "Customer Name" field
  ↓
Keyboard appears → Type name: "Priya Sharma"
  ↓
Tap "Phone Number" field
  ↓
Type: "+91 98765 43210"
  ↓
System checks: Is this a returning customer?
  ├→ Yes: Show badge "Repeat Customer 💝"
  └→ No: Continue
  ↓
Tap "Next" button
  ↓
────────────────────────────────────
STEP 2: Order Details (2/4)
────────────────────────────────────
  ↓
Tap "Occasion" dropdown
  ↓
Select: "Birthday" from list
  ↓
Select "Delivery or Pickup"
  ↓
Tap "Pickup" radio button
  ↓
[If "Delivery" selected:]
│ ↓
│ "Delivery Address" field appears
│ ↓
│ Tap and type address
│ ↓
│ Optional: Location picker
  ↓
Tap "Order Date" picker
  ↓
Calendar appears → Select: "May 10, 2026"
  ↓
Tap "Time" picker
  ↓
Time selector appears → Choose: "2:00 PM"
  ↓
Tap "Platform Source"
  ↓
Chip selection appears:
[Instagram] [WhatsApp] [Phone] [Walk-in] [Repeat] [Other]
  ↓
Tap: "Instagram" (chip highlights in pink)
  ↓
Tap "Next" button
  ↓
────────────────────────────────────
STEP 3: Select Items (3/4)
────────────────────────────────────
  ↓
Product catalog loads
  ↓
Categories displayed: Vanilla Cakes, Chocolate Cakes, etc.
  ↓
Scroll to "Vanilla Cakes"
  ↓
Find: "6" Pineapple - ₹850"
  ↓
Tap "+" button
  ↓
Quantity changes: 0 → 1
  ↓
Running total updates: "₹850"
  ↓
Scroll down to "Brownies"
  ↓
Find: "Hazelnut/Roasted Almond Box - ₹875"
  ↓
Tap "+" button (quantity: 1)
  ↓
Running total updates: "₹1,725"
  ↓
[Optional] Tap "Special Instructions" field
  ↓
Type: "Write 'Happy Birthday Ananya' with pink frosting"
  ↓
Tap "Review →" button
  ↓
────────────────────────────────────
STEP 4: Review & Confirm (4/4)
────────────────────────────────────
  ↓
Order summary displays:
├ Customer: Priya Sharma (+91 98765 43210)
├ Details: May 10, 2026 · 2:00 PM · Pickup · Birthday · Via Instagram
├ Items:
│  • 6" Vanilla - Pineapple (₹850)
│  • Brownie Box (₹875)
├ Special Notes: "Write 'Happy Birthday Ananya' with pink frosting"
└ Total: ₹1,725
  ↓
Chef reviews all details
  ↓
Tap "Create Order" button (primary, pink)
  ↓
Loading spinner appears (gentle flower animation)
  ↓
Order saves to database
  ↓
Success animation: Floating petals + checkmark
  ↓
Toast: "Order created! 🎂"
  ↓
Options:
├→ "View Order" → Navigate to Order Details
└→ "Add Another" → Reset form to Step 1
  ↓
Default: Return to Home Dashboard
  ↓
New order appears in "Today's Orders" (or relevant date section)
  ↓
END
```

**Success Criteria:**
- Form feels conversational, not overwhelming
- Progress indicator (1/4, 2/4, etc.) always visible
- Can go back to previous steps without losing data
- Smart defaults minimize typing
- Product selection is visual and quick
- Running total always visible
- Final review prevents errors
- Total time: 2-3 minutes

**Error Handling:**
```
If required field is empty:
  ↓
"Next" button disabled (grayed out)
  ↓
Tap disabled button → Field with error shakes gently
  ↓
Helper text appears: "Please enter customer name"
  ↓
Field highlights in soft coral
```

---

## Flow 4: Quick Add Order from Menu

**Scenario:** Chef is showing menu to customer, wants to quickly create order from products

```
START (Menu screen)
  ↓
Browse product categories
  ↓
Find product: "6" Pineapple Cake"
  ↓
Tap product card
  ↓
Product detail sheet appears
  ↓
Select size: "6 inch - ₹850" (radio button)
  ↓
[Optional] Add customization note
  ↓
Tap "Add to New Order" button
  ↓
System prompts: "Create order for this item?"
  ├→ Tap "Quick Add" → Opens simplified order form (pre-filled with product)
  │   ↓
  │   Enter: Customer name, phone, date/time
  │   ↓
  │   Tap "Create Order"
  │   ↓
  │   Success → Order created
  │   ↓
  └→ Tap "Continue Shopping" → Return to menu, start cart
      ↓
      Add more products
      ↓
      Tap floating cart icon (shows item count)
      ↓
      Review cart
      ↓
      Tap "Create Order"
      ↓
      (Same order creation flow)
END
```

**Success Criteria:**
- Menu-to-order flow is seamless
- Cart system works like e-commerce (familiar pattern)
- Can add multiple products before creating order
- Quick add is truly quick (< 1 minute)

---

## Flow 5: View Daily Schedule in Calendar

**Scenario:** Chef wants to plan tomorrow's baking schedule

```
START (Any screen)
  ↓
Tap "Calendar" tab in bottom navigation
  ↓
Month view displays (current month)
  ↓
Scan month: Days with orders show pink dots
  ├ Single dot: 1-2 orders
  ├ Double dot: 3-5 orders
  └ Triple dot: 6+ orders (amber/warning color)
  ↓
Tap "Tomorrow's date" (e.g., May 9)
  ↓
Bottom section updates:
├ Header: "May 9 (4 orders)"
└ Order cards listed chronologically
  ↓
Review orders:
├ 9:00 AM Pickup - Neha Kapoor
├ 11:30 AM Delivery - Amit Verma
├ 3:00 PM Pickup - Ravi Singh
└ 5:00 PM Pickup - Priya Sharma
  ↓
Mental planning: "I'll bake Neha's cake tonight, rest in morning"
  ↓
[Optional] Tap "Day View" button
  ↓
Switch to timeline view (grouped by time blocks)
  ↓
END
```

**Success Criteria:**
- Calendar loads instantly
- Order density immediately visible
- Easy to scan multiple days quickly
- Tap interaction is natural
- Can quickly assess workload for week ahead

**Alternative Flow: Identify Overloaded Day**
```
Scanning month view
  ↓
Notice: May 15 has triple dots (red/amber)
  ↓
Tap May 15
  ↓
See: "8 orders" (high capacity)
  ↓
Warning banner: "⚠️ High capacity day! Consider spacing out orders"
  ↓
Options:
├→ "View Orders" → See full list
└→ "Dismiss" → Acknowledge
  ↓
Chef decides to call customers and adjust some pickup times
  ↓
END
```

---

## Flow 6: Share Menu with Customer

**Scenario:** Customer requests menu via WhatsApp

```
START (Menu screen)
  ↓
Customer messages: "Can you send the menu?"
  ↓
Chef opens app → Navigates to Menu tab
  ↓
Tap "Share" button (top-right)
  ↓
Bottom sheet appears: "Share Menu As"
├ 📄 PDF Document
├ 📱 WhatsApp Image
├ 📸 Instagram Story
└ 🔗 Share Link
  ↓
Tap "WhatsApp Image"
  ↓
App generates: Single optimized image with menu items
  ↓
System share sheet appears
  ↓
Select: WhatsApp
  ↓
Choose contact: Customer
  ↓
Image attaches to chat
  ↓
Send message
  ↓
Return to app → Toast: "Menu shared! 💝"
  ↓
END
```

**Success Criteria:**
- Share options are clear and purposeful
- Generated images are high quality
- WhatsApp image is mobile-friendly (readable on small screens)
- Instagram story is correctly formatted (9:16 aspect ratio)
- PDF is professional and printable
- Total time: < 30 seconds

**Alternative Flow: Share as Instagram Story**
```
Tap "Instagram Story" option
  ↓
App generates vertical story format:
├ Brand colors and florals
├ Product highlights
└ Contact info overlay
  ↓
System share sheet → Select Instagram
  ↓
Instagram opens in story creation mode
  ↓
Chef can add stickers/text
  ↓
Post story
  ↓
END
```

---

## Flow 7: View Monthly Report

**Scenario:** End of month - chef wants to see business performance

```
START (Any screen)
  ↓
Tap "Reports" tab in bottom navigation
  ↓
Monthly overview displays (current month: May 2026)
  ↓
Scan key metrics:
├ Total Revenue: ₹45,600 (↑ 12% from last month)
├ Total Orders: 32
├ Repeat Customers: 18 (56%)
└ Best Seller: 6" Pineapple Cake (12 orders)
  ↓
Scroll down → View revenue trend line chart
  ↓
Notice: Week 3 had a spike (₹15,000)
  ↓
Scroll down → View platform breakdown donut chart
├ Instagram: 45%
├ WhatsApp: 30%
├ Repeat: 15%
└ Phone: 10%
  ↓
Insight: "Instagram is driving nearly half of orders!"
  ↓
Continue scrolling → View "Insights" section
  ↓
Read insights:
├ "🎂 Cupcakes performed 35% better this month"
├ "📆 Weekends drive the highest custom cake orders"
└ "💖 Repeat customer rate up from 12% to 18%"
  ↓
Tap month selector (top)
  ↓
Dropdown: [This week | This month | Last 30 days | Custom]
  ↓
Select: "Last 30 days"
  ↓
Report updates with new data range
  ↓
[Optional] Tap "Share Report" button
  ↓
Export as PDF or screenshot
  ↓
END
```

**Success Criteria:**
- All key metrics visible without scrolling
- Charts are elegant and easy to read
- Insights are actionable and personalized
- Can compare different time periods
- Total time to get insights: < 1 minute

---

## Flow 8: Call Customer from Order

**Scenario:** Chef needs to clarify order details with customer

```
START (Home Dashboard)
  ↓
Locate order: "Priya Sharma"
  ↓
Option 1: Swipe RIGHT on order card
  ↓
  "Call" action button reveals
  ↓
  Tap "Call" button (with phone icon)
  ↓
  System dialer opens with number: +91 98765 43210
  ↓
  Tap "Call" → Phone call starts
  ↓
  END

Option 2: Tap order card
  ↓
  Order Details screen opens
  ↓
  See customer info section:
  ├ Name: Priya Sharma
  └ Phone: +91 98765 43210
  ↓
  Tap phone number (formatted as link/button)
  ↓
  System dialer opens
  ↓
  Call customer
  ↓
  After call: Return to app (app remembers your place)
  ↓
  END
```

**Success Criteria:**
- Phone number is tappable/clickable
- System handles the call (not in-app)
- Easy return to app after call
- Swipe gesture for quick access
- Total time to initiate call: < 5 seconds

---

## Flow 9: Edit Existing Order

**Scenario:** Customer calls to change pickup time

```
START (Home Dashboard or Calendar)
  ↓
Locate order: "Amit Verma - 2:00 PM Pickup"
  ↓
Tap order card
  ↓
Order Details screen opens
  ↓
Tap "Edit" button (top-right, icon or text)
  ↓
Order Edit form appears (pre-filled with current data)
  ↓
Navigate to "Time" field
  ↓
Tap "Time" → Time picker opens
  ↓
Change: 2:00 PM → 4:00 PM
  ↓
Tap "Done"
  ↓
Review changes (form shows updated time)
  ↓
Scroll to bottom
  ↓
Tap "Save Changes" button (primary)
  ↓
Loading spinner (brief)
  ↓
Success animation + toast: "Order updated! ✨"
  ↓
Return to Order Details screen (with updated time)
  ↓
END
```

**Success Criteria:**
- Edit is easily discoverable
- Form is pre-filled (not blank)
- Only changed fields are validated
- Clear confirmation of what changed
- Total time: < 1 minute

---

## Flow 10: Delete Order

**Scenario:** Customer cancels their order

```
START (Order Details screen)
  ↓
Tap "⋯" menu (top-right)
  ↓
Dropdown menu appears:
├ Edit Order
├ Call Customer
├ Share Order
└ Delete Order (red text)
  ↓
Tap "Delete Order"
  ↓
Confirmation modal appears:
"Delete this order?"
"This action cannot be undone."
[Cancel] [Delete]
  ↓
Tap "Delete" button (red)
  ↓
Loading spinner
  ↓
Order deleted from database
  ↓
Return to Home Dashboard
  ↓
Order removed from list (gentle fade-out animation)
  ↓
Toast: "Order deleted"
  ↓
END
```

**Success Criteria:**
- Delete action is not immediately accessible (prevents accidents)
- Requires two confirmations (menu tap + modal confirm)
- Warning is clear
- Destructive action uses red color
- No option to undo (clear communication)

---

## Flow 11: First Time App Launch

**Scenario:** Chef opens app for the first time

```
START (App Launch)
  ↓
Splash screen appears:
├ Pastel Bakery Co logo
├ Soft pink background
└ Floral decorations
  ↓
(2 seconds)
  ↓
Onboarding carousel appears:

────────────────────────
Slide 1/3
────────────────────────
[Illustration: Dashboard with order cards]

"Manage Your Orders"
Track every order from creation to delivery

[Next →]

────────────────────────
Slide 2/3
────────────────────────
[Illustration: Calendar with events]

"Plan Your Production"
Visualize your schedule and never miss a delivery

[Next →]

────────────────────────
Slide 3/3
────────────────────────
[Illustration: Analytics charts]

"Grow Your Business"
Understand what sells and when

[Get Started]

  ↓
Tap "Get Started"
  ↓
Optional: Quick setup
├ "What should we call you?" → Enter chef name
├ "Your bakery name?" → Enter business name
└ "Enable notifications?" → Yes/No
  ↓
Tap "Continue"
  ↓
Land on Home Dashboard (empty state)
  ↓
Empty state displays:
[Floral illustration]
"Welcome to Pastel Bakery Co!"
"Add your first order to get started"
[+ Create First Order]
  ↓
[Optional] Tap "Create First Order" → Guided flow
  ↓
END
```

**Success Criteria:**
- Onboarding is beautiful and on-brand
- Can skip if desired
- Minimal setup (not overwhelming)
- Empty state is encouraging, not intimidating
- Clear next action

---

## Flow 12: Search for Past Order

**Scenario:** Customer calls asking about previous order from 2 weeks ago

```
START (Home Dashboard)
  ↓
Tap search icon (top-right) or pull down to reveal search
  ↓
Search bar appears with cursor
  ↓
Type: "Priya" or "ORD-1234" or "Pineapple Cake"
  ↓
Real-time results filter:
├ Orders matching "Priya"
├ Orders with item "Pineapple Cake"
└ Order IDs matching search
  ↓
Results show:
├ Recent first (this week)
├ Then older matches
└ "Load more" if many results
  ↓
Tap result: "Priya Sharma - May 1"
  ↓
Order Details screen opens
  ↓
Review past order details
  ↓
[Optional] Tap "Reorder" button
  ↓
Creates new order with same items (prompts for new date/time)
  ↓
END
```

**Success Criteria:**
- Search is fast (real-time filtering)
- Searches across: customer name, order ID, product names, dates
- Results are chronologically sorted
- Past orders are clearly marked (e.g., "Completed • May 1")
- Reorder feature saves time

---

## Flow 13: Swipe Gestures Discovery

**Scenario:** New user discovers swipe actions

```
START (Home Dashboard with orders)
  ↓
User naturally tries to swipe on order card
  ↓
(First time swipe)
  ↓
Swipe left → Actions reveal with gentle animation
├ ✓ Complete (green)
└ ✏️ Edit (blue)
  ↓
Tooltip appears (first time only):
"💡 Swipe left to complete or edit orders"
  ↓
User taps outside or waits 3 seconds → Tooltip dismisses
  ↓
Card returns to normal state
  ↓
(User learns swipe left = quick actions)
  ↓
Later: User tries swipe right
  ↓
Swipe right → Different action reveals
└ 📞 Call Customer (teal)
  ↓
Tooltip: "Swipe right to quickly call customer"
  ↓
END
```

**Success Criteria:**
- Swipe gestures feel natural (not forced)
- First-time tooltips are subtle and helpful
- Actions are color-coded for clarity
- Card smoothly returns if no action is taken
- Works with one hand

---

## Flow 14: Handle Low/No Internet

**Scenario:** App is opened with poor network connection

```
START (App Launch - No Network)
  ↓
App loads from local cache
  ↓
Home Dashboard displays with cached data
  ↓
Banner appears (top, soft amber background):
"⚠️ Limited connection. Showing cached orders."
  ↓
User can view orders, menu, past reports (read-only)
  ↓
User tries to create new order
  ↓
Error modal:
"No Internet Connection"
"Connect to save new orders"
[OK]
  ↓
Tap OK → Return to form (data is saved locally)
  ↓
Banner changes:
"📝 Order saved locally. Will sync when online."
  ↓
Connection returns
  ↓
Auto-sync happens in background
  ↓
Toast: "✓ All changes synced"
  ↓
Banner dismisses
  ↓
END
```

**Success Criteria:**
- App doesn't crash without internet
- Cached data allows read-only access
- Changes are queued and synced later
- Clear communication about connection status
- No data loss

---

## Flow 15: Dark Mode (Future)

**Scenario:** User enables dark mode in evening

```
START (Any screen - Light mode)
  ↓
Swipe down → System settings
  ↓
Enable "Dark Mode"
  ↓
Return to app
  ↓
App detects system dark mode
  ↓
Smooth transition (500ms fade):
├ Background: #FFF8F3 → #2C1E1A (deep brown)
├ Cards: #FFFFFF → #3D2E28 (warm dark)
├ Text: #5C3A2E → #F4E4D7 (cream)
└ Accent: #FFB5B5 → #FFCACA (softer pink)
  ↓
Floral illustrations adjust (darker tones, glowing edges)
  ↓
All screens adapt to dark mode
  ↓
END
```

**Success Criteria:**
- Follows system dark mode setting
- Color palette maintains brand warmth
- Not pure black (retains warmth with dark browns)
- Florals are subtle, not overwhelming
- All text remains readable (WCAG AA contrast)

---

## Key Flow Metrics Summary

| Flow | Primary Users | Frequency | Time to Complete | Priority |
|------|---------------|-----------|------------------|----------|
| Quick Order Check | Chef | Daily | < 5 sec | Critical |
| Mark Complete | Chef | 3-5x/day | < 10 sec | Critical |
| Create New Order | Chef | 2-4x/day | 2-3 min | Critical |
| View Daily Schedule | Chef | Daily | 15-30 sec | High |
| Share Menu | Chef | Weekly | < 30 sec | High |
| Monthly Report | Chef | Monthly | < 1 min | Medium |
| Call Customer | Chef | As needed | < 5 sec | High |
| Edit Order | Chef | Occasionally | < 1 min | Medium |

---

## Flow Optimization Principles

1. **Speed First**
   - Most common actions take < 10 seconds
   - No unnecessary steps
   - Smart defaults reduce typing

2. **One-Handed Use**
   - All primary actions reachable with thumb
   - Bottom navigation for tabs
   - Floating action button in easy reach

3. **Forgiving**
   - Can go back without losing data
   - Destructive actions require confirmation
   - Auto-save where possible

4. **Clear Feedback**
   - Every action has visual response
   - Loading states are gentle
   - Success/error messages are clear

5. **Contextual**
   - Show relevant information at the right time
   - Hide complexity until needed
   - Progressive disclosure

---

These user flows create a smooth, efficient, and delightful experience that respects the chef's time while maintaining the app's elegant, handcrafted aesthetic.
