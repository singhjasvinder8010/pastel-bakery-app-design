# Pastel Bakery Co - Technical Implementation Guide

## Technology Stack Recommendations

### Frontend
- **Framework:** React Native (cross-platform iOS/Android)
  - Alternative: Flutter
- **Navigation:** React Navigation 6+
- **State Management:** Zustand or Redux Toolkit
- **Forms:** React Hook Form
- **Animations:** Reanimated 3 + Gesture Handler
- **Storage:** AsyncStorage + WatermelonDB (offline-first)
- **UI Testing:** Jest + React Native Testing Library

### Backend (Future)
- **API:** Node.js + Express or Firebase
- **Database:** PostgreSQL or Firestore
- **Authentication:** Firebase Auth
- **Storage:** Firebase Storage or AWS S3

### Design Implementation
- **Styling:** Styled Components or Tamagui
- **Icons:** React Native SVG + Custom icon set
- **Fonts:** 
  - Playfair Display (Google Fonts)
  - Inter (Google Fonts)
  - Cormorant Garamond (Google Fonts)

---

## Project Structure

```
pastel-bakery-app/
├── src/
│   ├── components/          # Reusable UI components
│   │   ├── buttons/
│   │   │   ├── PrimaryButton.tsx
│   │   │   ├── SecondaryButton.tsx
│   │   │   ├── IconButton.tsx
│   │   │   └── FloatingActionButton.tsx
│   │   ├── cards/
│   │   │   ├── OrderCard.tsx
│   │   │   ├── ProductCard.tsx
│   │   │   ├── StatCard.tsx
│   │   │   └── CalendarDayCell.tsx
│   │   ├── forms/
│   │   │   ├── TextInput.tsx
│   │   │   ├── Dropdown.tsx
│   │   │   ├── DatePicker.tsx
│   │   │   ├── TimePicker.tsx
│   │   │   ├── Checkbox.tsx
│   │   │   └── RadioButton.tsx
│   │   ├── navigation/
│   │   │   ├── BottomTabBar.tsx
│   │   │   ├── TopNavigationBar.tsx
│   │   │   └── TabSelector.tsx
│   │   ├── feedback/
│   │   │   ├── Toast.tsx
│   │   │   ├── Modal.tsx
│   │   │   ├── BottomSheet.tsx
│   │   │   ├── Badge.tsx
│   │   │   ├── Skeleton.tsx
│   │   │   └── Spinner.tsx
│   │   └── decorative/
│   │       ├── FloralDecoration.tsx
│   │       ├── FloatingPetals.tsx
│   │       └── Divider.tsx
│   │
│   ├── screens/             # Screen components
│   │   ├── Home/
│   │   │   ├── HomeScreen.tsx
│   │   │   ├── OrderDetailsScreen.tsx
│   │   │   └── hooks/
│   │   ├── Calendar/
│   │   │   ├── CalendarMonthScreen.tsx
│   │   │   ├── CalendarDayScreen.tsx
│   │   │   └── NewOrderForm/
│   │   ├── Menu/
│   │   │   ├── MenuScreen.tsx
│   │   │   ├── ProductDetailScreen.tsx
│   │   │   └── ShareMenuSheet.tsx
│   │   ├── Reports/
│   │   │   ├── ReportsScreen.tsx
│   │   │   └── components/
│   │   └── Onboarding/
│   │       └── OnboardingScreen.tsx
│   │
│   ├── navigation/          # Navigation configuration
│   │   ├── RootNavigator.tsx
│   │   ├── TabNavigator.tsx
│   │   └── StackNavigator.tsx
│   │
│   ├── store/              # State management
│   │   ├── ordersStore.ts
│   │   ├── menuStore.ts
│   │   ├── analyticsStore.ts
│   │   └── appStore.ts
│   │
│   ├── services/           # Business logic & APIs
│   │   ├── orderService.ts
│   │   ├── menuService.ts
│   │   ├── analyticsService.ts
│   │   └── storageService.ts
│   │
│   ├── hooks/              # Custom React hooks
│   │   ├── useOrders.ts
│   │   ├── useSwipeGesture.ts
│   │   ├── useAnimatedValue.ts
│   │   └── useKeyboard.ts
│   │
│   ├── utils/              # Utility functions
│   │   ├── date.ts
│   │   ├── currency.ts
│   │   ├── validation.ts
│   │   └── formatters.ts
│   │
│   ├── theme/              # Design tokens & theming
│   │   ├── colors.ts
│   │   ├── typography.ts
│   │   ├── spacing.ts
│   │   ├── shadows.ts
│   │   └── animations.ts
│   │
│   ├── assets/             # Static assets
│   │   ├── fonts/
│   │   ├── images/
│   │   ├── icons/
│   │   └── illustrations/
│   │
│   └── types/              # TypeScript types
│       ├── order.ts
│       ├── product.ts
│       ├── customer.ts
│       └── analytics.ts
│
├── App.tsx
├── package.json
└── tsconfig.json
```

