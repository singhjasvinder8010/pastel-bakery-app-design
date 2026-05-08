# Pastel Bakery Co - Design System

## Brand Essence
A premium home bakery application that feels like a handcrafted journal meets luxury brand book - elegant, feminine, delicate, warm, and personal.

---

## Color Palette

### Primary Colors
Extracted from the menu's soft, romantic aesthetic:

```
Cream Base
- #FFF8F3 (Primary background - warm off-white)
- #FFF5ED (Secondary background - softer cream)
- #FFFBF7 (Card surfaces)

Blush Pink
- #FFE8E8 (Lightest - backgrounds, subtle highlights)
- #FFC9C9 (Light - accent backgrounds)
- #FFB5B5 (Medium - primary buttons, active states)
- #FF9E9E (Bold - emphasis, CTAs)

Rose
- #E8B4B8 (Muted rose - secondary actions)
- #D4949A (Deep rose - hover states)

Sage Green
- #B8C9B4 (Light sage - success states, nature accents)
- #9BB096 (Medium sage - completed items)
- #7A9475 (Deep sage - confirmation states)

Botanical Accents
- #F4E4D7 (Warm beige)
- #E8D4C9 (Dusty peach)
- #D9C7BC (Taupe)
```

### Typography Colors

```
Text Primary
- #5C3A2E (Rich brown - main headings, body text)
- #8B6E5F (Medium brown - secondary text)
- #A68976 (Light brown - tertiary, captions)

Text Accents
- #7B5E4F (Chocolate brown - emphasis)
- #D4949A (Rose - special callouts)
```

### Semantic Colors

```
Success
- #9BB096 (Soft sage)
- Background: #F0F5EF

Warning
- #F4C896 (Soft amber)
- Background: #FFF9F0

Error
- #E8A5A5 (Soft coral red)
- Background: #FFF0F0

Info
- #B8C9E8 (Soft periwinkle)
- Background: #F5F8FF
```

---

## Typography

### Font Families

**Display & Headings:** Playfair Display (Serif)
- Elegant, feminine, editorial quality
- Used for: App title, section headings, feature text

**Body & UI:** Inter (Sans-serif)
- Clean, modern, highly readable
- Used for: body text, forms, buttons, UI elements

**Accents:** Cormorant Garamond (Serif - alternative)
- Delicate, graceful
- Used for: special callouts, quotes, decorative text

### Type Scale

```
Display Large (App Title)
- Font: Playfair Display
- Size: 32px / 2rem
- Weight: 600 (Semibold)
- Line Height: 40px
- Letter Spacing: -0.5px
- Color: #5C3A2E

Heading 1 (Screen Titles)
- Font: Playfair Display
- Size: 28px / 1.75rem
- Weight: 600
- Line Height: 36px
- Letter Spacing: -0.3px
- Color: #5C3A2E

Heading 2 (Section Headers)
- Font: Playfair Display
- Size: 22px / 1.375rem
- Weight: 600
- Line Height: 30px
- Letter Spacing: 0
- Color: #5C3A2E

Heading 3 (Card Titles)
- Font: Playfair Display
- Size: 18px / 1.125rem
- Weight: 600
- Line Height: 26px
- Color: #5C3A2E

Body Large
- Font: Inter
- Size: 16px / 1rem
- Weight: 400
- Line Height: 24px
- Color: #5C3A2E

Body Regular
- Font: Inter
- Size: 14px / 0.875rem
- Weight: 400
- Line Height: 22px
- Color: #5C3A2E

Body Small
- Font: Inter
- Size: 13px / 0.8125rem
- Weight: 400
- Line Height: 20px
- Color: #8B6E5F

Caption
- Font: Inter
- Size: 12px / 0.75rem
- Weight: 400
- Line Height: 18px
- Color: #A68976

Label
- Font: Inter
- Size: 12px / 0.75rem
- Weight: 500
- Line Height: 16px
- Letter Spacing: 0.3px
- Text Transform: uppercase
- Color: #8B6E5F

Button Text
- Font: Inter
- Size: 15px / 0.9375rem
- Weight: 500
- Line Height: 20px
- Letter Spacing: 0.2px
- Color: #5C3A2E or #FFFFFF
```

---

## Spacing System

Organic, breathing room - more generous than typical enterprise apps.

```
Space 1:  4px   (0.25rem)  - Tight padding
Space 2:  8px   (0.5rem)   - Compact spacing
Space 3:  12px  (0.75rem)  - Default padding
Space 4:  16px  (1rem)     - Standard spacing
Space 5:  20px  (1.25rem)  - Comfortable spacing
Space 6:  24px  (1.5rem)   - Section spacing
Space 7:  32px  (2rem)     - Large spacing
Space 8:  40px  (2.5rem)   - Extra large
Space 9:  48px  (3rem)     - Section breaks
Space 10: 64px  (4rem)     - Screen margins
```

