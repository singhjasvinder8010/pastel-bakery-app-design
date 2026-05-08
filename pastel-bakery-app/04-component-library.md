# Pastel Bakery Co - Component Library

## Complete UI Component Specifications

---

## 1. Buttons

### 1.1 Primary Button

**Visual Specification:**
```
┌─────────────────────────┐
│   Button Text Label     │
└─────────────────────────┘

Background: Linear Gradient
  - Start: #FFB5B5
  - End: #FF9E9E
  - Direction: Left to right
Border: None
Border Radius: 12px
Padding: 14px 24px
Min Height: 48px
Text: Inter Medium, 15px, #5C3A2E
Shadow: 0 2px 8px rgba(92, 58, 46, 0.06)
```

**States:**
- **Default:** As above
- **Hover:** 
  - Shadow: 0 4px 16px rgba(92, 58, 46, 0.08)
  - Transform: scale(1.02)
  - Transition: 200ms ease
- **Active/Pressed:**
  - Transform: scale(0.98)
  - Shadow: 0 1px 4px rgba(92, 58, 46, 0.08)
- **Disabled:**
  - Background: #E8D4C9
  - Text: #A68976
  - Cursor: not-allowed
  - Opacity: 0.6

**Usage:**
- Primary actions (Create Order, Save, Confirm)
- One per screen maximum
- Always above other buttons in hierarchy

**Code Example:**
```jsx
<Button variant="primary">
  Create Order
</Button>
```

---

### 1.2 Secondary Button

**Visual Specification:**
```
┌─────────────────────────┐
│   Button Text Label     │
└─────────────────────────┘

Background: #FFF8F3
Border: 1.5px solid #E8B4B8
Border Radius: 12px
Padding: 14px 24px
Min Height: 48px
Text: Inter Medium, 15px, #5C3A2E
Shadow: None
```

**States:**
- **Hover:**
  - Background: #FFE8E8
  - Border: #D4949A
- **Active:**
  - Background: #FFC9C9
  - Transform: scale(0.98)
- **Disabled:**
  - Border: #E8D4C9
  - Text: #A68976
  - Opacity: 0.6

**Usage:**
- Secondary actions (Cancel, Go Back)
- Alternative choices
- Less important actions

---

### 1.3 Ghost Button

**Visual Specification:**
```
┌─────────────────────────┐
│   Button Text Label     │
└─────────────────────────┘

Background: Transparent
Border: None
Padding: 12px 20px
Min Height: 44px
Text: Inter Medium, 15px, #D4949A
```

**States:**
- **Hover:**
  - Background: #FFE8E8
  - Border Radius: 8px
- **Active:**
  - Background: #FFC9C9

**Usage:**
- Tertiary actions (Skip, Not Now)
- Navigation links
- Inline actions

---

### 1.4 Icon Button

**Visual Specification:**
```
┌──────┐
│  🔍  │
└──────┘

Size: 44px × 44px
Background: #FFFBF7
Border Radius: 999px (circular)
Icon Size: 20px × 20px
Icon Color: #5C3A2E
Shadow: 0 2px 8px rgba(92, 58, 46, 0.06)
```

**States:**
- **Hover:**
  - Background: #FFE8E8
  - Shadow: 0 4px 12px rgba(92, 58, 46, 0.08)
- **Active:**
  - Background: #FFC9C9
  - Transform: scale(0.95)

**Variants:**
- **Small:** 36px × 36px, icon 18px
- **Large:** 52px × 52px, icon 24px

**Usage:**
- Standalone actions
- Navigation controls
- Quick access functions

---

### 1.5 Floating Action Button (FAB)

**Visual Specification:**
```
┌─────────────────┐
│  +  New Order   │
└─────────────────┘

Size: Auto width × 56px
Background: Linear gradient #FFB5B5 → #FF9E9E
Border Radius: 28px (pill shape)
Padding: 16px 24px
Icon: 24px, #5C3A2E (left side)
Text: Inter Semibold, 16px, #5C3A2E
Shadow: 0 8px 24px rgba(255, 181, 181, 0.4)
Position: Fixed bottom-right, 20px from edges
```

