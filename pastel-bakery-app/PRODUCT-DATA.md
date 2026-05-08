# Pastel Bakery Co - Complete Product Data

## Product Catalog (From Menu)

This document contains all product data extracted from the uploaded bakery menu, structured for easy implementation in the app.

---

## Product Categories

1. **Vanilla Cakes** 🌸
2. **Chocolate Cakes** 🍫
3. **Brownies** 💝
4. **Cheesecakes** 🧈

---

## 1. Vanilla Cakes

### Pineapple 💝 (Most Popular)
```json
{
  "id": "vc-001",
  "name": "Pineapple",
  "category": "Vanilla Cake",
  "popular": true,
  "sizes": [
    {
      "size": "6 inch",
      "price": 850,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1500,
      "weight": "1100-1200g"
    }
  ],
  "description": "Moist vanilla sponge with fresh pineapple chunks and whipped cream"
}
```

### Blueberry
```json
{
  "id": "vc-002",
  "name": "Blueberry",
  "category": "Vanilla Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 850,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1500,
      "weight": "1100-1200g"
    }
  ],
  "description": "Light vanilla cake with fresh blueberries"
}
```

### Caramel Butterscotch 💝 (Most Popular)
```json
{
  "id": "vc-003",
  "name": "Caramel Butterscotch",
  "category": "Vanilla Cake",
  "popular": true,
  "sizes": [
    {
      "size": "6 inch",
      "price": 875,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1550,
      "weight": "1100-1200g"
    }
  ],
  "description": "Buttery caramel vanilla cake with butterscotch drizzle"
}
```

### Rasmalai
```json
{
  "id": "vc-004",
  "name": "Rasmalai",
  "category": "Vanilla Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 950,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1650,
      "weight": "1100-1200g"
    }
  ],
  "description": "Traditional Indian milk cake with saffron and cardamom"
}
```

### Seasonal (Mango/Strawberry)
```json
{
  "id": "vc-005",
  "name": "Seasonal",
  "category": "Vanilla Cake",
  "popular": false,
  "seasonal": true,
  "variants": ["Mango", "Strawberry"],
  "sizes": [
    {
      "size": "6 inch",
      "price": 950,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1650,
      "weight": "1100-1200g"
    }
  ],
  "description": "Fresh seasonal fruit vanilla cake"
}
```

### Fresh Fruit
```json
{
  "id": "vc-006",
  "name": "Fresh Fruit",
  "category": "Vanilla Cake",
  "popular": false,
  "sizes": [
    {
      "size": "8 inch",
      "price": 1850,
      "weight": "1100-1200g",
      "note": "8 inch only"
    }
  ],
  "description": "Vanilla cake topped with assorted fresh fruits"
}
```

---

## 2. Chocolate Cakes

### Classic Truffle
```json
{
  "id": "cc-001",
  "name": "Classic Truffle",
  "category": "Chocolate Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 850,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1550,
      "weight": "1100-1200g"
    }
  ],
  "description": "Rich chocolate sponge with chocolate ganache"
}
```

### Cookies & Cream
```json
{
  "id": "cc-002",
  "name": "Cookies & Cream",
  "category": "Chocolate Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 950,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1650,
      "weight": "1100-1200g"
    }
  ],
  "description": "Chocolate cake with crushed Oreo cookies and cream"
}
```

### Honey Roasted Almond
```json
{
  "id": "cc-003",
  "name": "Honey Roasted Almond",
  "category": "Chocolate Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 950,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1650,
      "weight": "1100-1200g"
    }
  ],
  "description": "Chocolate cake with honey-roasted almond crunch"
}
```

### Hazelnut Crunch 💝 (Most Popular)
```json
{
  "id": "cc-004",
  "name": "Hazelnut Crunch",
  "category": "Chocolate Cake",
  "popular": true,
  "sizes": [
    {
      "size": "6 inch",
      "price": 975,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1675,
      "weight": "1100-1200g"
    }
  ],
  "description": "Chocolate cake with crunchy hazelnut praline"
}
```

### Ferrero
```json
{
  "id": "cc-005",
  "name": "Ferrero",
  "category": "Chocolate Cake",
  "popular": false,
  "sizes": [
    {
      "size": "6 inch",
      "price": 975,
      "weight": "600-650g"
    },
    {
      "size": "8 inch",
      "price": 1675,
      "weight": "1100-1200g"
    }
  ],
  "description": "Chocolate cake inspired by Ferrero Rocher with hazelnut"
}
```