---

## Design Tokens Implementation

### `src/theme/colors.ts`

```typescript
export const colors = {
  // Primary palette
  cream: {
    base: '#FFF8F3',
    secondary: '#FFF5ED',
    surface: '#FFFBF7',
  },
  
  pink: {
    lightest: '#FFE8E8',
    light: '#FFC9C9',
    medium: '#FFB5B5',
    bold: '#FF9E9E',
  },
  
  rose: {
    muted: '#E8B4B8',
    deep: '#D4949A',
  },
  
  sage: {
    light: '#B8C9B4',
    medium: '#9BB096',
    deep: '#7A9475',
  },
  
  // Text
  text: {
    primary: '#5C3A2E',
    secondary: '#8B6E5F',
    tertiary: '#A68976',
  },
  
  // Semantic
  success: {
    main: '#9BB096',
    background: '#F0F5EF',
  },
  
  warning: {
    main: '#F4C896',
    background: '#FFF9F0',
  },
  
  error: {
    main: '#E8A5A5',
    background: '#FFF0F0',
  },
  
  info: {
    main: '#B8C9E8',
    background: '#F5F8FF',
  },
} as const;

export type Colors = typeof colors;
```

### `src/theme/typography.ts`

```typescript
export const typography = {
  fonts: {
    display: 'Playfair Display',
    body: 'Inter',
    accent: 'Cormorant Garamond',
  },
  
  sizes: {
    displayLarge: 32,
    h1: 28,
    h2: 22,
    h3: 18,
    bodyLarge: 16,
    bodyRegular: 14,
    bodySmall: 13,
    caption: 12,
    label: 12,
    button: 15,
  },
  
  weights: {
    regular: '400' as const,
    medium: '500' as const,
    semibold: '600' as const,
    bold: '700' as const,
  },
  
  lineHeights: {
    displayLarge: 40,
    h1: 36,
    h2: 30,
    h3: 26,
    bodyLarge: 24,
    bodyRegular: 22,
    bodySmall: 20,
    caption: 18,
    label: 16,
    button: 20,
  },
} as const;
```

### `src/theme/spacing.ts`

```typescript
export const spacing = {
  1: 4,
  2: 8,
  3: 12,
  4: 16,
  5: 20,
  6: 24,
  7: 32,
  8: 40,
  9: 48,
  10: 64,
} as const;
```

### `src/theme/shadows.ts`

```typescript
export const shadows = {
  level0: {
    shadowColor: '#5C3A2E',
    shadowOffset: { width: 0, height: 0 },
    shadowOpacity: 0,
    shadowRadius: 0,
    elevation: 0,
  },
  
  level1: {
    shadowColor: '#5C3A2E',
    shadowOffset: { width: 0, height: 2 },
    shadowOpacity: 0.06,
    shadowRadius: 8,
    elevation: 2,
  },
  
  level2: {
    shadowColor: '#5C3A2E',
    shadowOffset: { width: 0, height: 4 },
    shadowOpacity: 0.08,
    shadowRadius: 16,
    elevation: 4,
  },
  
  level3: {
    shadowColor: '#5C3A2E',
    shadowOffset: { width: 0, height: 8 },
    shadowOpacity: 0.10,
    shadowRadius: 24,
    elevation: 8,
  },
  
  level4: {
    shadowColor: '#5C3A2E',
    shadowOffset: { width: 0, height: 12 },
    shadowOpacity: 0.14,
    shadowRadius: 40,
    elevation: 12,
  },
} as const;
```