**States:**
- **Hover:**
  - Shadow: 0 12px 32px rgba(255, 181, 181, 0.5)
  - Transform: translateY(-2px)
- **Active:**
  - Transform: scale(0.96)

**Usage:**
- Primary action on Home/Calendar screens
- Always accessible
- Initiates new order flow

---

## 2. Cards

### 2.1 Order Card (Main Component)

**Visual Specification:**
```
┌────────────────────────────────────────────┐
│ 📱 Priya Sharma                      🌸    │ 2px colored
│ #ORD-1234 · 2:00 PM Pickup                 │ stripe
│                                            │
│ • 6" Vanilla Cake - Pineapple              │
│ • Brownie Box (12 pcs)                     │
│                                            │
│ [Pending]      ₹2,700            ⋯         │
└────────────────────────────────────────────┘

Background: #FFFBF7
Border: 1px solid rgba(232, 180, 184, 0.3)
Border Left: 3px solid (status color)
Border Radius: 16px
Padding: 20px
Gap: 12px (between sections)
Shadow: 0 2px 8px rgba(92, 58, 46, 0.06)
Decorative: Small floral in top-right (32px, 20% opacity)
```

**Border Colors (Status):**
- Urgent (< 2 hours): #E8A5A5
- Today: #F4C896
- Tomorrow: #B8C9B4
- Future: #B8C9E8

**Header Section:**
- Platform icon: 20px, color based on platform
- Customer name: Playfair Display Semibold, 18px, #5C3A2E
- Floral decoration: 32px × 32px, top-right absolute position

**Meta Row:**
- Order ID: Inter Regular, 12px, #A68976
- Separator: "·" character
- Time & Type: Inter Regular, 12px, #8B6E5F

**Items List:**
- Bullet style: "•" character
- Text: Inter Regular, 14px, #5C3A2E
- Line height: 22px
- Max visible: 3 items, then "...and 2 more"

**Footer:**
- Status badge: 8px radius, colored background
- Price: Inter Bold, 16px, #5C3A2E
- More menu: Icon button, 32px × 32px

**Interactive States:**
- **Default:** As above
- **Hover (desktop):** Shadow Level 2, lift 2px
- **Swipe Left:** Reveal action buttons (width expands 80px)
- **Swipe Right:** Reveal call button (width expands 60px)
- **Active/Tap:** Scale 0.98, immediate response

**Swipe Actions:**

Left Swipe:
```
┌───────────────────────────┬───────┬────────┐
│ Order Card Content        │ ✓ COM │ ✏️ EDIT │
└───────────────────────────┴───────┴────────┘
  
Complete Button:
- Background: #9BB096
- Icon: Checkmark, white, 20px
- Width: 80px
  
Edit Button:
- Background: #B8C9E8
- Icon: Pencil, white, 18px
- Width: 80px
```

Right Swipe:
```
┌───────┬───────────────────────────┐
│ 📞CALL │ Order Card Content        │
└───────┴───────────────────────────┘

Call Button:
- Background: #82C9C3
- Icon: Phone, white, 20px
- Width: 80px
```

**Variants:**
- **Compact:** Reduced padding (16px), smaller text
- **Expanded:** Shows full item list, special notes
- **Completed:** 50% opacity, strikethrough text, checkmark overlay

---

### 2.2 Product Card (Menu)

**Visual Specification:**
```
┌─────────────────────┐
│                     │
│   [Image/Photo]     │
│                     │
│                     │
├─────────────────────┤
│ Pineapple Cake      │
│ ₹850 / ₹1500        │
│ 6" | 8"             │
│                     │
│ [Quick Add]         │
└─────────────────────┘

Container:
- Width: 48% (2 column grid)
- Background: #FFFFFF
- Border: 1px solid #F4E4D7
- Border Radius: 12px
- Shadow: 0 2px 8px rgba(92, 58, 46, 0.04)

Image Area:
- Height: 160px
- Background: #FFF5ED (if no image)
- Border Radius: 12px 12px 0 0
- Object-fit: cover

Content Area:
- Padding: 16px

Title:
- Playfair Display Semibold, 16px
- Color: #5C3A2E
- Line clamp: 2 lines

Pricing:
- Inter Medium, 14px
- Color: #8B6E5F

Size Options:
- Inter Regular, 12px
- Color: #A68976
- Separated by "|"

Quick Add Button:
- Full width
- Secondary style
- Height: 36px
```