---

## 3. Brownies

### Brownie Box 💝 (Most Popular)
```json
{
  "id": "br-001",
  "name": "Brownie Box",
  "category": "Brownies",
  "popular": true,
  "sizes": [
    {
      "size": "16 pieces",
      "price": 875,
      "weight": "650g"
    }
  ],
  "toppingOptions": [
    "Hazelnut",
    "Roasted Almond",
    "Walnut",
    "Kit-Kat",
    "Oreo",
    "Chocolate Chip"
  ],
  "customization": "Pick any 2 or 4 toppings",
  "description": "Fudgy chocolate brownies with your choice of toppings"
}
```

---

## 4. Cheesecakes

### Blueberry/Strawberry 💝 (Most Popular)
```json
{
  "id": "ch-001",
  "name": "Blueberry/Strawberry",
  "category": "Cheesecake",
  "popular": true,
  "variants": ["Blueberry", "Strawberry"],
  "sizes": [
    {
      "size": "900g slab",
      "price": 1400,
      "weight": "900g"
    }
  ],
  "description": "Creamy cheesecake with fresh berry topping"
}
```

### Biscoff/Nutella
```json
{
  "id": "ch-002",
  "name": "Biscoff/Nutella",
  "category": "Cheesecake",
  "popular": false,
  "variants": ["Biscoff", "Nutella"],
  "sizes": [
    {
      "size": "900g slab",
      "price": 1550,
      "weight": "900g"
    }
  ],
  "description": "Rich cheesecake with Biscoff cookie or Nutella swirl"
}
```

---

## Complete Product Array (JSON)