---

## Elevation & Shadows

Soft, layered, paper-like depth - avoiding harsh edges.

```
Level 0 (Flat)
- No shadow

Level 1 (Subtle Card)
- Shadow: 0 2px 8px rgba(92, 58, 46, 0.06)
- Blur: 8px
- Spread: 0

Level 2 (Raised Card)
- Shadow: 0 4px 16px rgba(92, 58, 46, 0.08)
- Blur: 16px
- Spread: 0

Level 3 (Floating)
- Shadow: 0 8px 24px rgba(92, 58, 46, 0.10)
- Blur: 24px
- Spread: 0

Level 4 (Modal/Dialog)
- Shadow: 0 12px 40px rgba(92, 58, 46, 0.14)
- Blur: 40px
- Spread: 0

Inner Glow (Selected State)
- Inner Shadow: inset 0 0 0 2px #FFB5B5
- Glow: 0 0 8px rgba(255, 181, 181, 0.4)
```

---

## Border Radius

Soft, rounded, organic shapes.

```
Radius 1: 8px   - Small elements (badges, tags)
Radius 2: 12px  - Standard cards, buttons
Radius 3: 16px  - Large cards
Radius 4: 20px  - Special containers
Radius 5: 24px  - Hero sections
Radius 6: 999px - Pills, circular avatars
```

---

## Iconography Style

### Guidelines
- **Style:** Outlined, soft rounded strokes
- **Stroke Weight:** 1.5px - 2px (delicate, not bold)
- **Corner Radius:** Rounded ends
- **Size:** 20px × 20px (default), 24px × 24px (emphasis)
- **Color:** Match text colors
- **Sources:** Phosphor Icons (Thin/Light weight), Lucide Icons

### Icon Categories
- Navigation: home, calendar, menu, chart, settings
- Actions: plus, check, edit, trash, share
- Status: clock, check-circle, alert-circle, info
- Product: cake, cupcake, cookie, bread
- Delivery: truck, package, map-pin
- Communication: phone, message, instagram, whatsapp
- Decorative: flower, leaf, sparkle, heart

---

## Illustration Style

### Floral & Botanical Elements
- **Style:** Watercolor-inspired, soft edges, transparent overlays
- **Colors:** Extracted from menu - soft pinks, peaches, sage greens
- **Placement:** 
  - Corners of cards (subtle, ~40px)
  - Page headers (larger, ~80-120px)
  - Empty states (central, ~200px)
  - Background decorations (very subtle, 15% opacity)

### Decorative Patterns
- Floating petals
- Delicate branches
- Small floral clusters
- Watercolor washes

### Usage
- Never overpower content
- Always maintain readability
- Use sparingly but purposefully
- Animate subtly (gentle floating, fading)

---

## Components Library

### 1. Buttons

#### Primary Button
```
Background: Linear gradient #FFB5B5 → #FF9E9E
Text: #5C3A2E
Border: none
Border Radius: 12px
Padding: 14px 24px
Shadow: Level 1
Hover: Lift (shadow Level 2), slight scale (1.02)
Active: Scale (0.98)
Font: Button Text
```

#### Secondary Button
```
Background: #FFF8F3
Text: #5C3A2E
Border: 1.5px solid #E8B4B8
Border Radius: 12px
Padding: 14px 24px
Shadow: none
Hover: Background #FFE8E8, border #D4949A
Active: Scale (0.98)
```

#### Ghost Button
```
Background: transparent
Text: #D4949A
Border: none
Padding: 12px 20px
Hover: Background #FFE8E8
Active: Background #FFC9C9
```

#### Icon Button
```
Size: 40px × 40px
Background: #FFFBF7
Border Radius: 999px
Icon: 20px, #5C3A2E
Shadow: Level 1
Hover: Background #FFE8E8
```

### 2. Cards

#### Standard Order Card
```
Background: #FFFBF7
Border: 1px solid rgba(232, 180, 184, 0.3)
Border Radius: 16px
Padding: 20px
Shadow: Level 1
Hover: Shadow Level 2, subtle lift
Decorative: Small floral element in top-right corner
```

#### Elevated Card
```
Background: #FFFFFF
Border: none
Border Radius: 16px
Padding: 24px
Shadow: Level 2
```