**States:**
- **Hover:** Shadow Level 2, lift
- **Tap:** Navigate to product detail

---

### 2.3 Stat Card (Dashboard)

**Visual Specification:**
```
┌─────────────────────┐
│ ₹15,600            │
│ Today's Revenue     │
│ ↑ 12% from yesterday│
└─────────────────────┘

Background: Linear gradient
  - Start: #FFF8F3
  - End: #FFF5ED
Border: 1px solid rgba(232, 180, 184, 0.2)
Border Radius: 12px
Padding: 20px
Gap: 4px

Value:
- Playfair Display Semibold, 28px
- Color: #5C3A2E

Label:
- Inter Regular, 13px
- Color: #8B6E5F

Change Indicator:
- Inter Medium, 12px
- Color: #7A9475 (positive) or #E8A5A5 (negative)
- Icon: Arrow up/down, 14px
```

**Variants:**
- **Neutral:** No change indicator
- **Positive:** Green text + up arrow
- **Negative:** Coral text + down arrow

---

### 2.4 Calendar Day Cell

**Visual Specification:**
```
┌──────┐
│  15  │
│  ●●  │
└──────┘

Size: 48px × 48px (mobile), 56px × 56px (tablet)
Border Radius: 8px

Day Number:
- Inter Semibold, 16px
- Color: #5C3A2E (default)
- Color: #D4949A (selected)

Order Indicators:
- Position: Below number
- Dot size: 4px × 4px
- Spacing: 2px
- Colors:
  - 1-2 orders: Single pink dot (#FFB5B5)
  - 3-5 orders: Two pink dots
  - 6+ orders: Three amber dots (#F4C896)
```

**States:**
- **Default:** Background transparent
- **Today:** Border 2px solid #FFB5B5
- **Selected:** Background #FFE8E8
- **Other Month:** Opacity 0.4
- **Past:** Opacity 0.6

---

## 3. Form Inputs

### 3.1 Text Input

**Visual Specification:**
```
Label
┌──────────────────────────────────┐
│ Placeholder text                 │
└──────────────────────────────────┘
Helper text

Container:
- Width: 100%
- Min Height: 48px

Label:
- Inter Medium, 13px
- Color: #5C3A2E
- Margin bottom: 8px

Input Field:
- Background: #FFFFFF
- Border: 1.5px solid #E8D4C9
- Border Radius: 12px
- Padding: 14px 16px
- Font: Inter Regular, 15px
- Color: #5C3A2E
- Placeholder: #A68976

Helper Text:
- Inter Regular, 12px
- Color: #8B6E5F
- Margin top: 6px
```

**States:**
- **Focus:**
  - Border: 2px solid #FFB5B5
  - Shadow: 0 0 0 4px rgba(255, 181, 181, 0.15)
- **Error:**
  - Border: 2px solid #E8A5A5
  - Background: #FFF0F0
  - Helper text: #C87878
  - Icon: Alert circle (right side)
- **Disabled:**
  - Background: #F4E4D7
  - Border: #E8D4C9
  - Text: #A68976
  - Cursor: not-allowed
- **Success:**
  - Border: #9BB096
  - Icon: Checkmark (right side)

**Variants:**
- **With Icon:** Left icon, 20px, padding-left: 44px
- **With Clear:** Right "×" button when has value
- **Multiline (Textarea):** Min height: 120px, resize vertical

---

### 3.2 Dropdown/Select

