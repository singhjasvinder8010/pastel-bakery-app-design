# Pastel Bakery Co - Motion & Animation Guide

## Animation Philosophy

The app's motion language should feel:
- **Gentle**: Like floating petals, never jarring
- **Organic**: Natural curves and flows
- **Delicate**: Subtle and refined
- **Warm**: Inviting and comforting
- **Purposeful**: Always enhancing usability, never decorative only

---

## Core Animation Principles

### 1. Easing Functions

```css
/* Primary Easing (Default) */
--ease-standard: cubic-bezier(0.4, 0.0, 0.2, 1);
/* Use for: Most transitions, card movements, fades */

/* Ease Out (Deceleration) */
--ease-out: cubic-bezier(0.0, 0.0, 0.2, 1);
/* Use for: Entering elements, expanding items */

/* Ease In (Acceleration) */
--ease-in: cubic-bezier(0.4, 0.0, 1, 1);
/* Use for: Exiting elements, collapsing items */

/* Ease In-Out (Smooth) */
--ease-in-out: cubic-bezier(0.4, 0.0, 0.6, 1);
/* Use for: Navigation transitions, modal appearances */

/* Gentle Bounce */
--ease-bounce: cubic-bezier(0.68, -0.55, 0.265, 1.55);
/* Use for: Success states, completion animations */

/* Soft Spring */
--ease-spring: cubic-bezier(0.175, 0.885, 0.32, 1.275);
/* Use for: Button presses, interactive feedback */
```

### 2. Duration Scale

```css
/* Ultra Fast */
--duration-instant: 100ms;
/* Use for: Hover states, color changes */

/* Fast */
--duration-fast: 150ms;
/* Use for: Micro-interactions, tooltips */

/* Medium */
--duration-medium: 250ms;
/* Use for: Cards, buttons, standard transitions */

/* Slow */
--duration-slow: 400ms;
/* Use for: Page transitions, complex animations */

/* Very Slow */
--duration-very-slow: 600ms;
/* Use for: Modal appearances, decorative animations */

/* Extra Slow */
--duration-extra-slow: 800ms;
/* Use for: Onboarding, celebration animations */
```

### 3. Delay Scale

```css
/* Stagger delays for list animations */
--delay-stagger-1: 60ms;  /* First item */
--delay-stagger-2: 120ms; /* Second item */
--delay-stagger-3: 180ms; /* Third item */
--delay-stagger-4: 240ms; /* Fourth item */
/* Pattern: increment by 60ms per item, max 5 items */
```

---

## Component Animations

### Button Interactions

#### Press Animation
```css
.button:active {
  transform: scale(0.96);
  transition: transform 150ms cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.button:not(:active) {
  transform: scale(1);
  transition: transform 200ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Press down: Scale to 96% in 150ms with spring easing
- Release: Return to 100% in 200ms with standard easing
- Creates tactile, responsive feel

#### Hover Animation (Desktop)
```css
.button:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-2);
  transition: all 200ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Lift 2px upward
- Shadow increases from Level 1 to Level 2
- Smooth 200ms transition

#### Loading State
```css
@keyframes button-pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.6; }
}

.button--loading {
  animation: button-pulse 1.5s ease-in-out infinite;
  pointer-events: none;
}
```

**Behavior:**
- Gentle pulsing opacity
- Prevents interaction
- Spinner icon rotates continuously

---

### Card Animations

#### Card Enter (Stagger)
```css
@keyframes card-enter {
  from {
    opacity: 0;
    transform: translateY(16px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.order-card:nth-child(1) {
  animation: card-enter 400ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 0ms;
}

.order-card:nth-child(2) {
  animation: card-enter 400ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 60ms;
}

.order-card:nth-child(3) {
  animation: card-enter 400ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 120ms;
}

/* Max 5 cards stagger, then instant appear */
```

**Behavior:**
- Cards fade in from below
- 16px vertical movement
- 60ms stagger between cards
- Smooth, elegant entrance