### `src/theme/animations.ts`

```typescript
export const animations = {
  timing: {
    instant: 100,
    fast: 150,
    medium: 250,
    slow: 400,
    verySlow: 600,
    extraSlow: 800,
  },
  
  easing: {
    standard: [0.4, 0.0, 0.2, 1] as const,
    easeOut: [0.0, 0.0, 0.2, 1] as const,
    easeIn: [0.4, 0.0, 1, 1] as const,
    easeInOut: [0.4, 0.0, 0.6, 1] as const,
    bounce: [0.68, -0.55, 0.265, 1.55] as const,
    spring: [0.175, 0.885, 0.32, 1.275] as const,
  },
} as const;
```

---

## Core Component Examples

### Primary Button Component

```typescript
// src/components/buttons/PrimaryButton.tsx

import React from 'react';
import { TouchableOpacity, Text, StyleSheet, ActivityIndicator } from 'react-native';
import Animated, {
  useAnimatedStyle,
  useSharedValue,
  withSpring,
  withTiming,
} from 'react-native-reanimated';
import { colors, typography, spacing, shadows } from '../../theme';

interface PrimaryButtonProps {
  label: string;
  onPress: () => void;
  loading?: boolean;
  disabled?: boolean;
  icon?: React.ReactNode;
}

const AnimatedTouchable = Animated.createAnimatedComponent(TouchableOpacity);

export const PrimaryButton: React.FC<PrimaryButtonProps> = ({
  label,
  onPress,
  loading = false,
  disabled = false,
  icon,
}) => {
  const scale = useSharedValue(1);
  
  const animatedStyle = useAnimatedStyle(() => ({
    transform: [{ scale: scale.value }],
  }));
  
  const handlePressIn = () => {
    scale.value = withSpring(0.96, {
      damping: 15,
      stiffness: 150,
    });
  };
  
  const handlePressOut = () => {
    scale.value = withTiming(1, { duration: 200 });
  };
  
  return (
    <AnimatedTouchable
      style={[
        styles.button,
        animatedStyle,
        disabled && styles.disabled,
      ]}
      onPress={onPress}
      onPressIn={handlePressIn}
      onPressOut={handlePressOut}
      disabled={disabled || loading}
      activeOpacity={0.9}
    >
      {loading ? (
        <ActivityIndicator color={colors.text.primary} />
      ) : (
        <>
          {icon}
          <Text style={styles.label}>{label}</Text>
        </>
      )}
    </AnimatedTouchable>
  );
};

const styles = StyleSheet.create({
  button: {
    flexDirection: 'row',
    alignItems: 'center',
    justifyContent: 'center',
    minHeight: 48,
    paddingHorizontal: spacing[6],
    paddingVertical: spacing[3],
    borderRadius: 12,
    backgroundColor: colors.pink.medium,
    ...shadows.level1,
    gap: spacing[2],
  },
  
  label: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.button,
    fontWeight: typography.weights.medium,
    color: colors.text.primary,
    letterSpacing: 0.2,
  },
  
  disabled: {
    backgroundColor: colors.text.tertiary,
    opacity: 0.6,
  },
});
```

### Order Card Component