**Visual Specification:**
```
Label
┌──────────────────────────────────┐
│ Selected Option          ▼       │
└──────────────────────────────────┘

Dropdown Menu (Open):
┌──────────────────────────────────┐
│ Option 1                    ✓    │
│ Option 2                         │
│ Option 3                         │
└──────────────────────────────────┘

Trigger:
- Same as Text Input
- Icon: Chevron down, 16px, right side
- Padding right: 40px

Menu:
- Background: #FFFFFF
- Border: 1px solid #E8D4C9
- Border Radius: 12px
- Shadow: 0 8px 24px rgba(92, 58, 46, 0.10)
- Max Height: 280px (scrollable)
- Margin top: 4px

Option:
- Padding: 12px 16px
- Font: Inter Regular, 15px
- Color: #5C3A2E
- Hover: Background #FFF5ED
- Selected: Background #FFE8E8, checkmark icon
```

**States:**
- **Open:** Chevron rotates 180°
- **Closed:** Default state

**Variants:**
- **Multi-select:** Checkboxes, multiple values
- **Searchable:** Input field at top of menu

---

### 3.3 Radio Button

**Visual Specification:**
```
( ) Option Label

Circle:
- Size: 20px × 20px
- Border: 1.5px solid #E8D4C9
- Border Radius: 999px
- Background: #FFFFFF

Label:
- Inter Regular, 15px
- Color: #5C3A2E
- Margin left: 12px
```

**States:**
- **Selected:**
  - Border: 2px solid #FFB5B5
  - Inner circle: 10px, #FFB5B5, centered
- **Hover:**
  - Border: #D4949A
- **Disabled:**
  - Border: #E8D4C9
  - Background: #F4E4D7
  - Label: #A68976

---

### 3.4 Checkbox

**Visual Specification:**
```
[ ] Option Label

Box:
- Size: 20px × 20px
- Border: 1.5px solid #E8D4C9
- Border Radius: 6px
- Background: #FFFFFF

Label:
- Inter Regular, 15px
- Color: #5C3A2E
- Margin left: 12px
```

**States:**
- **Checked:**
  - Background: #FFB5B5
  - Border: #FFB5B5
  - Checkmark: White, 14px, centered
- **Indeterminate:**
  - Background: #FFB5B5
  - Dash: White, 10px, centered
- **Hover:**
  - Border: #D4949A

---

### 3.5 Date Picker

**Visual Specification:**
```
Label
┌──────────────────────────────────┐
│ May 10, 2026              📅     │
└──────────────────────────────────┘

Calendar Popup:
┌──────────────────────────────────┐
│    ← May 2026 →                  │
├──────────────────────────────────┤
│ Su Mo Tu We Th Fr Sa             │
│              1  2  3             │
│  4  5  6  7  8  9 10             │
│ 11 12 13 14 15 16 17             │
│ 18 19 20 21 22 23 24             │
│ 25 26 27 28 29 30 31             │
│                                  │
│         [Today] [Clear]          │
└──────────────────────────────────┘

Trigger:
- Same as Text Input
- Icon: Calendar, 20px, right side
- Value format: "Month DD, YYYY"

Calendar:
- Background: #FFFBF7
- Border Radius: 16px
- Shadow: 0 12px 40px rgba(92, 58, 46, 0.14)
- Padding: 20px

Day Cell: 
- 40px × 40px
- Border Radius: 8px
- Selected: Background #FFB5B5, text white
- Today: Border 2px solid #FFB5B5
- Hover: Background #FFE8E8
```

---

### 3.6 Time Picker

**Visual Specification:**
```
Label
┌──────────────────────────────────┐
│ 2:00 PM                   🕐     │
└──────────────────────────────────┘

Time Selector (Scroll Wheel):
┌──────────────────────────────────┐
│       Hour    :    Minute   AM/PM │
│        01           00        AM  │
│      → 02     :   → 00   →  → PM  │
│        03           15        --  │
└──────────────────────────────────┘

Trigger:
- Same as Text Input
- Icon: Clock, 20px, right side
- Value format: "HH:MM AM/PM"

Selector:
- Background: #FFFFFF
- Border Radius: 16px
- Shadow: 0 8px 24px rgba(92, 58, 46, 0.10)
- Three columns: Hour, Minute, Period
- Selected row: Background #FFE8E8
- Scrollable: Smooth momentum
```

---

### 3.7 Search Bar