```json
{
  "products": [
    {
      "id": "vc-001",
      "name": "Pineapple",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": true,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 850, "weight": "600-650g" },
        { "size": "8 inch", "price": 1500, "weight": "1100-1200g" }
      ],
      "description": "Moist vanilla sponge with fresh pineapple chunks and whipped cream",
      "image": null,
      "customizable": true
    },
    {
      "id": "vc-002",
      "name": "Blueberry",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 850, "weight": "600-650g" },
        { "size": "8 inch", "price": 1500, "weight": "1100-1200g" }
      ],
      "description": "Light vanilla cake with fresh blueberries",
      "image": null,
      "customizable": true
    },
    {
      "id": "vc-003",
      "name": "Caramel Butterscotch",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": true,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 875, "weight": "600-650g" },
        { "size": "8 inch", "price": 1550, "weight": "1100-1200g" }
      ],
      "description": "Buttery caramel vanilla cake with butterscotch drizzle",
      "image": null,
      "customizable": true
    },
    {
      "id": "vc-004",
      "name": "Rasmalai",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 950, "weight": "600-650g" },
        { "size": "8 inch", "price": 1650, "weight": "1100-1200g" }
      ],
      "description": "Traditional Indian milk cake with saffron and cardamom",
      "image": null,
      "customizable": true
    },
    {
      "id": "vc-005",
      "name": "Seasonal (Mango/Strawberry)",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": false,
      "seasonal": true,
      "variants": ["Mango", "Strawberry"],
      "sizes": [
        { "size": "6 inch", "price": 950, "weight": "600-650g" },
        { "size": "8 inch", "price": 1650, "weight": "1100-1200g" }
      ],
      "description": "Fresh seasonal fruit vanilla cake",
      "image": null,
      "customizable": true
    },
    {
      "id": "vc-006",
      "name": "Fresh Fruit",
      "category": "Vanilla Cake",
      "categoryIcon": "🌸",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "8 inch", "price": 1850, "weight": "1100-1200g" }
      ],
      "description": "Vanilla cake topped with assorted fresh fruits",
      "image": null,
      "customizable": true,
      "note": "8 inch only"
    },
    {
      "id": "cc-001",
      "name": "Classic Truffle",
      "category": "Chocolate Cake",
      "categoryIcon": "🍫",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 850, "weight": "600-650g" },
        { "size": "8 inch", "price": 1550, "weight": "1100-1200g" }
      ],
      "description": "Rich chocolate sponge with chocolate ganache",
      "image": null,
      "customizable": true
    },
    {
      "id": "cc-002",
      "name": "Cookies & Cream",
      "category": "Chocolate Cake",
      "categoryIcon": "🍫",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 950, "weight": "600-650g" },
        { "size": "8 inch", "price": 1650, "weight": "1100-1200g" }
      ],
      "description": "Chocolate cake with crushed Oreo cookies and cream",
      "image": null,
      "customizable": true
    },
    {
      "id": "cc-003",
      "name": "Honey Roasted Almond",
      "category": "Chocolate Cake",
      "categoryIcon": "🍫",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 950, "weight": "600-650g" },
        { "size": "8 inch", "price": 1650, "weight": "1100-1200g" }
      ],
      "description": "Chocolate cake with honey-roasted almond crunch",
      "image": null,
      "customizable": true
    },
    {
      "id": "cc-004",
      "name": "Hazelnut Crunch",
      "category": "Chocolate Cake",
      "categoryIcon": "🍫",
      "popular": true,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 975, "weight": "600-650g" },
        { "size": "8 inch", "price": 1675, "weight": "1100-1200g" }
      ],
      "description": "Chocolate cake with crunchy hazelnut praline",
      "image": null,
      "customizable": true
    },
    {
      "id": "cc-005",
      "name": "Ferrero",
      "category": "Chocolate Cake",
      "categoryIcon": "🍫",
      "popular": false,
      "seasonal": false,
      "sizes": [
        { "size": "6 inch", "price": 975, "weight": "600-650g" },
        { "size": "8 inch", "price": 1675, "weight": "1100-1200g" }
      ],
      "description": "Chocolate cake inspired by Ferrero Rocher with hazelnut",
      "image": null,
      "customizable": true
    },
    {
      "id": "br-001",
      "name": "Brownie Box",
      "category": "Brownies",
      "categoryIcon": "💝",
      "popular": true,
      "seasonal": false,
      "sizes": [
        { "size": "16 pieces", "price": 875, "weight": "650g" }
      ],
      "description": "Fudgy chocolate brownies with your choice of toppings",
      "image": null,
      "customizable": true,
      "toppingOptions": [
        "Hazelnut",
        "Roasted Almond",
        "Walnut",
        "Kit-Kat",
        "Oreo",
        "Chocolate Chip"
      ],
      "customizationNote": "Pick any 2 or 4 toppings"
    },
    {
      "id": "ch-001",
      "name": "Blueberry/Strawberry",
      "category": "Cheesecake",
      "categoryIcon": "🧈",
      "popular": true,
      "seasonal": false,
      "variants": ["Blueberry", "Strawberry"],
      "sizes": [
        { "size": "900g slab", "price": 1400, "weight": "900g" }
      ],
      "description": "Creamy cheesecake with fresh berry topping",
      "image": null,
      "customizable": false
    },
    {
      "id": "ch-002",
      "name": "Biscoff/Nutella",
      "category": "Cheesecake",
      "categoryIcon": "🧈",
      "popular": false,
      "seasonal": false,
      "variants": ["Biscoff", "Nutella"],
      "sizes": [
        { "size": "900g slab", "price": 1550, "weight": "900g" }
      ],
      "description": "Rich cheesecake with Biscoff cookie or Nutella swirl",
      "image": null,
      "customizable": false
    }
  ],
  "categories": [
    {
      "id": "vanilla-cakes",
      "name": "Vanilla Cakes",
      "icon": "🌸",
      "description": "Our signature collection",
      "productCount": 6
    },
    {
      "id": "chocolate-cakes",
      "name": "Chocolate Cakes",
      "icon": "🍫",
      "description": "Rich and indulgent",
      "productCount": 5
    },
    {
      "id": "brownies",
      "name": "Brownies",
      "icon": "💝",
      "description": "Fudgy and delicious",
      "productCount": 1
    },
    {
      "id": "cheesecakes",
      "name": "Cheesecakes",
      "icon": "🧈",
      "description": "Creamy perfection",
      "productCount": 2
    }
  ]
}
```

---

## Product Statistics

### Total Products: 14
- Vanilla Cakes: 6
- Chocolate Cakes: 5
- Brownies: 1 (with 6 topping options)
- Cheesecakes: 2

### Popular Products (6 total)
1. Pineapple Vanilla Cake
2. Caramel Butterscotch Vanilla Cake
3. Hazelnut Crunch Chocolate Cake
4. Brownie Box
5. Blueberry/Strawberry Cheesecake