```typescript
// src/components/cards/OrderCard.tsx

import React from 'react';
import { View, Text, StyleSheet, TouchableOpacity } from 'react-native';
import { Swipeable } from 'react-native-gesture-handler';
import Animated, { FadeOut, SlideOutRight } from 'react-native-reanimated';
import { colors, typography, spacing, shadows } from '../../theme';
import { Order } from '../../types/order';

interface OrderCardProps {
  order: Order;
  onPress: () => void;
  onComplete: () => void;
  onEdit: () => void;
  onCall: () => void;
}

export const OrderCard: React.FC<OrderCardProps> = ({
  order,
  onPress,
  onComplete,
  onEdit,
  onCall,
}) => {
  const renderLeftActions = () => (
    <View style={styles.leftActions}>
      <TouchableOpacity
        style={[styles.actionButton, styles.callButton]}
        onPress={onCall}
      >
        <Text style={styles.actionIcon}>📞</Text>
        <Text style={styles.actionText}>CALL</Text>
      </TouchableOpacity>
    </View>
  );
  
  const renderRightActions = () => (
    <View style={styles.rightActions}>
      <TouchableOpacity
        style={[styles.actionButton, styles.completeButton]}
        onPress={onComplete}
      >
        <Text style={styles.actionIcon}>✓</Text>
        <Text style={styles.actionText}>COM</Text>
      </TouchableOpacity>
      
      <TouchableOpacity
        style={[styles.actionButton, styles.editButton]}
        onPress={onEdit}
      >
        <Text style={styles.actionIcon}>✏️</Text>
        <Text style={styles.actionText}>EDIT</Text>
      </TouchableOpacity>
    </View>
  );
  
  const statusColor = getStatusColor(order.status);
  
  return (
    <Swipeable
      renderLeftActions={renderLeftActions}
      renderRightActions={renderRightActions}
      overshootLeft={false}
      overshootRight={false}
    >
      <Animated.View
        exiting={SlideOutRight.duration(500)}
      >
        <TouchableOpacity
          style={[
            styles.card,
            { borderLeftColor: statusColor },
          ]}
          onPress={onPress}
          activeOpacity={0.8}
        >
          {/* Floral decoration */}
          <View style={styles.decoration}>
            <Text style={styles.floralEmoji}>🌸</Text>
          </View>
          
          {/* Header */}
          <View style={styles.header}>
            <View style={styles.headerLeft}>
              <Text style={styles.platformIcon}>
                {getPlatformIcon(order.platform)}
              </Text>
              <Text style={styles.customerName}>
                {order.customerName}
              </Text>
            </View>
          </View>
          
          {/* Meta info */}
          <Text style={styles.meta}>
            #{order.id} · {order.time} {order.type}
          </Text>
          
          {/* Items */}
          <View style={styles.items}>
            {order.items.slice(0, 3).map((item, index) => (
              <Text key={index} style={styles.item}>
                • {item.name}
              </Text>
            ))}
            {order.items.length > 3 && (
              <Text style={styles.item}>
                ...and {order.items.length - 3} more
              </Text>
            )}
          </View>
          
          {/* Footer */}
          <View style={styles.footer}>
            <View style={[styles.badge, getStatusBadgeStyle(order.status)]}>
              <Text style={[styles.badgeText, getStatusTextStyle(order.status)]}>
                {order.status.toUpperCase()}
              </Text>
            </View>
            
            <Text style={styles.price}>₹{order.total}</Text>
            
            <TouchableOpacity style={styles.moreButton}>
              <Text style={styles.moreIcon}>⋯</Text>
            </TouchableOpacity>
          </View>
        </TouchableOpacity>
      </Animated.View>
    </Swipeable>
  );
};

const styles = StyleSheet.create({
  card: {
    backgroundColor: colors.cream.surface,
    borderWidth: 1,
    borderColor: 'rgba(232, 180, 184, 0.3)',
    borderLeftWidth: 3,
    borderRadius: 16,
    padding: spacing[5],
    marginHorizontal: spacing[6],
    marginBottom: spacing[3],
    ...shadows.level1,
  },
  
  decoration: {
    position: 'absolute',
    top: spacing[5],
    right: spacing[5],
    opacity: 0.25,
  },
  
  floralEmoji: {
    fontSize: 32,
  },
  
  header: {
    flexDirection: 'row',
    justifyContent: 'space-between',
    alignItems: 'center',
    marginBottom: spacing[2],
  },
  
  headerLeft: {
    flexDirection: 'row',
    alignItems: 'center',
    gap: spacing[2],
  },
  
  platformIcon: {
    fontSize: 20,
  },
  
  customerName: {
    fontFamily: typography.fonts.display,
    fontSize: typography.sizes.h3,
    fontWeight: typography.weights.semibold,
    color: colors.text.primary,
  },
  
  meta: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.caption,
    color: colors.text.tertiary,
    marginBottom: spacing[3],
  },
  
  items: {
    gap: spacing[1],
    marginBottom: spacing[4],
  },
  
  item: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.bodyRegular,
    color: colors.text.primary,
    lineHeight: typography.lineHeights.bodyRegular,
  },
  
  footer: {
    flexDirection: 'row',
    alignItems: 'center',
    gap: spacing[3],
  },
  
  badge: {
    paddingHorizontal: spacing[2],
    paddingVertical: spacing[1],
    borderRadius: 8,
  },
  
  badgeText: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.caption,
    fontWeight: typography.weights.semibold,
    letterSpacing: 0.5,
  },
  
  price: {
    flex: 1,
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.bodyLarge,
    fontWeight: typography.weights.bold,
    color: colors.text.primary,
  },
  
  moreButton: {
    width: 32,
    height: 32,
    alignItems: 'center',
    justifyContent: 'center',
  },
  
  moreIcon: {
    fontSize: 20,
    color: colors.text.secondary,
  },
  
  // Swipe actions
  leftActions: {
    flexDirection: 'row',
    marginRight: spacing[3],
  },
  
  rightActions: {
    flexDirection: 'row',
    marginLeft: spacing[3],
  },
  
  actionButton: {
    width: 80,
    justifyContent: 'center',
    alignItems: 'center',
    borderRadius: 12,
  },
  
  callButton: {
    backgroundColor: '#82C9C3',
  },
  
  completeButton: {
    backgroundColor: colors.sage.medium,
  },
  
  editButton: {
    backgroundColor: colors.info.main,
    marginLeft: spacing[2],
  },
  
  actionIcon: {
    fontSize: 20,
    marginBottom: spacing[1],
  },
  
  actionText: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.caption,
    fontWeight: typography.weights.semibold,
    color: '#FFFFFF',
    letterSpacing: 0.5,
  },
});

// Helper functions
const getPlatformIcon = (platform: string) => {
  const icons: Record<string, string> = {
    instagram: '📱',
    whatsapp: '💬',
    phone: '📞',
    walkin: '🚶',
    repeat: '💝',
  };
  return icons[platform.toLowerCase()] || '📋';
};

const getStatusColor = (status: string) => {
  const colors: Record<string, string> = {
    urgent: '#E8A5A5',
    today: '#F4C896',
    tomorrow: '#B8C9B4',
    future: '#B8C9E8',
  };
  return colors[status.toLowerCase()] || colors.future;
};

const getStatusBadgeStyle = (status: string) => {
  const styles: Record<string, object> = {
    pending: { backgroundColor: '#FFF9F0' },
    inprogress: { backgroundColor: '#F5F8FF' },
    completed: { backgroundColor: '#F0F5EF' },
    urgent: { backgroundColor: '#FFF0F0' },
  };
  return styles[status.toLowerCase()] || styles.pending;
};

const getStatusTextStyle = (status: string) => {
  const styles: Record<string, object> = {
    pending: { color: '#B8874E' },
    inprogress: { color: '#6B8BB8' },
    completed: { color: '#7A9475' },
    urgent: { color: '#C87878' },
  };
  return styles[status.toLowerCase()] || styles.pending;
};
```