**Visual Specification:**
```
┌──────────────────────────────────┐
│ 🔍 Search orders, customers...  × │
└──────────────────────────────────┘

Background: #FFF5ED
Border: None
Border Radius: 24px (pill)
Padding: 12px 16px
Height: 48px

Icon:
- Search: 20px, left side, #A68976
- Clear: 20px, right side, appears when typing

Input:
- Font: Inter Regular, 15px
- Color: #5C3A2E
- Placeholder: #A68976
```

**States:**
- **Focus:** Border 2px solid #FFB5B5
- **With Results:** Results dropdown appears below

---

## 4. Navigation

### 4.1 Bottom Tab Bar

**Visual Specification:**
```
┌─────────────────────────────────────────┐
│   🏠      📅       📖       📊          │
│  Home  Calendar  Menu   Reports         │
└─────────────────────────────────────────┘

Container:
- Background: #FFFFFF
- Border Top: 1px solid rgba(232, 180, 184, 0.2)
- Shadow: 0 -2px 16px rgba(92, 58, 46, 0.06)
- Height: 72px
- Padding: 8px 16px
- Position: Fixed bottom
- Safe Area: Respects device notches

Tab Item:
- Width: 25% (4 items)
- Flex direction: Column
- Align: Center
- Gap: 4px

Icon:
- Size: 24px × 24px
- Active: #FFB5B5 (filled style)
- Inactive: #A68976 (outline style)

Label:
- Font: Inter Medium, 11px
- Active: #5C3A2E
- Inactive: #A68976
- Text Transform: None
```

**Active State:**
- Icon scale: 1.1
- Subtle glow: 0 0 8px rgba(255, 181, 181, 0.3)
- Label: Bold weight

**Animation:**
- Tab switch: 250ms ease
- Icon scale: 200ms cubic-bezier

---

### 4.2 Top Navigation Bar

**Visual Specification:**
```
┌─────────────────────────────────────────┐
│ ←  Screen Title              🔍  ⋯      │
└─────────────────────────────────────────┘

Container:
- Background: #FFFBF7
- Border Bottom: 1px solid rgba(232, 180, 184, 0.15)
- Height: 56px
- Padding: 0 16px
- Safe Area: Respects status bar

Left:
- Back button: Icon button, 44px × 44px
- Icon: Arrow left, 24px, #5C3A2E

Center:
- Title: Playfair Display Semibold, 20px, #5C3A2E
- Subtitle (optional): Inter Regular, 13px, #8B6E5F

Right:
- Action buttons: Icon buttons, 44px × 44px
- Max 2 icons
```

**Variants:**
- **With Search:** Search bar expands, title shrinks
- **Transparent:** No background, no border (for hero sections)
- **Scrolled:** Shadow appears on scroll

---

### 4.3 Tab Selector (Horizontal)

**Visual Specification:**
```
┌─────────────────────────────────────────┐
│  Today    Tomorrow    Week    Month     │
│  ────                                   │
└─────────────────────────────────────────┘

Container:
- Background: Transparent
- Border Bottom: 2px solid #F4E4D7
- Height: 44px
- Padding: 0 16px

Tab:
- Padding: 12px 16px
- Font: Inter Medium, 15px
- Active: #5C3A2E, border-bottom 2px solid #FFB5B5
- Inactive: #8B6E5F
- Hover: #D4949A

Indicator:
- Height: 2px
- Background: #FFB5B5
- Width: Matches tab text width
- Transition: 300ms cubic-bezier (smooth slide)
```

---

## 5. Feedback Components

### 5.1 Badge

**Visual Specification:**
```
┌─────────┐
│ PENDING │
└─────────┘

Container:
- Display: Inline-block
- Border Radius: 8px
- Padding: 4px 10px
- Font: Inter Semibold, 11px
- Text Transform: Uppercase
- Letter Spacing: 0.5px

Status Variants:
Pending:
- Background: #FFF9F0
- Text: #B8874E

Completed:
- Background: #F0F5EF
- Text: #7A9475

In Progress:
- Background: #F5F8FF
- Text: #6B8BB8

Urgent:
- Background: #FFF0F0
- Text: #C87878
```