### Price Range
- **Lowest:** ₹850 (6" Pineapple, 6" Blueberry, 6" Classic Truffle)
- **Highest:** ₹1850 (8" Fresh Fruit)
- **Average:** ₹1,200 approx

### Size Options
- **6 inch:** 600-650g (11 products)
- **8 inch:** 1100-1200g (11 products)
- **16 pieces:** 650g (1 product - Brownies)
- **900g slab:** (2 products - Cheesecakes)

---

## Customization Options

### All Cakes
- Custom message on cake
- Color preferences for frosting
- Delivery/pickup timing

### Brownies Specific
- Pick 2 or 4 toppings from:
  - Hazelnut
  - Roasted Almond
  - Walnut
  - Kit-Kat
  - Oreo
  - Chocolate Chip

### Seasonal Products
- Mango (Summer)
- Strawberry (Winter)

---

## TypeScript Types

```typescript
// Product Types
export interface Product {
  id: string;
  name: string;
  category: 'Vanilla Cake' | 'Chocolate Cake' | 'Brownies' | 'Cheesecake';
  categoryIcon: string;
  popular: boolean;
  seasonal: boolean;
  variants?: string[];
  sizes: ProductSize[];
  description: string;
  image: string | null;
  customizable: boolean;
  toppingOptions?: string[];
  customizationNote?: string;
  note?: string;
}

export interface ProductSize {
  size: string;
  price: number;
  weight: string;
}

export interface Category {
  id: string;
  name: string;
  icon: string;
  description: string;
  productCount: number;
}

// Order Item Type
export interface OrderItem {
  productId: string;
  productName: string;
  size: string;
  quantity: number;
  price: number;
  customization?: {
    message?: string;
    toppings?: string[];
    variant?: string;
    notes?: string;
  };
}
```

---

## Implementation Notes

### Database Schema
```sql
CREATE TABLE products (
  id VARCHAR(10) PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  category VARCHAR(50) NOT NULL,
  category_icon VARCHAR(10),
  popular BOOLEAN DEFAULT false,
  seasonal BOOLEAN DEFAULT false,
  description TEXT,
  image_url VARCHAR(255),
  customizable BOOLEAN DEFAULT true,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

CREATE TABLE product_sizes (
  id SERIAL PRIMARY KEY,
  product_id VARCHAR(10) REFERENCES products(id),
  size VARCHAR(50) NOT NULL,
  price INTEGER NOT NULL,
  weight VARCHAR(20),
  note VARCHAR(255)
);

CREATE TABLE product_variants (
  id SERIAL PRIMARY KEY,
  product_id VARCHAR(10) REFERENCES products(id),
  variant_name VARCHAR(50) NOT NULL
);

CREATE TABLE topping_options (
  id SERIAL PRIMARY KEY,
  product_id VARCHAR(10) REFERENCES products(id),
  topping_name VARCHAR(50) NOT NULL
);
```

---

## Search Tags (for Search Functionality)

### Vanilla Cakes
- Tags: vanilla, fruit, pineapple, blueberry, caramel, butterscotch, rasmalai, mango, strawberry, seasonal, fresh fruit

### Chocolate Cakes
- Tags: chocolate, truffle, cookies, cream, oreo, almond, hazelnut, ferrero, nutella

### Brownies
- Tags: brownie, chocolate, fudgy, hazelnut, almond, walnut, kitkat, oreo, chocolate chip

### Cheesecakes
- Tags: cheesecake, blueberry, strawberry, biscoff, nutella, cream cheese

---

## Price Calculation Logic

```javascript
// Calculate total price for order item
function calculateItemPrice(product, size, quantity, customization) {
  const sizeOption = product.sizes.find(s => s.size === size);
  if (!sizeOption) return 0;
  
  let basePrice = sizeOption.price;
  let additionalCost = 0;
  
  // Add customization costs if any (future feature)
  if (customization?.premium) {
    additionalCost += 50; // Example: ₹50 for premium customization
  }
  
  return (basePrice + additionalCost) * quantity;
}

// Calculate order total
function calculateOrderTotal(items) {
  return items.reduce((total, item) => {
    return total + item.price * item.quantity;
  }, 0);
}
```

---

This product data structure is ready for direct implementation in the app's database and can be easily imported, queried, and displayed throughout the application.