### Text Input Component

```typescript
// src/components/forms/TextInput.tsx

import React, { useState } from 'react';
import { View, TextInput as RNTextInput, Text, StyleSheet, Animated } from 'react-native';
import { colors, typography, spacing } from '../../theme';

interface TextInputProps {
  label: string;
  value: string;
  onChangeText: (text: string) => void;
  placeholder?: string;
  error?: string;
  helperText?: string;
  multiline?: boolean;
  secureTextEntry?: boolean;
  keyboardType?: 'default' | 'email-address' | 'numeric' | 'phone-pad';
}

export const TextInput: React.FC<TextInputProps> = ({
  label,
  value,
  onChangeText,
  placeholder,
  error,
  helperText,
  multiline = false,
  secureTextEntry = false,
  keyboardType = 'default',
}) => {
  const [isFocused, setIsFocused] = useState(false);
  const shakeAnimation = new Animated.Value(0);
  
  React.useEffect(() => {
    if (error) {
      // Shake animation on error
      Animated.sequence([
        Animated.timing(shakeAnimation, { toValue: -4, duration: 50, useNativeDriver: true }),
        Animated.timing(shakeAnimation, { toValue: 4, duration: 50, useNativeDriver: true }),
        Animated.timing(shakeAnimation, { toValue: -4, duration: 50, useNativeDriver: true }),
        Animated.timing(shakeAnimation, { toValue: 4, duration: 50, useNativeDriver: true }),
        Animated.timing(shakeAnimation, { toValue: 0, duration: 50, useNativeDriver: true }),
      ]).start();
    }
  }, [error]);
  
  return (
    <Animated.View
      style={[
        styles.container,
        { transform: [{ translateX: shakeAnimation }] },
      ]}
    >
      <Text style={styles.label}>{label}</Text>
      
      <View style={[
        styles.inputContainer,
        isFocused && styles.inputFocused,
        error && styles.inputError,
      ]}>
        <RNTextInput
          style={[
            styles.input,
            multiline && styles.inputMultiline,
          ]}
          value={value}
          onChangeText={onChangeText}
          placeholder={placeholder}
          placeholderTextColor={colors.text.tertiary}
          onFocus={() => setIsFocused(true)}
          onBlur={() => setIsFocused(false)}
          multiline={multiline}
          secureTextEntry={secureTextEntry}
          keyboardType={keyboardType}
        />
      </View>
      
      {(error || helperText) && (
        <Text style={[styles.helperText, error && styles.errorText]}>
          {error || helperText}
        </Text>
      )}
    </Animated.View>
  );
};

const styles = StyleSheet.create({
  container: {
    marginBottom: spacing[5],
  },
  
  label: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.bodySmall,
    fontWeight: typography.weights.medium,
    color: colors.text.primary,
    marginBottom: spacing[2],
  },
  
  inputContainer: {
    backgroundColor: '#FFFFFF',
    borderWidth: 1.5,
    borderColor: '#E8D4C9',
    borderRadius: 12,
    paddingHorizontal: spacing[4],
    paddingVertical: spacing[3],
  },
  
  inputFocused: {
    borderColor: colors.pink.medium,
    borderWidth: 2,
    shadowColor: colors.pink.medium,
    shadowOffset: { width: 0, height: 0 },
    shadowOpacity: 0.15,
    shadowRadius: 4,
    elevation: 2,
  },
  
  inputError: {
    borderColor: colors.error.main,
    borderWidth: 2,
    backgroundColor: colors.error.background,
  },
  
  input: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.bodyRegular,
    color: colors.text.primary,
    padding: 0, // Reset default padding
    minHeight: 20,
  },
  
  inputMultiline: {
    minHeight: 120,
    textAlignVertical: 'top',
  },
  
  helperText: {
    fontFamily: typography.fonts.body,
    fontSize: typography.sizes.caption,
    color: colors.text.secondary,
    marginTop: spacing[2],
  },
  
  errorText: {
    color: colors.error.main,
  },
});
```