**Sizes:**
- Small: 10px font, 3px 8px padding
- Medium: Default (above)
- Large: 13px font, 6px 12px padding

---

### 5.2 Toast Notification

**Visual Specification:**
```
┌─────────────────────────────────────┐
│ ✓ Order created! 🎂                 │
└─────────────────────────────────────┘

Container:
- Background: #5C3A2E (dark) or #FFFFFF (light)
- Border Radius: 12px
- Shadow: 0 8px 24px rgba(92, 58, 46, 0.2)
- Padding: 14px 20px
- Min Width: 280px
- Max Width: 90vw
- Position: Fixed top, center
- Margin top: 20px

Content:
- Icon: 20px, left side
- Text: Inter Medium, 15px
- Dark toast: White text
- Light toast: #5C3A2E text

Animation:
- Enter: Slide down + fade in (300ms)
- Exit: Fade out (200ms)
- Duration: 3 seconds (auto-dismiss)
```

**Variants:**
- **Success:** Green icon, "✓"
- **Error:** Coral icon, "×"
- **Info:** Blue icon, "ℹ"
- **Warning:** Amber icon, "⚠"

---

### 5.3 Modal Dialog

**Visual Specification:**
```
    ┌───────────────────────────┐
    │ Dialog Title              │
    │                           │
    │ Dialog content goes here  │
    │ with description text     │
    │                           │
    │ [Cancel]     [Confirm]    │
    └───────────────────────────┘

Backdrop:
- Background: rgba(92, 58, 46, 0.5)
- Blur: 4px (backdrop-filter)

Dialog:
- Background: #FFFFFF
- Border Radius: 20px
- Shadow: 0 12px 40px rgba(92, 58, 46, 0.14)
- Padding: 32px
- Width: 90vw
- Max Width: 400px

Title:
- Playfair Display Semibold, 22px
- Color: #5C3A2E
- Margin bottom: 16px

Content:
- Inter Regular, 15px
- Color: #8B6E5F
- Line height: 24px

Actions:
- Flex row, justify end
- Gap: 12px
- Margin top: 24px
```

**Animation:**
- Backdrop: Fade in (200ms)
- Dialog: Scale 0.9 → 1.0 + fade in (300ms)

---

### 5.4 Bottom Sheet

**Visual Specification:**
```
┌─────────────────────────────────────┐
│             ────                    │ ← Handle
│                                     │
│ Sheet Title                         │
│                                     │
│ Sheet content...                    │
│                                     │
│                                     │
└─────────────────────────────────────┘

Container:
- Background: #FFFBF7
- Border Radius: 24px 24px 0 0
- Shadow: 0 -4px 24px rgba(92, 58, 46, 0.12)
- Max Height: 85vh
- Position: Fixed bottom
- Padding: 24px

Handle:
- Width: 40px
- Height: 4px
- Background: #E8D4C9
- Border Radius: 2px
- Centered top
- Margin: 12px auto 20px

Title:
- Playfair Display Semibold, 20px
- Color: #5C3A2E
- Margin bottom: 20px

Content:
- Scrollable if overflow
- Padding bottom: Safe area
```

**Interactions:**
- Drag handle to dismiss
- Tap backdrop to close
- Swipe down to close

---

### 5.5 Skeleton Loader

**Visual Specification:**
```
┌────────────────────────────────────┐
│ ▓▓▓▓▓▓▓▓▓                         │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                   │
│                                    │
│ ▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓▓                │
│ ▓▓▓▓▓▓▓▓▓                         │
└────────────────────────────────────┘

Shape:
- Border Radius: Match component
- Background: Linear gradient shimmer
  - Color 1: #F4E4D7
  - Color 2: #E8D4C9
  - Color 3: #F4E4D7
- Animation: Wave effect
  - Duration: 2s
  - Timing: ease-in-out
  - Infinite loop
  - Direction: Left to right
```

**Usage:**
- Card skeletons during load
- Text line skeletons
- Image placeholders

---

### 5.6 Progress Indicator