#### Card Hover
```css
.order-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-2);
  transition: all 250ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

#### Card Swipe (Left)
```css
.order-card.swiped-left {
  transform: translateX(-80px);
  transition: transform 250ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.order-card.swiped-left .swipe-actions {
  opacity: 1;
  transition: opacity 200ms ease-out 100ms; /* Delay reveal */
}
```

**Behavior:**
- Card slides left 80px
- Actions fade in after 100ms delay
- Returns smoothly if tap outside

#### Card Exit (Complete)
```css
@keyframes card-complete {
  0% {
    opacity: 1;
    transform: scale(1) translateX(0);
  }
  50% {
    opacity: 0.6;
    transform: scale(1.02) translateX(8px);
  }
  100% {
    opacity: 0;
    transform: scale(0.9) translateX(40px);
  }
}

.order-card--completing {
  animation: card-complete 500ms cubic-bezier(0.4, 0.0, 0.6, 1);
  animation-fill-mode: forwards;
}
```

**Behavior:**
- Slight scale up, then shrink
- Fade out while moving right
- Creates satisfying "checked off" feel

---

### Swipe Gesture Animations

#### Swipe Threshold Feedback
```css
/* As user swipes, provide progressive feedback */
.order-card[data-swipe-progress="25"] {
  /* 25% swiped - hint */
  transform: translateX(-20px);
  transition: transform 100ms linear;
}

.order-card[data-swipe-progress="50"] {
  /* 50% swiped - ready */
  transform: translateX(-40px);
  transition: transform 100ms linear;
}

.order-card[data-swipe-progress="75"] {
  /* 75% swiped - committed */
  transform: translateX(-60px);
  transition: transform 100ms linear;
}
```

**Behavior:**
- Follow finger with immediate response
- Linear transition for direct manipulation feel
- Action buttons reveal progressively

#### Swipe Release (Snapback)
```css
.order-card.swipe-release {
  transform: translateX(0);
  transition: transform 300ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

**Behavior:**
- If released before threshold, snap back
- Gentle bounce easing
- Feels springy and forgiving

---

### Modal & Sheet Animations

#### Modal Enter
```css
/* Backdrop */
@keyframes backdrop-enter {
  from { opacity: 0; }
  to { opacity: 1; }
}

.modal-backdrop {
  animation: backdrop-enter 200ms ease-out;
}

/* Dialog */
@keyframes modal-enter {
  from {
    opacity: 0;
    transform: scale(0.9) translateY(-20px);
  }
  to {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
}

.modal-dialog {
  animation: modal-enter 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Backdrop fades in quickly
- Dialog scales up and drops down slightly
- Feels like it's landing gently

#### Modal Exit
```css
@keyframes modal-exit {
  from {
    opacity: 1;
    transform: scale(1) translateY(0);
  }
  to {
    opacity: 0;
    transform: scale(0.95) translateY(10px);
  }
}

.modal-dialog--exiting {
  animation: modal-exit 200ms cubic-bezier(0.4, 0.0, 1, 1);
}
```

#### Bottom Sheet Enter
```css
@keyframes sheet-enter {
  from {
    transform: translateY(100%);
  }
  to {
    transform: translateY(0);
  }
}

.bottom-sheet {
  animation: sheet-enter 350ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Slides up from bottom
- Smooth deceleration
- Can be dragged during animation

#### Bottom Sheet Drag
```css
/* Follow finger directly, no animation during drag */
.bottom-sheet[data-dragging="true"] {
  transform: translateY(var(--drag-offset));
  transition: none; /* Instant response */
}

/* On release, snap to position or dismiss */
.bottom-sheet[data-releasing="true"] {
  transition: transform 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

---

### Navigation Transitions

#### Tab Switch
```css
/* Outgoing screen */
@keyframes tab-exit {
  from {
    opacity: 1;
    transform: translateX(0);
  }
  to {
    opacity: 0;
    transform: translateX(-20px);
  }
}

/* Incoming screen */
@keyframes tab-enter {
  from {
    opacity: 0;
    transform: translateX(20px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.screen--exiting {
  animation: tab-exit 250ms cubic-bezier(0.4, 0.0, 1, 1);
}

.screen--entering {
  animation: tab-enter 250ms cubic-bezier(0.0, 0.0, 0.2, 1);
}
```

**Behavior:**
- Cross-fade between screens
- Subtle horizontal movement
- Fast enough to feel instant, slow enough to be smooth

#### Stack Navigation (Push)
```css
/* Screen being pushed (current) */
@keyframes stack-push-old {
  from {
    opacity: 1;
    transform: translateX(0) scale(1);
  }
  to {
    opacity: 0.6;
    transform: translateX(-30%) scale(0.95);
  }
}

/* Screen entering (new) */
@keyframes stack-push-new {
  from {
    transform: translateX(100%);
  }
  to {
    transform: translateX(0);
  }
}

.screen--pushed {
  animation: stack-push-old 350ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.screen--entering {
  animation: stack-push-new 350ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

#### Stack Navigation (Pop/Back)
```css
/* Screen being popped (current) */
@keyframes stack-pop-old {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(100%);
  }
}

/* Screen returning (previous) */
@keyframes stack-pop-new {
  from {
    opacity: 0.6;
    transform: translateX(-30%) scale(0.95);
  }
  to {
    opacity: 1;
    transform: translateX(0) scale(1);
  }
}

.screen--popped {
  animation: stack-pop-old 350ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.screen--returning {
  animation: stack-pop-new 350ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

---

### Form & Input Animations

#### Input Focus
```css
.input:focus {
  border-color: #FFB5B5;
  box-shadow: 0 0 0 4px rgba(255, 181, 181, 0.15);
  transition: all 200ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

#### Input Error (Shake)
```css
@keyframes input-error-shake {
  0%, 100% { transform: translateX(0); }
  10%, 30%, 50%, 70%, 90% { transform: translateX(-4px); }
  20%, 40%, 60%, 80% { transform: translateX(4px); }
}

.input--error {
  animation: input-error-shake 500ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Quick horizontal shake
- 5 oscillations
- Draws attention to error

#### Checkbox Check
```css
@keyframes checkbox-check {
  0% {
    stroke-dashoffset: 16;
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    stroke-dashoffset: 0;
    opacity: 1;
  }
}

.checkbox__checkmark {
  stroke-dasharray: 16;
  stroke-dashoffset: 16;
  animation: checkbox-check 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

**Behavior:**
- Checkmark draws in from top-left
- Smooth stroke animation
- Satisfying completion feel

#### Radio Select
```css
@keyframes radio-select {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  50% {
    transform: scale(1.2);
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.radio__indicator {
  animation: radio-select 250ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

---

### Loading States

#### Skeleton Shimmer
```css
@keyframes skeleton-shimmer {
  0% {
    background-position: -200% 0;
  }
  100% {
    background-position: 200% 0;
  }
}

.skeleton {
  background: linear-gradient(
    90deg,
    #F4E4D7 0%,
    #E8D4C9 50%,
    #F4E4D7 100%
  );
  background-size: 200% 100%;
  animation: skeleton-shimmer 2s ease-in-out infinite;
}
```

#### Spinner (Flower Petals)
```css
@keyframes spinner-rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.spinner {
  animation: spinner-rotate 1.5s cubic-bezier(0.4, 0.0, 0.2, 1) infinite;
}

/* Individual petals pulse */
@keyframes petal-pulse {
  0%, 100% {
    opacity: 0.6;
    transform: scale(1);
  }
  50% {
    opacity: 1;
    transform: scale(1.1);
  }
}

.spinner__petal:nth-child(1) {
  animation: petal-pulse 1.5s ease-in-out infinite;
  animation-delay: 0ms;
}

.spinner__petal:nth-child(2) {
  animation: petal-pulse 1.5s ease-in-out infinite;
  animation-delay: 200ms;
}

.spinner__petal:nth-child(3) {
  animation: petal-pulse 1.5s ease-in-out infinite;
  animation-delay: 400ms;
}

/* ... up to 6 petals */
```

#### Progress Bar
```css
@keyframes progress-fill {
  from {
    transform: scaleX(0);
    transform-origin: left;
  }
  to {
    transform: scaleX(1);
    transform-origin: left;
  }
}

.progress-bar__fill {
  animation: progress-fill 400ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

/* Indeterminate state */
@keyframes progress-indeterminate {
  0% {
    transform: translateX(-100%);
  }
  100% {
    transform: translateX(100%);
  }
}

.progress-bar__fill--indeterminate {
  animation: progress-indeterminate 1.5s cubic-bezier(0.4, 0.0, 0.2, 1) infinite;
}
```

---

### Success & Completion Animations

#### Checkmark Draw
```css
@keyframes checkmark-draw {
  0% {
    stroke-dashoffset: 100;
  }
  100% {
    stroke-dashoffset: 0;
  }
}

.success-checkmark {
  stroke-dasharray: 100;
  stroke-dashoffset: 100;
  animation: checkmark-draw 600ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

/* Circle background expands */
@keyframes success-circle {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  50% {
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.success-circle {
  animation: success-circle 400ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

**Sequence:**
1. Circle expands (0-400ms)
2. Checkmark draws (200-800ms, overlaps)
3. Total: 800ms

#### Floating Petals (Background)
```css
@keyframes petal-float {
  0% {
    transform: translateY(0) translateX(0) rotate(0deg);
    opacity: 0;
  }
  10% {
    opacity: 0.3;
  }
  90% {
    opacity: 0.3;
  }
  100% {
    transform: translateY(-100px) translateX(20px) rotate(180deg);
    opacity: 0;
  }
}

.floating-petal {
  animation: petal-float 6s cubic-bezier(0.4, 0.0, 0.6, 1) infinite;
}

.floating-petal:nth-child(1) {
  animation-delay: 0s;
  left: 10%;
}

.floating-petal:nth-child(2) {
  animation-delay: 2s;
  left: 30%;
}

.floating-petal:nth-child(3) {
  animation-delay: 4s;
  left: 50%;
}

/* Randomize timing and position for organic feel */
```

**Usage:**
- Success states
- Order completion
- Celebration moments
- Max 3-5 petals simultaneously

#### Confetti Burst (Special Occasions)
```css
@keyframes confetti-burst {
  0% {
    transform: translateY(0) scale(1) rotate(0deg);
    opacity: 1;
  }
  100% {
    transform: translateY(150px) scale(0.5) rotate(720deg);
    opacity: 0;
  }
}

.confetti-piece {
  animation: confetti-burst 1.2s cubic-bezier(0.4, 0.0, 0.6, 1);
}

/* Randomize: 
   - delay (0-200ms)
   - trajectory (different translateX values)
   - rotation speed (360-1080deg)
*/
```

**Usage:**
- First order completed
- Milestone achievements
- Monthly report unlocked

---

### Toast Notifications

#### Toast Enter
```css
@keyframes toast-enter {
  from {
    opacity: 0;
    transform: translateY(-20px) scale(0.95);
  }
  to {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.toast {
  animation: toast-enter 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

#### Toast Exit
```css
@keyframes toast-exit {
  from {
    opacity: 1;
    transform: translateY(0);
  }
  to {
    opacity: 0;
    transform: translateY(-10px);
  }
}

.toast--exiting {
  animation: toast-exit 200ms cubic-bezier(0.4, 0.0, 1, 1);
}
```

#### Toast Progress Bar
```css
@keyframes toast-progress {
  from {
    transform: scaleX(1);
  }
  to {
    transform: scaleX(0);
  }
}

.toast__progress {
  transform-origin: left;
  animation: toast-progress 3s linear;
}
```

---

### Badge & Tag Animations

#### Badge Appear
```css
@keyframes badge-appear {
  0% {
    transform: scale(0);
    opacity: 0;
  }
  50% {
    transform: scale(1.15);
    opacity: 1;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.badge--new {
  animation: badge-appear 400ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

#### Badge Pulse (Notification)
```css
@keyframes badge-pulse {
  0%, 100% {
    transform: scale(1);
    box-shadow: 0 0 0 0 rgba(255, 181, 181, 0.7);
  }
  50% {
    transform: scale(1.05);
    box-shadow: 0 0 0 4px rgba(255, 181, 181, 0);
  }
}

.badge--alert {
  animation: badge-pulse 2s ease-in-out infinite;
}
```

---

### Empty State Animations

#### Illustration Float
```css
@keyframes illustration-float {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

.empty-state__illustration {
  animation: illustration-float 3s ease-in-out infinite;
}
```

#### Text Fade In (Stagger)
```css
@keyframes text-fade-in {
  from {
    opacity: 0;
    transform: translateY(8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.empty-state__heading {
  animation: text-fade-in 500ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 200ms;
  animation-fill-mode: backwards;
}

.empty-state__description {
  animation: text-fade-in 500ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 350ms;
  animation-fill-mode: backwards;
}

.empty-state__button {
  animation: text-fade-in 500ms cubic-bezier(0.4, 0.0, 0.2, 1);
  animation-delay: 500ms;
  animation-fill-mode: backwards;
}
```

---

## Scroll Animations

### Pull to Refresh
```css
/* Spinner reveals as user pulls */
.refresh-spinner {
  transform: translateY(-100%) rotate(0deg);
  opacity: 0;
  transition: all 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.refresh-spinner[data-pull-progress="50"] {
  transform: translateY(-50%) rotate(180deg);
  opacity: 0.5;
}

.refresh-spinner[data-pull-progress="100"] {
  transform: translateY(0) rotate(360deg);
  opacity: 1;
}

/* Release triggers spin */
.refresh-spinner--loading {
  animation: spinner-rotate 1s linear infinite;
}
```

### Infinite Scroll Loader
```css
@keyframes loader-fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.infinite-loader {
  animation: loader-fade-in 400ms cubic-bezier(0.4, 0.0, 0.2, 1);
}
```

### Scroll-Triggered Animations

#### Parallax Floral Decorations
```javascript
// Pseudo-code for scroll-based parallax
floralDecoration.style.transform = `translateY(${scrollY * 0.3}px)`;
```

**Effect:**
- Decorative florals move slower than content
- Creates depth
- Subtle, not distracting

#### Header Collapse
```css
/* Expanded state */
.header--expanded {
  height: 80px;
  transition: height 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

/* Collapsed state (on scroll) */
.header--collapsed {
  height: 56px;
  transition: height 300ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.header__greeting--collapsed {
  opacity: 0;
  transform: translateY(-8px);
  transition: all 250ms cubic-bezier(0.4, 0.0, 1, 1);
}
```

---

## Gesture Feedback

### Long Press (Haptic Feedback Equivalent)
```css
@keyframes long-press-scale {
  0% {
    transform: scale(1);
  }
  100% {
    transform: scale(0.97);
  }
}

.element--long-pressing {
  animation: long-press-scale 300ms cubic-bezier(0.4, 0.0, 0.2, 1) forwards;
}
```

**Trigger:** After 500ms of continuous press

### Drag Handle
```css
@keyframes drag-handle-pulse {
  0%, 100% {
    opacity: 0.6;
  }
  50% {
    opacity: 1;
  }
}

.drag-handle {
  animation: drag-handle-pulse 2s ease-in-out infinite;
}

/* Stop pulsing after first interaction */
.drag-handle--used {
  animation: none;
  opacity: 0.6;
}
```

---

## Accessibility Considerations

### Reduced Motion
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
  
  /* Keep essential functional animations */
  .loading-spinner,
  .progress-bar {
    animation-duration: 1s !important;
  }
}
```

### Focus Animations
```css
.focus-visible {
  outline: 2px solid #FFB5B5;
  outline-offset: 2px;
  transition: outline-offset 150ms cubic-bezier(0.4, 0.0, 0.2, 1);
}

.focus-visible:focus {
  outline-offset: 4px;
}
```

---

## Performance Optimization

### GPU Acceleration
```css
/* Trigger hardware acceleration for smooth animations */
.animated-element {
  will-change: transform, opacity;
  /* Remove will-change after animation completes */
}

/* Prefer transform over position changes */
/* ✅ Good */
transform: translateX(100px);

/* ❌ Avoid */
left: 100px;
```

### Animation Limits
- **Max simultaneous animations:** 10
- **Max floating petals:** 5
- **Stagger max items:** 5 (then instant)
- **Auto-stop:** Background animations pause when app in background

---

## Animation Recipes

### Recipe: Order Completion Flow
```
1. User swipes order card (250ms)
2. User taps "Complete" button
3. Confirmation modal appears (300ms scale-up)
4. User confirms
5. Modal exits (200ms fade)
6. Order card completes exit animation (500ms)
7. Success checkmark draws (600ms)
8. Floating petals release (6s, 3 petals)
9. Toast notification appears (300ms)
10. Toast exits after 3s (200ms)

Total duration: ~4.5s (petals continue in background)
```

### Recipe: New Order Creation
```
1. FAB tap (press animation 150ms)
2. Bottom sheet slides up (350ms)
3. Form fields appear (stagger, 400ms total)
4. User fills form
5. "Next" button tap (press 150ms)
6. Current step fades left (250ms)
7. Next step fades in right (250ms)
8. Repeat steps 6-7 through all steps
9. Final "Create Order" tap
10. Loading spinner (1.5s)
11. Success animation (800ms)
12. Return to home (350ms transition)
13. New order card appears (400ms stagger in list)

Total: ~1.5s of automatic animation
```

---

## Testing Animations

### Animation Checklist
- [ ] Works on 60fps displays
- [ ] Works on 120fps displays (if applicable)
- [ ] No jank or stuttering
- [ ] Respects `prefers-reduced-motion`
- [ ] Appropriate easing curve
- [ ] Appropriate duration
- [ ] Can be interrupted gracefully
- [ ] Doesn't block user input
- [ ] GPU-accelerated when necessary

### Debug Mode
```javascript
// Add to development build
document.body.classList.add('animation-debug');
```

```css
.animation-debug * {
  outline: 1px solid rgba(255, 0, 0, 0.2);
  animation-duration: calc(var(--duration) * 2) !important;
  transition-duration: calc(var(--duration) * 2) !important;
}
```

**Effect:** Slows all animations to 50% speed for debugging

---

This motion system creates a cohesive, delightful, and performant animation language that reinforces the app's elegant, handcrafted aesthetic while maintaining excellent usability.