#### Stat Card
```
Background: Linear gradient #FFF8F3 → #FFF5ED
Border: none
Border Radius: 12px
Padding: 16px
Shadow: none
Inner border: 1px solid rgba(232, 180, 184, 0.2)
```

### 3. Inputs

#### Text Input
```
Background: #FFFFFF
Border: 1.5px solid #E8D4C9
Border Radius: 12px
Padding: 12px 16px
Font: Body Regular
Color: #5C3A2E
Placeholder: #A68976

Focus:
- Border: #FFB5B5
- Shadow: 0 0 0 3px rgba(255, 181, 181, 0.15)

Error:
- Border: #E8A5A5
- Background: #FFF0F0
```

#### Select Dropdown
```
Similar to Text Input
Icon: Chevron down, right-aligned
Options: Card-style dropdown with Level 3 shadow
```

#### Checkbox
```
Size: 20px × 20px
Border: 1.5px solid #E8D4C9
Border Radius: 6px
Checked: Background #FFB5B5, checkmark white
```

#### Radio Button
```
Size: 20px × 20px
Border: 1.5px solid #E8D4C9
Border Radius: 999px
Selected: Inner circle #FFB5B5 (12px)
```

### 4. Navigation

#### Bottom Navigation Bar
```
Background: #FFFFFF
Border Top: 1px solid rgba(232, 180, 184, 0.2)
Shadow: 0 -2px 16px rgba(92, 58, 46, 0.06)
Height: 72px
Items: 4-5 max
Active: Icon #FFB5B5, label #5C3A2E (bold)
Inactive: Icon & label #A68976
```

#### Tab Bar
```
Background: transparent
Border Bottom: 2px solid #F4E4D7
Active tab: Border #FFB5B5, text #5C3A2E (semibold)
Inactive: Text #8B6E5F
Indicator: Smooth slide animation
```

### 5. Badges & Tags

#### Status Badge
```
Border Radius: 8px
Padding: 4px 10px
Font: Caption (semibold)
Text Transform: uppercase
Letter Spacing: 0.5px

Pending: Background #FFF9F0, text #B8874E
Completed: Background #F0F5EF, text #7A9475
In Progress: Background #F5F8FF, text #6B8BB8
Urgent: Background #FFF0F0, text #C87878
```

#### Category Tag
```
Background: #FFE8E8
Text: #D4949A
Border Radius: 999px
Padding: 6px 14px
Font: Body Small (medium)
```

### 6. Modals & Sheets

#### Bottom Sheet
```
Background: #FFFBF7
Border Radius: 24px 24px 0 0
Shadow: Level 4
Handle: 40px × 4px, #E8D4C9, centered top
Padding: 24px
Max Height: 85vh
Backdrop: rgba(92, 58, 46, 0.4)
```

#### Modal Dialog
```
Background: #FFFFFF
Border Radius: 20px
Shadow: Level 4
Padding: 32px
Max Width: 90vw
Backdrop: rgba(92, 58, 46, 0.5)
```

### 7. Lists & Tables

#### List Item
```
Background: transparent
Border Bottom: 1px solid #F4E4D7
Padding: 16px 0
Swipeable: Yes (reveal actions)
Hover: Background #FFF5ED
```

#### Table Row (Reports)
```
Border Bottom: 1px solid #F4E4D7
Padding: 12px 16px
Alternate Row: Background #FFF8F3
Hover: Background #FFE8E8
```

### 8. Loading States

#### Skeleton
```
Background: Linear gradient shimmer
- From: #F4E4D7
- To: #E8D4C9
Animation: Gentle wave, 2s duration
Border Radius: Match component
```

#### Spinner
```
Style: Circular, rotating petals/flowers
Color: #FFB5B5
Size: 32px (small), 48px (large)
Animation: Gentle rotation with easing
```

### 9. Empty States

#### Illustration + Message
```
Illustration: Watercolor botanical (200px)
Heading: Heading 3, #5C3A2E
Message: Body Regular, #8B6E5F
CTA Button: Primary
Spacing: Generous vertical rhythm
```

---

## Motion & Animation

### Principles
- Gentle, organic, never jarring
- Inspired by floating petals, paper movement
- Subtle scale and fade transitions
- Easing: cubic-bezier(0.4, 0.0, 0.2, 1)

### Timing
```
Fast: 150ms (hover states, small interactions)
Medium: 250ms (cards, buttons, transitions)
Slow: 400ms (page transitions, modals)
Very Slow: 600ms (decorative animations)
```

### Animations

#### Card Enter
```
Opacity: 0 → 1
Transform: translateY(12px) → translateY(0)
Duration: 400ms
Delay: Stagger 60ms per card
```