**Visual Specification:**
```
Step 1/4

┌───────┬───────┬───────┬───────┐
│   ●   │   ●   │   ○   │   ○   │
└───────┴───────┴───────┴───────┘

Container:
- Flex row, space between
- Width: 100%
- Margin: 20px 0

Step:
- Flex: 1
- Height: 4px
- Background: #F4E4D7 (inactive)
- Background: #FFB5B5 (active)
- Border Radius: 2px

Dots (Alternative):
- Size: 8px × 8px
- Border Radius: 999px
- Background: #E8D4C9 (inactive)
- Background: #FFB5B5 (active)
- Gap: 8px

Label:
- Inter Medium, 13px
- Color: #8B6E5F
- Centered above
```

---

## 6. Data Display

### 6.1 Avatar

**Visual Specification:**
```
┌────┐
│ PS │
└────┘

Size: 40px × 40px (default)
Border Radius: 999px
Background: Linear gradient
  - Based on name hash
  - Soft pastels (#FFE8E8, #F5F8FF, #F0F5EF)
Border: 2px solid #FFFFFF
Shadow: 0 2px 8px rgba(92, 58, 46, 0.08)

Initials:
- Font: Inter Semibold, 16px
- Color: #5C3A2E
- Centered

Image (if available):
- Object-fit: cover
- Border Radius: Inherit
```

**Sizes:**
- Small: 32px, font 14px
- Medium: 40px, font 16px
- Large: 56px, font 20px
- XLarge: 80px, font 28px

---

### 6.2 List Item

**Visual Specification:**
```
┌────────────────────────────────────┐
│ Title Text                         │
│ Subtitle or description            │
│                                    │
└────────────────────────────────────┘

Container:
- Border Bottom: 1px solid #F4E4D7
- Padding: 16px 0
- Background: Transparent

Left (optional):
- Icon or avatar: 40px

Center:
- Title: Inter Medium, 15px, #5C3A2E
- Subtitle: Inter Regular, 13px, #8B6E5F
- Line clamp: 2 lines max

Right (optional):
- Chevron or value
- Inter Regular, 14px, #A68976
```

**States:**
- **Hover:** Background #FFF5ED
- **Active:** Background #FFE8E8
- **Swipeable:** Same as Order Card

---

### 6.3 Empty State

**Visual Specification:**
```
┌────────────────────────────────────┐
│                                    │
│     [Floral Illustration]          │
│          200px × 200px             │
│                                    │
│     No orders today!               │
│     Time to relax 🌸               │
│                                    │
│     [Create New Order]             │
│                                    │
└────────────────────────────────────┘

Container:
- Padding: 48px 24px
- Text align: Center
- Min Height: 400px
- Flex: Center vertically

Illustration:
- Width: 200px
- Height: 200px
- Opacity: 0.9
- Margin bottom: 32px

Heading:
- Playfair Display Semibold, 24px
- Color: #5C3A2E
- Margin bottom: 8px

Description:
- Inter Regular, 15px
- Color: #8B6E5F
- Max Width: 320px

Action Button:
- Margin top: 24px
- Primary style
```

---

### 6.4 Divider

**Visual Specification:**
```
───────────────────────

Horizontal:
- Height: 1px
- Background: #F4E4D7
- Margin: 20px 0

Vertical:
- Width: 1px
- Background: #F4E4D7
- Height: 100%
- Margin: 0 16px
```

**Variants:**
- **With Text:** "OR" centered with background
- **Dashed:** Border-style: dashed
- **Thick:** 2px height

---

## 7. Decorative Elements

### 7.1 Floral Decoration

**Specification:**
```
Small Corner: 32px × 32px
Medium: 64px × 64px
Large Header: 120px × 120px

Opacity: 15-30%
Position: Absolute
Colors: Extract from menu (soft pinks, peaches, sage)
Style: Watercolor, soft edges
Format: SVG for crisp scaling
```

**Placement Guidelines:**
- Top-right corners of cards (32px)
- Page headers (80-120px)
- Empty states (200px, center)
- Never overlap important content
- Maintain 16px clearance from text

---

### 7.2 Floating Petals (Background Animation)