---

## State Management Example (Zustand)

```typescript
// src/store/ordersStore.ts

import { create } from 'zustand';
import { persist, createJSONStorage } from 'zustand/middleware';
import AsyncStorage from '@react-native-async-storage/async-storage';
import { Order, OrderStatus } from '../types/order';

interface OrdersState {
  orders: Order[];
  loading: boolean;
  error: string | null;
  
  // Actions
  fetchOrders: () => Promise<void>;
  addOrder: (order: Omit<Order, 'id' | 'createdAt'>) => Promise<void>;
  updateOrder: (id: string, updates: Partial<Order>) => Promise<void>;
  deleteOrder: (id: string) => Promise<void>;
  completeOrder: (id: string) => Promise<void>;
  
  // Selectors
  getOrdersByDate: (date: Date) => Order[];
  getTodaysOrders: () => Order[];
  getTomorrowsOrders: () => Order[];
}

export const useOrdersStore = create<OrdersState>()(
  persist(
    (set, get) => ({
      orders: [],
      loading: false,
      error: null,
      
      fetchOrders: async () => {
        set({ loading: true, error: null });
        try {
          // TODO: Replace with actual API call
          const response = await fetch('/api/orders');
          const orders = await response.json();
          set({ orders, loading: false });
        } catch (error) {
          set({ error: (error as Error).message, loading: false });
        }
      },
      
      addOrder: async (orderData) => {
        set({ loading: true, error: null });
        try {
          const newOrder: Order = {
            ...orderData,
            id: generateOrderId(),
            createdAt: new Date().toISOString(),
            status: 'pending' as OrderStatus,
          };
          
          // TODO: Replace with actual API call
          // await fetch('/api/orders', { method: 'POST', body: JSON.stringify(newOrder) });
          
          set((state) => ({
            orders: [...state.orders, newOrder],
            loading: false,
          }));
        } catch (error) {
          set({ error: (error as Error).message, loading: false });
        }
      },
      
      updateOrder: async (id, updates) => {
        set({ loading: true, error: null });
        try {
          // TODO: Replace with actual API call
          // await fetch(`/api/orders/${id}`, { method: 'PATCH', body: JSON.stringify(updates) });
          
          set((state) => ({
            orders: state.orders.map((order) =>
              order.id === id ? { ...order, ...updates } : order
            ),
            loading: false,
          }));
        } catch (error) {
          set({ error: (error as Error).message, loading: false });
        }
      },
      
      deleteOrder: async (id) => {
        set({ loading: true, error: null });
        try {
          // TODO: Replace with actual API call
          // await fetch(`/api/orders/${id}`, { method: 'DELETE' });
          
          set((state) => ({
            orders: state.orders.filter((order) => order.id !== id),
            loading: false,
          }));
        } catch (error) {
          set({ error: (error as Error).message, loading: false });
        }
      },
      
      completeOrder: async (id) => {
        await get().updateOrder(id, {
          status: 'completed' as OrderStatus,
          completedAt: new Date().toISOString(),
        });
      },
      
      // Selectors
      getOrdersByDate: (date) => {
        const dateString = date.toISOString().split('T')[0];
        return get().orders.filter((order) => {
          const orderDate = new Date(order.orderDate).toISOString().split('T')[0];
          return orderDate === dateString;
        });
      },
      
      getTodaysOrders: () => {
        return get().getOrdersByDate(new Date());
      },
      
      getTomorrowsOrders: () => {
        const tomorrow = new Date();
        tomorrow.setDate(tomorrow.getDate() + 1);
        return get().getOrdersByDate(tomorrow);
      },
    }),
    {
      name: 'orders-storage',
      storage: createJSONStorage(() => AsyncStorage),
    }
  )
);

// Helper function
const generateOrderId = (): string => {
  return `ORD-${Date.now().toString().slice(-8)}`;
};
```