#### Button Press
```
Transform: scale(1) → scale(0.96) → scale(1)
Duration: 200ms
```

#### Swipe Action
```
Transform: translateX(0) → translateX(-80px)
Duration: 250ms
Reveal: Action buttons behind card
```

#### Modal Enter
```
Backdrop: opacity 0 → 1 (200ms)
Modal: scale(0.9) opacity(0) → scale(1) opacity(1) (300ms)
```

#### Floating Petals (Background)
```
Animation: Gentle vertical float
Y-Offset: ±20px
Duration: 4-8s (randomized)
Easing: ease-in-out
Opacity: 0.3 → 0.1 → 0.3
```

---

## Responsive Breakpoints

```
Mobile Portrait: 320px - 428px (primary design)
Mobile Landscape: 568px - 926px
Tablet Portrait: 768px - 834px
Tablet Landscape: 1024px - 1366px
```

### Spacing Adjustments
- Mobile: Base spacing
- Tablet: Increase padding by 1.25x
- Large screens: Increase padding by 1.5x

---

## Accessibility

### Touch Targets
- Minimum: 44px × 44px
- Preferred: 48px × 48px
- Spacing: 8px minimum between targets

### Color Contrast
- Text on backgrounds: Minimum 4.5:1
- Large text: Minimum 3:1
- Interactive elements: Clear focus states

### Focus States
```
Outline: 2px solid #FFB5B5
Offset: 2px
Border Radius: Match element + 2px
```

---

## Data Visualization

### Chart Colors
```
Primary: #FFB5B5 (main data)
Secondary: #B8C9B4 (comparison)
Tertiary: #F4C896 (accent)
Grid: #F4E4D7
Labels: #8B6E5F
```

### Chart Style
- Soft rounded bars
- Gentle gradients
- Minimal grid lines
- Elegant axis labels
- Tooltips: Card-style with shadow

---

## Design Tokens (CSS Variables)

```css
:root {
  /* Colors */
  --color-cream-base: #FFF8F3;
  --color-cream-secondary: #FFF5ED;
  --color-surface: #FFFBF7;
  
  --color-pink-lightest: #FFE8E8;
  --color-pink-light: #FFC9C9;
  --color-pink-medium: #FFB5B5;
  --color-pink-bold: #FF9E9E;
  
  --color-rose-muted: #E8B4B8;
  --color-rose-deep: #D4949A;
  
  --color-sage-light: #B8C9B4;
  --color-sage-medium: #9BB096;
  --color-sage-deep: #7A9475;
  
  --color-text-primary: #5C3A2E;
  --color-text-secondary: #8B6E5F;
  --color-text-tertiary: #A68976;
  
  /* Typography */
  --font-display: 'Playfair Display', serif;
  --font-body: 'Inter', sans-serif;
  --font-accent: 'Cormorant Garamond', serif;
  
  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-7: 32px;
  --space-8: 40px;
  --space-9: 48px;
  --space-10: 64px;
  
  /* Radius */
  --radius-sm: 8px;
  --radius-md: 12px;
  --radius-lg: 16px;
  --radius-xl: 20px;
  --radius-2xl: 24px;
  --radius-full: 999px;
  
  /* Shadows */
  --shadow-1: 0 2px 8px rgba(92, 58, 46, 0.06);
  --shadow-2: 0 4px 16px rgba(92, 58, 46, 0.08);
  --shadow-3: 0 8px 24px rgba(92, 58, 46, 0.10);
  --shadow-4: 0 12px 40px rgba(92, 58, 46, 0.14);
  
  /* Timing */
  --timing-fast: 150ms;
  --timing-medium: 250ms;
  --timing-slow: 400ms;
  --timing-very-slow: 600ms;
  
  /* Easing */
  --ease-standard: cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

---

## Usage Guidelines

### Do's
✓ Use generous white space
✓ Layer decorative florals subtly
✓ Maintain soft, rounded corners throughout
✓ Keep animations gentle and organic
✓ Use serif fonts for emotional warmth in headings
✓ Apply soft shadows for depth
✓ Create breathing room in layouts
✓ Use the pink gradient for primary actions
✓ Include decorative elements in empty states

### Don'ts
✗ Use harsh, bright colors
✗ Apply rigid, boxy layouts
✗ Create dense, cluttered interfaces
✗ Use sharp corners or edges
✗ Apply aggressive animations
✗ Use monochrome or cold palettes
✗ Overcrowd with decorative elements
✗ Use default system components without customization
✗ Apply heavy, bold typography everywhere

---

This design system creates a cohesive, premium bakery brand experience that feels handcrafted, warm, and delightfully organized.