**Specification:**
```
Size: 8-20px (randomized)
Color: #FFB5B5, #FFC9C9, #E8B4B8 (randomized)
Opacity: 0.1-0.3
Count: 3-5 petals max per screen

Animation:
- Y movement: ±20px
- Duration: 4-8s (per petal, random)
- Easing: ease-in-out
- Infinite loop
- Slight rotation: ±15deg
```

**Usage:**
- Success states
- Completion animations
- Onboarding screens
- Never on forms or during user input

---

## 8. Charts & Visualizations

### 8.1 Line Chart

**Specification:**
```
Container:
- Height: 240px
- Padding: 16px
- Background: Transparent

Line:
- Stroke: #FFB5B5
- Stroke Width: 2.5px
- Fill: Linear gradient (top: rgba(255,181,181,0.2), bottom: transparent)
- Corner Radius: Smooth curves (not sharp angles)

Grid:
- Lines: #F4E4D7
- Stroke Width: 1px
- Opacity: 0.5
- Horizontal only (or minimal vertical)

Axis Labels:
- Font: Inter Regular, 11px
- Color: #A68976

Data Points:
- Circle: 6px diameter
- Fill: #FF9E9E
- Stroke: #FFFFFF, 2px
- Hover: Scale to 8px

Tooltip:
- Background: #5C3A2E
- Text: #FFFFFF
- Border Radius: 8px
- Padding: 8px 12px
- Shadow: 0 4px 12px rgba(92, 58, 46, 0.2)
```

---

### 8.2 Donut Chart

**Specification:**
```
Container:
- Size: 200px × 200px
- Center: Value display

Ring:
- Inner Radius: 60%
- Outer Radius: 85%
- Stroke Width: 25%

Segments:
- Instagram: #FFB5B5
- WhatsApp: #B8C9B4
- Repeat: #F4C896
- Phone: #B8C9E8

Labels:
- Font: Inter Medium, 13px
- Color: #5C3A2E
- Position: Outside with connecting lines

Center Value:
- Font: Playfair Display Semibold, 32px
- Color: #5C3A2E
- Label: Inter Regular, 13px, #8B6E5F

Interaction:
- Hover: Segment expands slightly (scale 1.05)
- Tooltip: Shows exact value
```

---

### 8.3 Bar Chart

**Specification:**
```
Container:
- Height: 240px
- Padding: 16px

Bars:
- Width: Auto (responsive)
- Min Width: 24px
- Gap: 8px
- Border Radius: 8px (top)
- Fill: Linear gradient
  - Top: #FFB5B5
  - Bottom: #FF9E9E

Grid:
- Same as Line Chart

Labels:
- X-axis: Below bars, Inter Regular, 12px
- Y-axis: Left side, #A68976

Value Display:
- Position: Top of bar
- Font: Inter Semibold, 12px
- Color: #5C3A2E

Interaction:
- Hover: Bar lifts slightly (shadow increase)
```

---

## Component Usage Matrix

| Component | Home | Calendar | Menu | Reports | Forms |
|-----------|------|----------|------|---------|-------|
| Order Card | ✓✓✓ | ✓✓ | - | ✓ | - |
| Product Card | - | - | ✓✓✓ | - | - |
| Stat Card | ✓✓ | - | - | ✓✓✓ | - |
| Text Input | - | - | - | - | ✓✓✓ |
| Button (Primary) | ✓✓ | ✓ | ✓ | ✓ | ✓✓✓ |
| Bottom Tab | ✓✓✓ | ✓✓✓ | ✓✓✓ | ✓✓✓ | - |
| Modal | ✓✓ | ✓ | - | - | ✓ |
| Bottom Sheet | ✓✓ | ✓✓ | ✓✓ | - | ✓✓ |
| Toast | ✓✓ | ✓✓ | ✓ | ✓ | ✓✓ |
| Empty State | ✓ | ✓ | ✓ | ✓ | - |
| Charts | - | - | - | ✓✓✓ | - |

Legend:
- ✓✓✓ = Primary component
- ✓✓ = Frequently used
- ✓ = Occasionally used
- - = Not used

---

This component library creates a cohesive, reusable system that maintains the elegant, handcrafted aesthetic throughout the entire application.