---

## Custom Hooks Examples

### useSwipeGesture Hook

```typescript
// src/hooks/useSwipeGesture.ts

import { useCallback } from 'react';
import { GestureResponderEvent } from 'react-native';
import { useSharedValue, runOnJS, withTiming } from 'react-native-reanimated';

interface SwipeGestureOptions {
  threshold?: number;
  onSwipeLeft?: () => void;
  onSwipeRight?: () => void;
}

export const useSwipeGesture = ({
  threshold = 80,
  onSwipeLeft,
  onSwipeRight,
}: SwipeGestureOptions) => {
  const translateX = useSharedValue(0);
  const startX = useSharedValue(0);
  
  const handleStart = useCallback((event: GestureResponderEvent) => {
    startX.value = event.nativeEvent.pageX;
  }, []);
  
  const handleMove = useCallback((event: GestureResponderEvent) => {
    const deltaX = event.nativeEvent.pageX - startX.value;
    translateX.value = deltaX;
  }, []);
  
  const handleEnd = useCallback(() => {
    const delta = translateX.value;
    
    if (Math.abs(delta) > threshold) {
      if (delta < 0 && onSwipeLeft) {
        runOnJS(onSwipeLeft)();
      } else if (delta > 0 && onSwipeRight) {
        runOnJS(onSwipeRight)();
      }
    }
    
    // Reset position
    translateX.value = withTiming(0, { duration: 300 });
  }, [threshold, onSwipeLeft, onSwipeRight]);
  
  return {
    translateX,
    handleStart,
    handleMove,
    handleEnd,
  };
};
```

---

## API Service Example

```typescript
// src/services/orderService.ts

import AsyncStorage from '@react-native-async-storage/async-storage';
import { Order } from '../types/order';

const STORAGE_KEY = '@orders';
const API_BASE_URL = process.env.API_URL || 'https://api.pastelbakery.com';

export class OrderService {
  // Local storage methods (offline-first)
  static async getLocalOrders(): Promise<Order[]> {
    try {
      const ordersJson = await AsyncStorage.getItem(STORAGE_KEY);
      return ordersJson ? JSON.parse(ordersJson) : [];
    } catch (error) {
      console.error('Error reading local orders:', error);
      return [];
    }
  }
  
  static async saveLocalOrders(orders: Order[]): Promise<void> {
    try {
      await AsyncStorage.setItem(STORAGE_KEY, JSON.stringify(orders));
    } catch (error) {
      console.error('Error saving local orders:', error);
    }
  }
  
  // API methods (cloud sync)
  static async fetchOrders(): Promise<Order[]> {
    try {
      const response = await fetch(`${API_BASE_URL}/orders`, {
        headers: {
          'Content-Type': 'application/json',
          // Add auth headers here
        },
      });
      
      if (!response.ok) {
        throw new Error('Failed to fetch orders');
      }
      
      const orders = await response.json();
      
      // Cache locally
      await this.saveLocalOrders(orders);
      
      return orders;
    } catch (error) {
      console.error('Error fetching orders from API:', error);
      
      // Fallback to local cache
      return await this.getLocalOrders();
    }
  }
  
  static async createOrder(order: Omit<Order, 'id' | 'createdAt'>): Promise<Order> {
    const newOrder: Order = {
      ...order,
      id: this.generateOrderId(),
      createdAt: new Date().toISOString(),
      status: 'pending',
    };
    
    try {
      const response = await fetch(`${API_BASE_URL}/orders`, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
        },
        body: JSON.stringify(newOrder),
      });
      
      if (!response.ok) {
        throw new Error('Failed to create order');
      }
      
      // Update local cache
      const localOrders = await this.getLocalOrders();
      await this.saveLocalOrders([...localOrders, newOrder]);
      
      return newOrder;
    } catch (error) {
      console.error('Error creating order:', error);
      
      // Save locally for sync later
      const localOrders = await this.getLocalOrders();
      await this.saveLocalOrders([...localOrders, newOrder]);
      
      return newOrder;
    }
  }
  
  private static generateOrderId(): string {
    return `ORD-${Date.now().toString().slice(-8)}`;
  }
}
```

---

## Testing Example

```typescript
// src/components/buttons/__tests__/PrimaryButton.test.tsx

import React from 'react';
import { render, fireEvent } from '@testing-library/react-native';
import { PrimaryButton } from '../PrimaryButton';

describe('PrimaryButton', () => {
  it('renders correctly', () => {
    const { getByText } = render(
      <PrimaryButton label="Test Button" onPress={() => {}} />
    );
    
    expect(getByText('Test Button')).toBeTruthy();
  });
  
  it('calls onPress when tapped', () => {
    const onPressMock = jest.fn();
    const { getByText } = render(
      <PrimaryButton label="Test Button" onPress={onPressMock} />
    );
    
    fireEvent.press(getByText('Test Button'));
    
    expect(onPressMock).toHaveBeenCalledTimes(1);
  });
  
  it('shows loading state', () => {
    const { getByTestId } = render(
      <PrimaryButton label="Test Button" onPress={() => {}} loading />
    );
    
    expect(getByTestId('activity-indicator')).toBeTruthy();
  });
  
  it('disables when disabled prop is true', () => {
    const onPressMock = jest.fn();
    const { getByText } = render(
      <PrimaryButton label="Test Button" onPress={onPressMock} disabled />
    );
    
    fireEvent.press(getByText('Test Button'));
    
    expect(onPressMock).not.toHaveBeenCalled();
  });
});
```

---

This technical implementation guide provides a solid foundation for building the Pastel Bakery Co app with clean, maintainable code that matches the elegant design aesthetic.
