# Orpington Rasoi - Elementor Implementation Guide
## Step-by-Step Page Building with Elementor Pro

---

## 🎨 SETUP & PREPARATION

### Step 1: Install Required Plugins

1. **Elementor Pro** (Page Builder)
2. **Astra Theme** (Recommended lightweight theme)
3. **WooCommerce** (E-commerce)
4. **Essential Addons for Elementor** (Extended widgets)
5. **Happy Addons** (Additional widgets)
6. **JetElements** (Advanced widgets for products)

### Step 2: Configure Elementor Settings

**Elementor → Settings → General:**
- CSS Print Method: External File
- Google Fonts: Enable

**Elementor → Settings → Advanced:**
- Enable Flexbox Container: Yes
- Enable Improved Asset Loading: Yes

**Elementor → Settings → Features:**
- Enable all features (Theme Builder, Popup, Custom Fonts, etc.)

---

## 🎨 GLOBAL DESIGN SETTINGS

### Step 1: Create Color Palette

**Elementor → Site Settings → Global Colors:**

1. **Primary** (#5C1A1A) - Maroon/Burgundy
2. **Secondary** (#E8B44D) - Golden Yellow
3. **Text** (#3D1F1F) - Dark Brown
4. **Accent** (#2D7A3E) - Fresh Green (Veg indicator)
5. **Background** (#F8F5F0) - Cream/Off-white
6. **Light Gray** (#F5F5F5) - Section backgrounds
7. **White** (#FFFFFF) - Cards
8. **Red Accent** (#D32F2F) - Spice indicator

### Step 2: Create Typography System

**Elementor → Site Settings → Global Fonts:**

**Primary Heading** (H1):
- Font Family: Poppins
- Weight: 700 (Bold)
- Size: 52px (Desktop), 36px (Tablet), 28px (Mobile)
- Line Height: 1.2

**Secondary Heading** (H2):
- Font Family: Poppins
- Weight: 600 (Semi-bold)
- Size: 42px (Desktop), 32px (Tablet), 24px (Mobile)
- Line Height: 1.3

**Third Heading** (H3):
- Font Family: Poppins
- Weight: 600
- Size: 32px (Desktop), 24px (Tablet), 20px (Mobile)
- Line Height: 1.4

**Fourth Heading** (H4):
- Font Family: Poppins
- Weight: 600
- Size: 24px (Desktop), 20px (Tablet), 18px (Mobile)
- Line Height: 1.4

**Body Text**:
- Font Family: Inter
- Weight: 400 (Regular)
- Size: 16px (Desktop), 15px (Tablet), 14px (Mobile)
- Line Height: 1.6

**Accent Text** (for taglines):
- Font Family: Pacifico
- Weight: 400
- Size: 24px
- Line Height: 1.5

### Step 3: Create Button Styles

**Elementor → Site Settings → Buttons:**

**Primary Button Style:**
```
Background Color: Secondary (#E8B44D)
Text Color: Text (#3D1F1F)
Border Radius: 8px
Padding: 16px 32px
Typography: Poppins, 18px, 600 weight
Box Shadow: 0 4px 12px rgba(232, 180, 77, 0.3)

Hover:
  Background: #D4A03D
  Transform: translateY(-2px)
  Box Shadow: 0 6px 16px rgba(232, 180, 77, 0.4)
  Transition: all 0.3s ease
```

**Secondary Button Style:**
```
Background Color: Transparent
Text Color: Primary (#5C1A1A)
Border: 2px solid Primary
Border Radius: 8px
Padding: 14px 30px
Typography: Poppins, 18px, 600 weight

Hover:
  Background: Primary (#5C1A1A)
  Text Color: White
  Transform: translateY(-2px)
```

---

## 🏗️ HEADER TEMPLATE (ELEMENTOR THEME BUILDER)

### Create Header Template

**Elementor → Theme Builder → Header → Add New**

### Header Structure (Container Layout)

```
CONTAINER (Full Width, Sticky: Top)
├── CONTAINER (Boxed, 1200px max-width)
│   ├── COLUMN 1 (33% width) - Logo Section
│   │   └── Image Widget (Logo)
│   │
│   ├── COLUMN 2 (44% width) - Navigation Menu
│   │   └── Nav Menu Widget
│   │
│   └── COLUMN 3 (23% width) - CTA & Cart
│       ├── Menu Cart Widget
│       └── Button Widget ("Order Now")
```

### Detailed Widget Settings:

#### Logo (Image Widget)
- Upload: Orpington Rasoi Logo (FINAL).png
- Width: 180px (Desktop), 140px (Mobile)
- Link: Homepage URL
- Alt Text: "Orpington Rasoi Logo"

#### Navigation Menu Widget
- Menu: Primary Menu (create in Appearance → Menus)
- Layout: Horizontal
- Alignment: Center
- Menu Items:
  - Home
  - Menu
  - About Us
  - Delivery Info
  - Contact

**Menu Styling:**
- Text Color: Text (#3D1F1F)
- Hover Color: Secondary (#E8B44D)
- Active Color: Primary (#5C1A1A)
- Typography: Poppins, 16px, 500 weight
- Padding: 12px 16px
- Transition: 0.3s

#### Menu Cart Widget
- Icon: Shopping bag
- Show Subtotal: Yes
- Icon Color: Primary (#5C1A1A)
- Badge Background: Secondary (#E8B44D)
- Badge Text Color: Text (#3D1F1F)

#### Order Now Button
- Text: "Order Now"
- Link: Menu page URL
- Style: Use Primary Button global style
- Add golden glow animation on hover

### Mobile Header (Responsive Settings)

**Mobile Breakpoint (< 768px):**
- Hide desktop navigation
- Show mobile toggle icon (hamburger)
- Logo: 120px width
- Full-width layout

**Mobile Menu (Popup):**
- Create using Elementor Popup Builder
- Slide from right animation
- Dark overlay background
- Full-height sidebar style
- Close icon at top right

---

## 🏠 HOMEPAGE BUILD (ELEMENTOR)

### Section 1: HERO SECTION

**Create New Page → Edit with Elementor**

#### Container Settings:
- Layout: Full Width
- Minimum Height: 100vh
- Background Type: Slideshow
- Background Images:
  1. Butter Chicken hero image
  2. Chicken Tikka hero image
  3. Paneer Tikka hero image
  4. Biryani hero image
- Slideshow Transition: Fade
- Duration: 5000ms
- Background Overlay: Gradient (Black 0% to 40% opacity)

#### Content Structure:
```
CONTAINER (Full Width, Centered Vertically & Horizontally)
└── CONTAINER (Boxed, 800px max-width, Center aligned)
    ├── Heading Widget
    │   Text: "Authentic Indian Cuisine"
    │   HTML Tag: H1
    │   Color: White
    │   Typography: Primary Heading
    │   Text Shadow: 0 2px 8px rgba(0,0,0,0.5)
    │
    ├── Heading Widget
    │   Text: "Delivered Fresh to Your Door"
    │   HTML Tag: H2
    │   Color: White
    │   Typography: Secondary Heading
    │
    ├── Text Editor Widget
    │   Text: "Made with Love, Served with Pride"
    │   Color: Secondary (#E8B44D)
    │   Typography: Accent Text (Pacifico)
    │
    ├── Spacer (30px)
    │
    ├── CONTAINER (Horizontal, Centered, Gap: 20px)
    │   ├── Button Widget ("Order Now")
    │   │   Style: Primary Button
    │   │   Link: Menu page
    │   │   Icon: Shopping cart
    │   │
    │   └── Button Widget ("View Menu")
    │       Style: Secondary Button (White border)
    │       Link: Menu page
    │       Icon: Menu icon
    │
    ├── Spacer (40px)
    │
    └── Icon List Widget
        Items:
        ├── ⏰ Open Daily 5:00 PM - 10:00 PM
        └── 📍 Orpington, London
        Color: White
        Typography: 16px, Poppins
```

#### Scroll Down Indicator:
- Add Icon Widget (Down arrow)
- Position: Absolute, Bottom: 30px
- Animated: Ken Burns (floating effect)
- Color: White with opacity 80%

---

### Section 2: QUICK ORDER STEPS

#### Container Settings:
- Layout: Boxed (1200px)
- Background: Light cream (#F8F5F0)
- Padding: 80px 40px (Desktop), 60px 20px (Mobile)

#### Content Structure:
```
CONTAINER (3 Columns - Desktop, 1 Column - Mobile)
│
├── Heading Widget (Full Width)
│   Text: "Order in 3 Simple Steps"
│   HTML Tag: H2
│   Alignment: Center
│   Bottom Margin: 60px
│
├── COLUMN 1
│   └── Icon Box Widget
│       Icon: fa-utensils (Menu icon)
│       Icon Color: Primary (#5C1A1A)
│       Icon Size: 64px
│       Title: "Browse Menu"
│       Description: "Choose from 40+ authentic dishes"
│       Title Color: Primary
│       Description Color: Text
│       Alignment: Center
│       Hover: Transform scale(1.05), translateY(-5px)
│
├── COLUMN 2
│   └── Icon Box Widget
│       Icon: fa-shopping-cart
│       Icon Color: Primary (#5C1A1A)
│       Icon Size: 64px
│       Title: "Add to Cart"
│       Description: "Secure checkout via Stripe"
│       Title Color: Primary
│       Description Color: Text
│       Alignment: Center
│       Hover: Transform scale(1.05), translateY(-5px)
│
└── COLUMN 3
    └── Icon Box Widget
        Icon: fa-shipping-fast
        Icon Color: Primary (#5C1A1A)
        Icon Size: 64px
        Title: "Fast Delivery"
        Description: "30-45 min delivery to your door"
        Title Color: Primary
        Description Color: Text
        Alignment: Center
        Hover: Transform scale(1.05), translateY(-5px)
```

**Add Arrows Between Icons (Desktop only):**
- Use Icon Widget with → arrow
- Position between columns
- Hide on mobile

---

### Section 3: FEATURED DISHES CAROUSEL

#### Container Settings:
- Layout: Boxed (1200px)
- Background: White
- Padding: 100px 40px

#### Content Structure:
```
CONTAINER
│
├── CONTAINER (Heading Area, Center aligned)
│   ├── Heading Widget
│   │   Text: "Our Signature Dishes"
│   │   HTML Tag: H2
│   │   Color: Primary
│   │
│   └── Text Editor Widget
│       Text: "Handcrafted with Traditional Recipes"
│       Color: Text (lighter)
│       Bottom Margin: 60px
│
└── Products Widget (WooCommerce)
    Query:
    ├── Source: Products
    ├── Filter by: Featured Products
    ├── Posts Per Page: 8
    └── Order By: Popularity

    Layout:
    ├── Columns: 4 (Desktop), 2 (Tablet), 1 (Mobile)
    ├── Rows: 2
    └── Products Gap: 30px

    Design:
    ├── Show: Image, Title, Price, Add to Cart
    ├── Image Ratio: 1:1
    ├── Image Border Radius: 12px
    └── Overlay: Hover with "Quick View"
```

#### Custom Product Card Styling (Additional CSS):

```css
/* Product Card */
.elementor-product {
    background: white;
    border-radius: 12px;
    overflow: hidden;
    transition: all 0.3s ease;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.elementor-product:hover {
    transform: translateY(-8px);
    box-shadow: 0 8px 24px rgba(0,0,0,0.15);
}

/* Product Image */
.elementor-product__image {
    position: relative;
    overflow: hidden;
}

.elementor-product__image img {
    transition: transform 0.4s ease;
}

.elementor-product:hover .elementor-product__image img {
    transform: scale(1.1);
}

/* Add to Cart Button */
.elementor-product .button {
    background: #E8B44D;
    color: #3D1F1F;
    border-radius: 8px;
    font-weight: 600;
    transition: all 0.3s ease;
}

.elementor-product .button:hover {
    background: #D4A03D;
    transform: translateY(-2px);
}

/* Price */
.elementor-product .price {
    color: #5C1A1A;
    font-size: 24px;
    font-weight: 700;
}
```

**Add Custom Badges:**
- Use Badge widget from Essential Addons
- Position: Absolute, top-right of image
- Popular badge: Golden background
- Veg badge: Green background with leaf icon

---

### Section 4: WHY CHOOSE US

#### Container Settings:
- Layout: Boxed (1200px)
- Background: White
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Why Orpington Rasoi?"
│   Alignment: Center
│   Bottom Margin: 80px
│
└── CONTAINER (4 Columns - Desktop, 2 - Tablet, 1 - Mobile)
    │
    ├── COLUMN 1
    │   └── Icon Box Widget
    │       Icon: Custom SVG (Fresh ingredients)
    │       Title: "Fresh Ingredients"
    │       Description: "Daily fresh ingredients"
    │
    ├── COLUMN 2
    │   └── Icon Box Widget
    │       Icon: Custom SVG (Recipe book)
    │       Title: "Authentic Recipes"
    │       Description: "Family recipes passed down"
    │
    ├── COLUMN 3
    │   └── Icon Box Widget
    │       Icon: Custom SVG (Clock)
    │       Title: "Fast Delivery"
    │       Description: "30-45 min guaranteed"
    │
    └── COLUMN 4
        └── Icon Box Widget
            Icon: Custom SVG (Halal)
            Title: "Halal Certified"
            Description: "100% Halal meat"
```

**Icon Box Styling:**
- Icon size: 80px
- Icon color: Maroon with golden accent
- Background: Light gray (#F5F5F5)
- Padding: 40px
- Border radius: 12px
- Center aligned
- Hover effect: Lift up 5px with shadow

---

### Section 5: CUSTOMER TESTIMONIALS

#### Container Settings:
- Layout: Full Width
- Background: Light gray (#F5F5F5)
- Padding: 100px 40px

```
CONTAINER (Boxed, 1200px)
│
├── Heading Widget
│   Text: "What Our Customers Say"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── Testimonial Carousel Widget (Essential Addons)
    Layout:
    ├── Columns: 3 (Desktop), 2 (Tablet), 1 (Mobile)
    ├── Show: 3 items
    ├── Autoplay: Yes (5s)
    └── Navigation: Dots + Arrows

    Content:
    Each testimonial:
    ├── Rating: 5 stars (golden)
    ├── Text: Customer review
    ├── Name: Customer name
    └── Photo: Avatar placeholder

    Styling:
    ├── Background: White
    ├── Border radius: 12px
    ├── Padding: 30px
    ├── Shadow: 0 2px 12px rgba(0,0,0,0.1)
    └── Quote icon: Large maroon quote mark
```

**Sample Testimonials:**
1. "Best Indian food in Orpington! The butter chicken is absolutely divine. Fast delivery too!" - Sarah M.
2. "Authentic flavors that remind me of home. The biryani is perfectly spiced." - Raj K.
3. "Fast delivery and food always arrives hot. Our go-to for Friday nights!" - Emma T.

---

### Section 6: DELIVERY AREAS

#### Container Settings:
- Layout: Boxed (1200px)
- Background: White
- Padding: 100px 40px

```
CONTAINER (2 Columns)
│
├── Heading Widget (Full Width)
│   Text: "We Deliver To Your Area"
│   Alignment: Center
│   Bottom Margin: 60px
│
├── COLUMN 1 (60% width)
│   └── Icon List Widget
│       Items:
│       ├── ✓ BR5 - Orpington
│       ├── ✓ BR6 - Locksbottom
│       ├── ✓ BR2 - Bromley South
│       ├── ✓ BR1 - Bromley
│       └── ✓ And surrounding areas
│
│       Styling:
│       ├── Icon: Check circle
│       ├── Icon Color: Green (#2D7A3E)
│       ├── Text Color: Text
│       └── Typography: 18px, Poppins
│
└── COLUMN 2 (40% width)
    └── Pricing Box Widget
        Content:
        ├── Title: "Free Delivery"
        ├── Price: "on orders over £25"
        ├── Description: "Otherwise £3.50"

        Styling:
        ├── Background: Light cream (#F8F5F0)
        ├── Border: 2px solid Secondary
        ├── Border radius: 12px
        ├── Padding: 40px
        └── Title Color: Primary
```

**Add Postcode Checker:**
- Use Form widget (Elementor Pro)
- Single text field: "Enter your postcode"
- Submit button: "Check Availability"
- Integrate with WooCommerce shipping zones

---

### Section 7: CTA BANNER

#### Container Settings:
- Layout: Full Width
- Background: Maroon (#5C1A1A)
- Background Overlay: Food texture pattern (20% opacity)
- Padding: 120px 40px

```
CONTAINER (Boxed, 800px, Center aligned)
│
├── Heading Widget
│   Text: "Hungry? Order Now!"
│   Color: White
│   HTML Tag: H2
│   Text Shadow: 0 2px 8px rgba(0,0,0,0.3)
│
├── Text Editor Widget
│   Text: "Fresh, Hot Food Delivered in 30-45 Minutes"
│   Color: Secondary (#E8B44D)
│   Typography: 20px, Poppins
│
├── Spacer (30px)
│
└── Button Widget
    Text: "View Full Menu"
    Style: Large golden button
    Link: Menu page
    Icon: Arrow right
    Size: Extra large
```

---

## 🍽️ MENU/SHOP PAGE BUILD

### Page Template Setup

**Create New Page: "Menu"**
- Template: Elementor Full Width
- WooCommerce: Set as shop page

### Top Hero Banner Section

```
CONTAINER (Full Width)
├── Background: Food collage image (blurred)
├── Overlay: Gradient (maroon to transparent)
├── Padding: 120px 40px
└── Content:
    ├── Heading: "Our Complete Menu"
    │   Color: White
    │   HTML Tag: H1
    │
    └── Text: "Explore 40+ Authentic Indian Dishes"
        Color: Secondary
```

### Filter & Search Bar (Sticky Section)

```
CONTAINER (Full Width, Sticky)
├── Background: White
├── Box Shadow: 0 2px 8px rgba(0,0,0,0.1)
├── Padding: 20px 40px
│
└── CONTAINER (Boxed, 1200px)
    │
    ├── Search Widget (Full Width)
    │   Placeholder: "🔍 Search dishes..."
    │   Border radius: 8px
    │   Bottom margin: 20px
    │
    ├── CONTAINER (Category Pills - Horizontal scroll)
    │   └── Button Group (Toggleable)
    │       Items:
    │       ├── All
    │       ├── Starters
    │       ├── Mains
    │       ├── Biryani & Rice
    │       ├── Breads & Rolls
    │       └── Combos
    │
    │       Styling:
    │       ├── Normal: Outline, Maroon border
    │       └── Active: Filled, Golden background
    │
    └── CONTAINER (Filter Toggles)
        Items (Checkbox style):
        ├── 🌱 Vegetarian
        ├── 🌶️ Spice Level
        ├── 💰 Price Range
        ├── ⚡ Popular
        └── 🔥 Chef's Special
```

**Make Sticky:**
- Advanced → Motion Effects → Sticky: Top
- Sticky offset: 100px (header height)
- Effects offset: 0px

### Main Product Grid Section

```
CONTAINER (Boxed, 1200px)
├── Padding: 60px 40px
│
└── GRID LAYOUT (2 Columns)
    │
    ├── COLUMN 1 - Sidebar (280px, Sticky)
    │   │
    │   └── CONTAINER (Filters)
    │       Background: Light cream (#F8F5F0)
    │       Border radius: 12px
    │       Padding: 30px
    │
    │       Widgets:
    │       ├── Heading: "CATEGORIES"
    │       ├── Category List Widget (WooCommerce)
    │       │   Show count: Yes
    │       │   Hierarchical: Yes
    │       │
    │       ├── Divider
    │       ├── Heading: "DIETARY"
    │       ├── Product Filter Widget
    │       │   Filter by: Dietary tags
    │       │   Style: Checkbox
    │       │
    │       ├── Divider
    │       ├── Heading: "SPICE LEVEL"
    │       ├── Product Filter Widget
    │       │   Filter by: Spice attribute
    │       │
    │       ├── Divider
    │       ├── Heading: "PRICE RANGE"
    │       └── Price Filter Widget (WooCommerce)
    │           Min: £0
    │           Max: £15
    │           Style: Slider
    │
    └── COLUMN 2 - Product Grid (Flexible)
        │
        └── Products Widget (WooCommerce)
            Query:
            ├── Source: All Products
            ├── Posts Per Page: 12
            ├── Pagination: Yes
            └── Columns: 3 (Desktop), 2 (Tablet), 1 (Mobile)

            Show:
            ├── Image
            ├── Title
            ├── Short Description
            ├── Price
            ├── Add to Cart button
            ├── Badges (custom)
            └── Quick view link
```

### Product Card Customization (using Product Archive template)

**Elementor → Theme Builder → Product Archive → Create New**

```
CONTAINER (Product Card)
├── Background: White
├── Border radius: 12px
├── Box shadow: 0 2px 8px rgba(0,0,0,0.1)
├── Padding: 0
├── Hover: Transform translateY(-8px)
│
└── STRUCTURE:
    │
    ├── Product Image Widget
    │   Aspect ratio: 1:1
    │   Border radius top: 12px
    │   Hover: Scale 1.1
    │
    │   Badges (Absolute position):
    │   ├── Top Left: Veg/Non-veg badge
    │   └── Top Right: Popular/New badge
    │
    ├── CONTAINER (Content - Padding 20px)
    │   │
    │   ├── Product Title Widget
    │   │   HTML Tag: H3
    │   │   Typography: 20px, Poppins, 600
    │   │   Color: Text
    │   │   Limit: 2 lines
    │   │
    │   ├── Custom Field Widget (Spice Level)
    │   │   Display: 🌶️ icons based on meta
    │   │   Color: Red accent
    │   │
    │   ├── Product Short Description Widget
    │   │   Lines: 2
    │   │   Color: Text (lighter)
    │   │   Typography: 14px
    │   │
    │   ├── Custom Field Widget (Allergens)
    │   │   Display: Icon + text
    │   │   Typography: 12px, light
    │   │   Color: Gray
    │   │
    │   ├── Spacer (10px)
    │   │
    │   └── CONTAINER (Flex, Space Between)
    │       ├── Product Price Widget
    │       │   Color: Primary (#5C1A1A)
    │       │   Typography: 24px, bold
    │       │
    │       └── Add to Cart Widget
    │           Style: Icon only (+ symbol)
    │           Background: Secondary (circular)
    │           Size: 48px
    │           Hover: Scale 1.1
```

### Mobile Sidebar (Convert to Filter Popup)

**Mobile (<768px):**
- Hide sidebar column
- Add floating "Filters" button (bottom-left, sticky)
- Button opens popup with all filters
- Popup slides from left

**Create Popup Template:**
- Elementor → Templates → Popups → Add New
- Copy all sidebar filter widgets
- Add close button at top-right
- Set trigger: Click on "Filters" button

---

## 🛒 CART PAGE CUSTOMIZATION

### Override Default WooCommerce Cart

**Elementor → Theme Builder → WooCommerce → Cart → Create New**

### Cart Page Layout

```
CONTAINER (Full Width)
│
├── CONTAINER (Boxed, 1200px)
│   │
│   ├── Heading Widget
│   │   Text: "Your Shopping Cart"
│   │   Add dynamic count: {{cart_count}} items
│   │
│   ├── Button Widget
│   │   Text: "← Continue Shopping"
│   │   Link: Menu page
│   │   Style: Text link
│   │
│   └── GRID (2 Columns - Desktop, 1 Column - Mobile)
│       │
│       ├── COLUMN 1 (65% width) - Cart Items
│       │   │
│       │   └── Cart Table Widget (WooCommerce)
│       │       Customize:
│       │       ├── Show product thumbnails
│       │       ├── Show product customizations
│       │       ├── Quantity selector style
│       │       ├── Remove button style
│       │       └── Update cart button
│       │
│       │       Styling:
│       │       ├── Product image: 120px square
│       │       ├── Each row: White card with shadow
│       │       ├── Border radius: 12px
│       │       ├── Margin between rows: 20px
│       │       └── Padding: 20px
│       │
│       └── COLUMN 2 (35% width) - Order Summary
│           │
│           └── CONTAINER (Sticky)
│               Background: Light cream (#F8F5F0)
│               Border radius: 12px
│               Padding: 30px
│               Box shadow: 0 4px 12px rgba(0,0,0,0.1)
│
│               Widgets:
│               ├── Heading: "ORDER SUMMARY"
│               │   Typography: 20px, bold
│               │
│               ├── Cart Totals Widget (WooCommerce)
│               │   Show:
│               │   ├── Subtotal
│               │   ├── Delivery fee
│               │   ├── Discount (if any)
│               │   └── Total (large, bold)
│               │
│               ├── Divider
│               │
│               ├── Icon List: Delivery Address
│               │   📍 Not selected [Change]
│               │
│               ├── Icon List: Delivery Time
│               │   ⏰ [Select time slot ▼]
│               │
│               ├── Divider
│               │
│               ├── Cart Coupon Widget
│               │   Placeholder: "Have a promo code?"
│               │   Button: "APPLY"
│               │
│               ├── Spacer (20px)
│               │
│               ├── Button Widget: "PROCEED TO CHECKOUT"
│               │   Style: Primary button
│               │   Full width
│               │   Size: Large
│               │   Icon: Lock (for security)
│               │
│               └── CONTAINER (Trust Badges)
│                   ├── Icon: 🔒 Secure Payment
│                   └── Icon: 💯 Money Back Guarantee
│                   Typography: 12px, center
│                   Color: Gray
```

### Empty Cart State

**Create Conditional Visibility:**

```
CONTAINER (Show when cart is empty)
├── Align: Center
├── Padding: 120px 40px
│
└── Content:
    ├── Icon Widget
    │   Icon: fa-shopping-cart (empty)
    │   Size: 120px
    │   Color: Light gray
    │
    ├── Heading Widget
    │   Text: "Your cart is empty"
    │   Color: Text
    │
    ├── Text Widget
    │   Text: "Let's fill it with delicious food!"
    │   Color: Gray
    │
    └── Button Widget
        Text: "BROWSE MENU"
        Link: Menu page
        Style: Primary button
```

---

## 💳 CHECKOUT PAGE CUSTOMIZATION

**Elementor → Theme Builder → WooCommerce → Checkout → Create New**

### Progress Indicator Section

```
CONTAINER (Full Width)
├── Background: Light gray
├── Padding: 30px 20px
│
└── CONTAINER (Boxed, 800px, Center)
    └── Progress Bar Widget (Custom or Essential Addons)
        Steps:
        ├── 1. Delivery (Active)
        ├── 2. Payment (Inactive)
        └── 3. Confirm (Inactive)

        Styling:
        ├── Active: Golden circle
        ├── Inactive: Gray circle
        └── Line: Gray, golden when completed
```

### Checkout Form Section

```
CONTAINER (Boxed, 1200px)
├── Padding: 60px 40px
│
└── GRID (2 Columns - Desktop, Stack on Mobile)
    │
    ├── COLUMN 1 (65% width) - Checkout Form
    │   │
    │   └── Checkout Form Widget (WooCommerce)
    │
    │       Customizations:
    │
    │       1️⃣ DELIVERY OPTIONS (Radio buttons)
    │       ○ Delivery  ● Collection
    │       Style: Large toggle buttons
    │
    │       2️⃣ CUSTOMER DETAILS
    │       Fields:
    │       ├── Full Name *
    │       ├── Phone Number *
    │       ├── Email *
    │       └── Company (optional, hide)
    │
    │       Field Styling:
    │       ├── Border radius: 6px
    │       ├── Padding: 14px
    │       ├── Border: 1px solid light gray
    │       └── Focus: Border color to secondary
    │
    │       3️⃣ DELIVERY ADDRESS (Show if Delivery selected)
    │       Fields:
    │       ├── Address Line 1 *
    │       ├── Address Line 2
    │       ├── Postcode * [Validate button]
    │       ├── City (auto-fill)
    │       └── County (auto-fill)
    │
    │       4️⃣ DELIVERY TIME
    │       ├── Date Selector Dropdown
    │       │   Options: Today, Tomorrow, Custom
    │       └── Time Slot Dropdown
    │           Options: 5:00 PM - 5:30 PM, etc.
    │           Show only available slots
    │
    │       5️⃣ SPECIAL INSTRUCTIONS
    │       Textarea:
    │       ├── Placeholder: "Any special requests?"
    │       ├── Rows: 3
    │       └── Optional
    │
    │       6️⃣ PAYMENT METHOD
    │       Radio buttons:
    │       ├── ● Credit/Debit Card (Stripe)
    │       └── ○ Cash on Delivery
    │
    │       [Stripe Card Element - embed seamlessly]
    │
    │       7️⃣ TERMS & CONDITIONS
    │       Checkbox:
    │       ☑️ I accept the Terms & Conditions
    │
    │       8️⃣ PLACE ORDER BUTTON
    │       Button: "PLACE ORDER - £28.50"
    │       Style: Primary button
    │       Full width
    │       Size: Extra large
    │       Loading state: Spinner
    │
    └── COLUMN 2 (35% width) - Order Review
        │
        └── CONTAINER (Sticky)
            Background: Light cream
            Border radius: 12px
            Padding: 30px

            Widgets:
            ├── Heading: "YOUR ORDER"
            │
            ├── Order Review Widget (WooCommerce)
            │   Show each product:
            │   ├── Thumbnail (60px)
            │   ├── Name
            │   ├── Quantity
            │   └── Subtotal
            │
            ├── Divider
            │
            ├── Cart Totals
            │   ├── Subtotal: £25.50
            │   ├── Delivery: £3.50
            │   ├── Discount: -£0.00
            │   └── Total: £28.50 (Large, bold)
            │
            └── Trust Badges
                ├── 🔒 Secure Payment
                └── Powered by Stripe logo
```

### Field Styling (Custom CSS)

```css
/* Checkout form fields */
.woocommerce-checkout .form-row input,
.woocommerce-checkout .form-row select,
.woocommerce-checkout .form-row textarea {
    border-radius: 6px;
    border: 1px solid #E0E0E0;
    padding: 14px;
    font-size: 16px;
    transition: border-color 0.3s ease;
}

.woocommerce-checkout .form-row input:focus,
.woocommerce-checkout .form-row select:focus {
    border-color: #E8B44D;
    outline: none;
    box-shadow: 0 0 0 3px rgba(232, 180, 77, 0.1);
}

/* Required field asterisk */
.woocommerce-checkout .required {
    color: #D32F2F;
}

/* Stripe element styling */
.wc-stripe-elements-field {
    border: 1px solid #E0E0E0;
    border-radius: 6px;
    padding: 14px;
    background: white;
}

/* Place order button */
.woocommerce-checkout #place_order {
    background: #E8B44D;
    color: #3D1F1F;
    border: none;
    border-radius: 8px;
    padding: 18px 40px;
    font-size: 20px;
    font-weight: 600;
    width: 100%;
    cursor: pointer;
    transition: all 0.3s ease;
}

.woocommerce-checkout #place_order:hover {
    background: #D4A03D;
    transform: translateY(-2px);
    box-shadow: 0 6px 16px rgba(232, 180, 77, 0.4);
}
```

---

## ✅ ORDER CONFIRMATION PAGE

**Create New Page: "Order Confirmation"**

```
CONTAINER (Boxed, 800px, Center aligned)
├── Padding: 100px 40px
│
└── Content:
    │
    ├── Icon Widget
    │   Icon: Check circle (animated)
    │   Color: Green
    │   Size: 100px
    │   Animation: Scale in
    │
    ├── Heading Widget
    │   Text: "Order Confirmed!"
    │   Color: Primary
    │   HTML Tag: H1
    │
    ├── Text Widget
    │   Text: "Thank you for your order!"
    │   Typography: 20px
    │
    ├── Text Widget
    │   Text: "Your food is being prepared with love"
    │   Color: Gray
    │
    ├── Spacer (40px)
    │
    ├── CONTAINER (Order Details Box)
    │   Background: Light cream
    │   Border: 2px solid Secondary
    │   Border radius: 12px
    │   Padding: 40px
    │
    │   Content:
    │   ├── Text: "Order #{{order_number}}"
    │   │   Typography: Bold, 18px
    │   │
    │   ├── Text: "Estimated Delivery: {{delivery_time}}"
    │   │   Icon: Clock
    │   │
    │   ├── Divider
    │   │
    │   ├── Text: "📧 Confirmation sent to: {{customer_email}}"
    │   ├── Text: "📱 Track your order via SMS updates"
    │   │
    │   ├── Divider
    │   │
    │   └── Text: "Need help? Call us: {{phone}}"
    │       Typography: Bold
    │
    ├── Spacer (40px)
    │
    └── CONTAINER (Action Buttons)
        Flex, Gap: 20px
        │
        ├── Button Widget: "ORDER AGAIN"
        │   Link: Menu page
        │   Style: Primary
        │
        └── Button Widget: "TRACK ORDER"
            Link: My Account → Orders
            Style: Secondary
```

---

## 📄 ABOUT US PAGE

### Hero Section
```
CONTAINER (Full Width)
├── Background: Kitchen/chef photo (blurred)
├── Overlay: Gradient maroon
├── Padding: 120px 40px
│
└── Content (Center aligned):
    ├── Heading: "Our Story"
    │   Color: White
    │   HTML Tag: H1
    │
    └── Text: "Bringing Authentic Indian Flavors to Orpington"
        Color: Secondary
        Typography: 24px, Pacifico
```

### Story Section
```
CONTAINER (Boxed, 1200px)
├── Padding: 100px 40px
│
└── GRID (2 Columns)
    │
    ├── COLUMN 1 (Image)
    │   └── Image Widget
    │       Image: Restaurant/food preparation photo
    │       Border radius: 12px
    │       Shadow: Medium
    │
    └── COLUMN 2 (Content)
        ├── Heading: "Welcome to Orpington Rasoi"
        │   HTML Tag: H2
        │   Color: Primary
        │
        ├── Text Editor Widget
        │   Content: Restaurant story (300-500 words)
        │   Typography: 18px, line height 1.8
        │
        │   Suggested content:
        │   "Our journey began with a simple passion:
        │   to share the authentic flavors of Indian
        │   home cooking with our community.
        │
        │   Each dish is prepared using traditional
        │   family recipes, fresh ingredients, and
        │   genuine love for Indian cuisine..."
        │
        └── Button Widget: "View Our Menu"
            Style: Primary
```

### What Makes Us Special Section
```
CONTAINER (Full Width)
├── Background: Light gray
├── Padding: 100px 40px
│
└── CONTAINER (Boxed, 1200px)
    │
    ├── Heading: "What Makes Us Special"
    │   Alignment: Center
    │   Bottom margin: 60px
    │
    └── GRID (4 Columns)
        │
        ├── Icon Box: Fresh Daily
        │   Icon: Custom SVG
        │   Description: "We source fresh ingredients daily"
        │
        ├── Icon Box: Family Recipes
        │   Icon: Custom SVG
        │   Description: "Authentic family recipes"
        │
        ├── Icon Box: Halal Certified
        │   Icon: Custom SVG
        │   Description: "100% Halal certified meat"
        │
        └── Icon Box: Made with Love
            Icon: Custom SVG (Heart)
            Description: "Prepared with care and passion"
```

---

## 🍽️ CATERING PAGE BUILD (ELEMENTOR)

### Page Setup
**Create New Page: "Catering"**
- Template: Elementor Full Width
- Add to navigation menu

---

### Section 1: Hero Banner

#### Container Settings:
- Layout: Full Width
- Minimum Height: 60vh
- Background Type: Classic
- Background Image: Elegant buffet/catering setup
- Background Position: Center Center
- Background Size: Cover
- Background Overlay: Gradient
  - Color 1: #5C1A1A (Maroon) 0%
  - Color 2: Transparent 100%
  - Opacity: 50%

#### Content Structure:
```
CONTAINER (Centered Vertically & Horizontally)
└── CONTAINER (Boxed, 800px, Center aligned)
    ├── Heading Widget
    │   Text: "Catering Services"
    │   HTML Tag: H1
    │   Color: White
    │   Typography: Primary Heading (52px)
    │   Text Shadow: 0 2px 8px rgba(0,0,0,0.5)
    │
    └── Heading Widget
        Text: "Perfect for Parties, Events & Corporate Functions"
        HTML Tag: H2
        Color: Secondary (#E8B44D)
        Typography: 24px, Poppins
        Text Shadow: 0 2px 8px rgba(0,0,0,0.3)
```

---

### Section 2: Introduction

#### Container Settings:
- Layout: Boxed (800px)
- Background: White
- Padding: 80px 40px
- Text Align: Center

```
CONTAINER
│
├── Heading Widget
│   Text: "Authentic Indian Catering for Your Event"
│   HTML Tag: H2
│   Color: Primary (#5C1A1A)
│   Typography: Secondary Heading
│   Bottom Margin: 30px
│
├── Text Editor Widget
│   Content: "Whether it's a birthday celebration, corporate
│            lunch, wedding reception, or any special occasion,
│            Orpington Rasoi brings authentic Indian flavors
│            to your event."
│   Typography: 18px, Inter, line height 1.8
│   Color: Text (#3D1F1F)
│   Bottom Margin: 40px
│
└── Icon List Widget
    Layout: Vertical
    Icon Color: Green (#2D7A3E)
    Icon Size: 24px
    Typography: 18px, Poppins
    Space Between: 20px

    Items:
    ├── ✓ Custom menus tailored to your needs
    ├── ✓ Professional setup and service options
    ├── ✓ Suitable for 20-200+ guests
    └── ✓ Dietary requirements accommodated
```

---

### Section 3: Catering Packages

#### Container Settings:
- Layout: Boxed (1200px)
- Background: Light gray (#F5F5F5)
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Our Catering Packages"
│   HTML Tag: H2
│   Alignment: Center
│   Color: Primary
│   Bottom Margin: 60px
│
└── GRID CONTAINER (3 Columns - Desktop, 1 Column - Mobile)
    Gap: 30px
    │
    ├── COLUMN 1 - Bronze Package
    │   │
    │   └── Pricing Table Widget (or Icon Box)
    │       │
    │       ├── Badge: "BRONZE PACKAGE"
    │       │   Background: #CD7F32
    │       │   Color: White
    │       │   Position: Top center
    │       │
    │       ├── Price: "From £12/pp"
    │       │   Typography: 32px, bold
    │       │   Color: Primary
    │       │
    │       ├── Icon List Widget
    │       │   Items:
    │       │   • 1 Starter
    │       │   • 1 Main Course
    │       │   • Rice or Bread
    │       │   • Chutney
    │       │
    │       │   Minimum: 20 guests
    │       │
    │       └── Styling:
    │           Background: White
    │           Border radius: 12px
    │           Padding: 40px
    │           Box shadow: 0 4px 12px rgba(0,0,0,0.1)
    │           Hover: Transform translateY(-10px)
    │           Hover: Golden border (3px)
    │
    ├── COLUMN 2 - Silver Package
    │   │
    │   └── Pricing Table Widget
    │       Badge: "SILVER PACKAGE"
    │       Background: #C0C0C0
    │       Price: "From £18/pp"
    │       Items:
    │       • 2 Starters
    │       • 2 Main Courses
    │       • Rice + Naan
    │       • Raita
    │       • Salad
    │
    │       Minimum: 30 guests
    │
    │       [Same styling as Bronze]
    │
    └── COLUMN 3 - Gold Package
        │
        └── Pricing Table Widget
            Badge: "GOLD PACKAGE"
            Background: #FFD700
            Price: "From £25/pp"
            Items:
            • 3 Starters
            • 3 Main Courses
            • Rice + Breads
            • Dessert
            • Premium Service

            Minimum: 50 guests

            [Same styling as Bronze]
            Featured: Yes (add "POPULAR" tag)
```

**Package Card Hover Animation:**
```css
.catering-package {
    transition: all 0.4s ease;
}

.catering-package:hover {
    transform: translateY(-10px);
    border: 3px solid #E8B44D;
    box-shadow: 0 12px 24px rgba(232, 180, 77, 0.3);
}
```

---

### Section 4: Popular Menu Items

#### Container Settings:
- Layout: Boxed (1200px)
- Background: Light cream (#F8F5F0)
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Popular Catering Choices"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── GRID CONTAINER (4 Columns - Desktop, 2 - Tablet, 1 - Mobile)
    │
    ├── COLUMN 1 - Starters
    │   │
    │   └── CONTAINER
    │       ├── Heading Widget
    │       │   Text: "STARTERS"
    │       │   Typography: 16px, bold, uppercase
    │       │   Color: Primary
    │       │   Bottom Border: 2px solid Secondary
    │       │   Bottom Margin: 20px
    │       │
    │       └── Icon List Widget
    │           Items:
    │           • Chicken Tikka
    │           • Paneer Tikka
    │           • Samosas
    │           • Pakoras
    │           Icon: None or simple bullet
    │           Typography: 16px
    │
    ├── COLUMN 2 - Main Courses
    │   [Same structure as Starters]
    │   Items:
    │   • Butter Chicken
    │   • Chicken Tikka Masala
    │   • Lamb Curry
    │   • Paneer Tikka Masala
    │   • Mix Vegetable Curry
    │
    ├── COLUMN 3 - Accompaniments
    │   [Same structure]
    │   Items:
    │   • Pilau Rice
    │   • Naan Bread
    │   • Raita
    │   • Salad
    │   • Chutneys
    │
    └── COLUMN 4 - Desserts
        [Same structure]
        Items:
        • Gulab Jamun
        • Rasmalai
        • Kheer
        • Mango Kulfi
```

---

### Section 5: Event Types

#### Container Settings:
- Layout: Boxed (1200px)
- Background: White
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Perfect For Every Occasion"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── GRID CONTAINER (4 Columns, then another 4 columns)
    │
    First Row:
    ├── Icon Box Widget - Birthday Parties
    │   Icon: 🎉 or fa-birthday-cake
    │   Title: "Birthday Parties"
    │
    ├── Icon Box Widget - Corporate Events
    │   Icon: 💼 or fa-briefcase
    │   Title: "Corporate Events"
    │
    ├── Icon Box Widget - Weddings
    │   Icon: 💒 or fa-ring
    │   Title: "Wedding Receptions"
    │
    └── Icon Box Widget - House Parties
        Icon: 🎂 or fa-home
        Title: "House Parties"

    Second Row:
    ├── Icon Box Widget - Anniversary
    ├── Icon Box Widget - Office Lunches
    ├── Icon Box Widget - Religious Ceremonies
    └── Icon Box Widget - Graduation Parties

    Styling for all:
    ├── Background: White
    ├── Border: 1px solid light gray
    ├── Border radius: 12px
    ├── Padding: 30px
    ├── Icon size: 64px
    ├── Icon color: Maroon with golden accent
    ├── Center aligned
    └── Hover: Shadow effect
```

---

### Section 6: Service Options

#### Container Settings:
- Layout: Boxed (1200px)
- Background: Light gray (#F5F5F5)
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Flexible Service Options"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── GRID CONTAINER (2x2 Grid)
    │
    ├── Icon Box Widget - Drop-off
    │   Icon: 🍱 or fa-box (golden)
    │   Title: "DROP-OFF"
    │   Description: "Food delivered hot and ready in
    │                serving containers. Most economical option."
    │
    ├── Icon Box Widget - Full Service
    │   Icon: 👨‍🍳 or fa-concierge-bell (golden)
    │   Title: "FULL SERVICE"
    │   Description: "Complete setup with staff serving
    │                and clearing up. Premium experience."
    │
    ├── Icon Box Widget - Buffet Setup
    │   Icon: 🍛 or fa-utensils (golden)
    │   Title: "BUFFET SETUP"
    │   Description: "We set up buffet station with heating
    │                equipment. You manage serving."
    │
    └── Icon Box Widget - Custom Menus
        Icon: 🎨 or fa-palette (golden)
        Title: "CUSTOM MENUS"
        Description: "Work with our chef to create a
                     personalized menu for your event."

    Card Styling:
    ├── Background: White
    ├── Border: 1px solid #E0E0E0
    ├── Border radius: 12px
    ├── Padding: 40px
    ├── Icon at top: 80px
    ├── Title: 20px, bold, maroon
    ├── Description: 16px, line height 1.6
    └── Equal height columns
```

---

### Section 7: How It Works Timeline

#### Container Settings:
- Layout: Boxed (1200px)
- Background: White
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Simple Booking Process"
│   Alignment: Center
│   Bottom Margin: 80px
│
└── GRID CONTAINER (4 Columns - Horizontal on Desktop, Vertical on Mobile)
    │
    ├── Step 1
    │   └── Icon Box Widget
    │       Number Badge: "1"
    │       Style: Golden circle (80px)
    │       Title: "Contact Us"
    │       Description: "Submit your enquiry with event details"
    │       Arrow: → (between steps, desktop only)
    │
    ├── Step 2
    │   Number Badge: "2"
    │   Title: "Get Quote"
    │   Description: "Receive customized quote within 24 hours"
    │
    ├── Step 3
    │   Number Badge: "3"
    │   Title: "Confirm"
    │   Description: "Finalize menu and make payment"
    │
    └── Step 4
        Number Badge: "4"
        Title: "Enjoy!"
        Description: "We deliver amazing food"

    Styling:
    ├── Number badge: Golden background, white text
    ├── Title: 20px, bold, maroon
    ├── Description: 14px, gray
    ├── Center aligned
    └── Arrow widget between steps (Desktop only)
```

**Arrow Between Steps (Desktop):**
- Use Divider widget rotated or Icon widget
- Icon: fa-arrow-right
- Color: Secondary
- Size: 32px
- Position: Center vertically
- Hide on tablet/mobile

---

### Section 8: Testimonials

#### Container Settings:
- Layout: Boxed (1200px)
- Background: Light cream (#F8F5F0)
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "What Our Catering Clients Say"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── Testimonial Widget or GRID (2 Columns)
    │
    ├── Testimonial Card 1
    │   │
    │   └── CONTAINER
    │       Background: White
    │       Border radius: 12px
    │       Padding: 40px
    │       Box shadow: 0 2px 12px rgba(0,0,0,0.1)
    │
    │       ├── Star Rating Widget
    │       │   Stars: 5
    │       │   Color: Golden
    │       │
    │       ├── Text Editor Widget (Quote)
    │       │   Text: "Catered our office Diwali party for
    │       │         80 people. The food was outstanding
    │       │         and arrived on time. Everyone loved
    │       │         the butter chicken!"
    │       │   Typography: 16px, italic
    │       │
    │       └── Heading Widget (Author)
    │           Text: "- Sarah, HR Manager"
    │           Typography: 14px, bold
    │           Color: Gray
    │
    └── Testimonial Card 2
        [Same structure]
        Quote: "Perfect for my daughter's wedding.
               Professional service, authentic taste.
               150 guests all happy!"
        Author: "- Rajesh Kumar"
```

---

### Section 9: Catering Enquiry Form (MAIN FEATURE)

#### Container Settings:
- Layout: Boxed (700px max-width)
- Background: Gradient (light gray to white)
- Padding: 120px 40px

```
CONTAINER (Center aligned)
│
├── Heading Widget
│   Text: "Request a Catering Quote"
│   HTML Tag: H2
│   Color: Primary
│   Typography: 36px, Poppins, bold
│   Alignment: Center
│
├── Text Editor Widget
│   Text: "Tell us about your event and we'll get back
│          to you within 24 hours"
│   Typography: 18px
│   Color: Gray
│   Alignment: Center
│   Bottom Margin: 40px
│
└── Form Widget (Elementor Pro)

    Container Styling:
    ├── Background: White
    ├── Border radius: 16px
    ├── Box shadow: 0 4px 20px rgba(0,0,0,0.08)
    ├── Padding: 60px 50px
    └── Max-width: 700px

    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

    SECTION 1: YOUR DETAILS

    ├── Section Heading (HTML widget)
    │   "YOUR DETAILS"
    │   Typography: 14px, uppercase, bold
    │   Border bottom: 1px solid light gray
    │   Margin bottom: 30px
    │
    ├── Name Field *
    │   Field Type: Text
    │   Placeholder: "Full Name"
    │   Required: Yes
    │   Width: 100%
    │   Styling:
    │   ├── Height: 50px
    │   ├── Border radius: 8px
    │   ├── Border: 1px solid #E0E0E0
    │   ├── Padding: 14px 18px
    │   ├── Font size: 16px
    │   └── Focus: Golden border (#E8B44D)
    │
    ├── Email Field *
    │   Field Type: Email
    │   Placeholder: "Email Address"
    │   Required: Yes
    │   Validation: Email format
    │   [Same styling as Name]
    │
    ├── Phone Field *
    │   Field Type: Tel
    │   Placeholder: "Phone Number"
    │   Required: Yes
    │   [Same styling]
    │
    ├── Divider Widget
    │   Style: Solid line
    │   Color: #E0E0E0
    │   Margin: 40px vertical
    │
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

    SECTION 2: EVENT DETAILS

    ├── Section Heading (HTML widget)
    │   "EVENT DETAILS"
    │   [Same styling as Section 1 heading]
    │
    ├── Event Type Field *
    │   Field Type: Select dropdown
    │   Placeholder: "Select Event Type"
    │   Options:
    │   ├── Birthday Party
    │   ├── Wedding Reception
    │   ├── Corporate Event
    │   ├── Anniversary
    │   ├── Religious Ceremony
    │   └── Other
    │   Required: Yes
    │
    ├── Event Date Field *
    │   Field Type: Date
    │   Placeholder: "DD/MM/YYYY"
    │   Min Date: Today
    │   Max Date: 1 year from today
    │   Date Format: DD/MM/YYYY
    │   Icon: Calendar icon (right side)
    │   Required: Yes
    │
    ├── Number of Guests Field *
    │   Field Type: Number
    │   Placeholder: "Number of Guests"
    │   Min: 20
    │   Max: 500
    │   Required: Yes
    │
    ├── Event Location Field *
    │   Field Type: Text
    │   Placeholder: "Event Location/Venue"
    │   Required: Yes
    │
    ├── Preferred Package Field
    │   Field Type: Radio buttons (horizontal)
    │   Options:
    │   ○ Bronze  ○ Silver  ○ Gold  ○ Custom
    │   Default: None selected
    │   Required: No
    │
    │   Radio Button Styling:
    │   ├── Custom styled (golden when selected)
    │   ├── Large clickable area (48px height)
    │   ├── Horizontal layout on desktop
    │   └── Stack vertically on mobile
    │
    ├── Service Type Field
    │   Field Type: Radio buttons (horizontal)
    │   Options:
    │   ○ Drop-off  ○ Buffet Setup  ○ Full Service
    │   [Same styling as Preferred Package]
    │
    ├── Divider Widget
    │   [Same as previous divider]
    │
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

    SECTION 3: ADDITIONAL INFORMATION

    ├── Section Heading (HTML widget)
    │   "ADDITIONAL INFORMATION"
    │   [Same styling]
    │
    ├── Dietary Requirements Field
    │   Field Type: Checkbox (multiple selection)
    │   Label: "Dietary Requirements (Optional)"
    │   Options:
    │   ☐ Vegetarian Only
    │   ☐ Vegan Options
    │   ☐ Nut-Free
    │   ☐ Gluten-Free
    │   ☐ Halal
    │   Required: No
    │
    │   Checkbox Styling:
    │   ├── Custom checkboxes
    │   ├── Green checkmark when selected
    │   ├── Wrap to multiple lines
    │   └── Adequate spacing between options
    │
    ├── Additional Notes Field
    │   Field Type: Textarea
    │   Placeholder: "Any special requests or additional
    │                 information..."
    │   Rows: 4
    │   Max length: 500 characters
    │   Required: No
    │   Styling:
    │   ├── Min height: 120px
    │   ├── Resizable: Vertical only
    │   └── Same border styling as inputs
    │
    ├── Divider Widget
    │   [Same style]
    │
    ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

    SUBMIT SECTION

    ├── Submit Button
    │   Text: "SUBMIT ENQUIRY"
    │   Type: Submit
    │   Width: 100%
    │   Styling:
    │   ├── Background: Golden (#E8B44D)
    │   ├── Color: Dark brown (#3D1F1F)
    │   ├── Height: 56px
    │   ├── Border radius: 8px
    │   ├── Font size: 18px
    │   ├── Font weight: 600
    │   ├── Letter spacing: 0.5px
    │   ├── Uppercase: Yes
    │   └── Box shadow: 0 4px 12px rgba(232,180,77,0.3)
    │
    │   Hover:
    │   ├── Background: #D4A03D (darker golden)
    │   ├── Transform: translateY(-2px)
    │   └── Box shadow: 0 6px 16px rgba(232,180,77,0.4)
    │
    │   Loading State:
    │   ├── Disable button
    │   ├── Show spinner icon
    │   └── Opacity: 0.7
    │
    └── Icon List Widget (Security note)
        Items:
        └── 🔒 Your information is secure and confidential
        Typography: 12px, gray
        Alignment: Center
        Top margin: 20px

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FORM ACTIONS & SETTINGS:

After Submit:
├── Action: Email
│   To: restaurant@orpingtonrasoi.co.uk
│   From: Form submitter email
│   Subject: "New Catering Enquiry - {event_type}"
│   Email Template: Include all form fields
│
├── Action: Email (Customer confirmation)
│   To: Customer email
│   Subject: "Catering Enquiry Received - Orpington Rasoi"
│   Message: Thank you message with enquiry details
│
├── Action: Redirect (optional)
│   Redirect to: Thank you page
│   Or show success message inline
│
└── Success Message:
    "✅ Enquiry Submitted!

    Thank you for your interest! We'll review your
    requirements and send you a detailed quote within
    24 hours.

    Confirmation sent to: {email}

    [BACK TO HOME button]"

Validation:
├── Real-time validation on blur
├── Error messages in red below fields
├── Success state: Green border
├── Required field indicator: Red asterisk (*)
└── Form-level validation before submit
```

---

### Section 10: FAQ (Accordion)

#### Container Settings:
- Layout: Boxed (900px)
- Background: White
- Padding: 100px 40px

```
CONTAINER
│
├── Heading Widget
│   Text: "Frequently Asked Questions"
│   Alignment: Center
│   Bottom Margin: 60px
│
└── Accordion Widget (Elementor Pro) or Toggle Widget

    Item 1:
    ├── Title: "What's the minimum number of guests?"
    │   Icon: fa-chevron-down
    │   Icon position: Right
    │
    └── Content: "Bronze package starts at 20 guests.
                  For smaller groups, please use our
                  regular takeaway menu."

    Item 2:
    ├── Title: "How far in advance should I book?"
    └── Content: "We recommend 2-3 weeks for small events,
                  4-6 weeks for large events or weddings."

    Item 3:
    ├── Title: "Do you provide serving staff?"
    └── Content: "Yes, full service option includes
                  professional staff for setup, serving,
                  and cleanup."

    Item 4:
    ├── Title: "Can you accommodate dietary restrictions?"
    └── Content: "Absolutely! We can customize menus for
                  vegetarian, vegan, gluten-free, nut-free,
                  and other requirements."

    Item 5:
    ├── Title: "What's included in the price?"
    └── Content: "All prices include food, disposable
                  plates/cutlery, and basic delivery.
                  Full service adds staff and equipment."

    Item 6:
    ├── Title: "Do you do tastings before events?"
    └── Content: "Yes! For large events (100+ guests),
                  we offer tastings to help you select
                  your menu."

    Accordion Styling:
    ├── Background: Alternating (white, light cream)
    ├── Border radius: 8px
    ├── Padding: 20px
    ├── Margin between items: 10px
    ├── Title color: Maroon
    ├── Title typography: 18px, bold
    ├── Content color: Dark brown
    ├── Content typography: 16px, line height 1.6
    ├── Icon color: Golden when open
    └── Transition: Smooth expand/collapse (0.3s)
```

---

### Section 11: Bottom CTA

#### Container Settings:
- Layout: Full Width
- Background: Maroon (#5C1A1A)
- Background Overlay: Food pattern texture (30% opacity)
- Padding: 120px 40px

```
CONTAINER (Boxed, 800px, Center aligned)
│
├── Heading Widget
│   Text: "Ready to Plan Your Event?"
│   HTML Tag: H2
│   Color: White
│   Typography: 42px, Poppins, bold
│   Alignment: Center
│   Bottom Margin: 20px
│
├── Text Editor Widget
│   Text: "Let's create an unforgettable dining
│          experience for you and your guests"
│   Color: Secondary (#E8B44D)
│   Typography: 20px
│   Alignment: Center
│   Bottom Margin: 40px
│
└── CONTAINER (Flex, Horizontal, Center, Gap: 20px)
    │
    ├── Button Widget - Primary
    │   Text: "GET A QUOTE"
    │   Link: Scroll to form (#catering-form)
    │   Style: Primary button (golden)
    │   Size: Large
    │   Icon: fa-arrow-down
    │
    └── Button Widget - Secondary
        Text: "CALL US NOW"
        Link: tel:[phone-number]
        Style: Outline button (white border)
        Size: Large
        Icon: fa-phone
```

---

## 📍 DELIVERY INFO PAGE

```
CONTAINER (Boxed, 1200px)
├── Padding: 100px 40px
│
└── GRID (2 Columns)
    │
    ├── COLUMN 1
    │   │
    │   ├── Heading: "Delivery Areas"
    │   │   Icon: Location pin
    │   │
    │   ├── Icon List Widget
    │   │   Items:
    │   │   ├── ✓ BR5 - Orpington
    │   │   ├── ✓ BR6 - Locksbottom
    │   │   ├── ✓ BR2 - Bromley South
    │   │   └── ✓ BR1 - Bromley
    │   │
    │   ├── Heading: "Delivery Charges"
    │   │
    │   ├── Pricing Table Widget
    │   │   ├── Free: Orders over £25
    │   │   └── £3.50: Orders under £25
    │   │
    │   └── Heading: "Minimum Order"
        │   Text: "£10 minimum for delivery"
    │
    └── COLUMN 2
        │
        ├── Heading: "Delivery Times"
        │
        ├── Icon List Widget
        │   ├── Monday - Sunday
        │   ├── 5:00 PM - 10:00 PM
        │   └── Last orders: 9:30 PM
        │
        ├── Heading: "Estimated Time"
        │   Text: "30-45 minutes from confirmation"
        │
        └── Heading: "Collection Available"
            Text: "Ready in 15-20 minutes"
            Text: "No minimum order"
```

---

## 📞 CONTACT PAGE

```
CONTAINER (Boxed, 1200px)
├── Padding: 100px 40px
│
└── GRID (2 Columns)
    │
    ├── COLUMN 1 (Contact Form)
    │   │
    │   └── Form Widget (Elementor Pro)
    │       Fields:
    │       ├── Name (Required)
    │       ├── Email (Required)
    │       ├── Phone (Optional)
    │       ├── Subject (Dropdown)
    │       └── Message (Textarea)
    │
    │       Submit Button:
    │       ├── Text: "SEND MESSAGE"
    │       └── Style: Primary button
    │
    │       After Submit:
    │       Success message: "Thank you! We'll respond within 24 hours"
    │       Email to: Restaurant email
    │
    └── COLUMN 2 (Contact Info)
        │
        └── CONTAINER
            Background: Light cream
            Border radius: 12px
            Padding: 40px

            Widgets:
            ├── Heading: "CONTACT INFO"
            │
            ├── Icon List Widget
            │   Items:
            │   ├── 📍 Address: Orpington, London
            │   ├── 📞 Phone: [Phone Number]
            │   ├── ✉️ Email: [Email]
            │   └── ⏰ Hours: Mon-Sun: 5PM-10PM
            │
            └── Social Icons Widget
                Icons:
                ├── Facebook
                ├── Instagram
                └── Twitter
                Color: Primary
                Size: 32px

CONTAINER (Full Width, Below)
├── Padding: 60px 0
│
└── Google Maps Widget (Elementor Pro)
    Height: 400px
    Zoom: 15
    Location: [Restaurant address]
    Style: Custom (match brand colors)
```

---

## 🏗️ FOOTER TEMPLATE (THEME BUILDER)

**Elementor → Theme Builder → Footer → Add New**

```
CONTAINER (Full Width)
├── Background: Dark maroon (#3D1F1F)
├── Color: White
├── Padding: 80px 40px 40px 40px
│
└── CONTAINER (Boxed, 1200px)
    │
    ├── GRID (4 Columns - Desktop, 2 - Tablet, 1 - Mobile)
    │   │
    │   ├── COLUMN 1 (About)
    │   │   ├── Image Widget (Logo - white version)
    │   │   │   Width: 160px
    │   │   │
    │   │   ├── Text Editor Widget
    │   │   │   Text: "Authentic Indian Takeaway"
    │   │   │   "Serving Orpington with love since [year]"
    │   │   │   Color: Light gray
    │   │   │
    │   │   └── Social Icons Widget
    │   │       ├── Facebook
    │   │       ├── Instagram
    │   │       └── Twitter
    │   │       Style: Circle, golden background
    │   │
    │   ├── COLUMN 2 (Quick Links)
    │   │   ├── Heading Widget
    │   │   │   Text: "QUICK LINKS"
    │   │   │   Color: Secondary
    │   │   │   Typography: 16px, uppercase
    │   │   │
    │   │   └── Nav Menu Widget
    │   │       Menu: Footer Menu
    │   │       Layout: Vertical
    │   │       Items:
    │   │       ├── Menu
    │   │       ├── About Us
    │   │       ├── Delivery Info
    │   │       ├── Privacy Policy
    │   │       └── Terms & Conditions
    │   │
    │   │       Link color: Light gray
    │   │       Hover color: Secondary
    │   │
    │   ├── COLUMN 3 (Contact)
    │   │   ├── Heading Widget
    │   │   │   Text: "CONTACT US"
    │   │   │   Color: Secondary
    │   │   │
    │   │   └── Icon List Widget
    │   │       Items:
    │   │       ├── 📍 Orpington, London
    │   │       ├── 📞 [Phone]
    │   │       └── ✉️ [Email]
    │   │
    │   │       Icon color: Secondary
    │   │       Text color: Light gray
    │   │
    │   └── COLUMN 4 (Hours)
    │       ├── Heading Widget
    │       │   Text: "OPENING HOURS"
    │       │   Color: Secondary
    │       │
    │       └── Text Editor Widget
    │           Content:
    │           Monday - Sunday
    │           5:00 PM - 10:00 PM
    │
    │           Last orders: 9:30 PM
    │           Color: Light gray
    │
    ├── Divider Widget
    │   Color: White, 20% opacity
    │   Margin: 40px 0
    │
    └── CONTAINER (Copyright - Center aligned)
        Text: "© 2025 Orpington Rasoi. All rights reserved."
        Color: Light gray
        Typography: 14px
```

---

## 🎨 FLOATING WIDGETS

### 1. Floating Cart Widget (Bottom Right)

**Create using Elementor Popup:**

```
POPUP (Type: Bottom Right)
├── Trigger: Always visible
├── Close: Never auto-close
├── Position: Bottom right, 20px from edges
│
└── Content:
    CONTAINER
    ├── Background: Secondary (#E8B44D)
    ├── Border radius: 50px
    ├── Padding: 15px 25px
    ├── Shadow: Large
    ├── Cursor: Pointer
    ├── Link: Cart page
    │
    └── FLEX Container (Horizontal)
        ├── Icon Widget
        │   Icon: Shopping cart
        │   Color: Primary
        │   Size: 24px
        │
        ├── Badge Widget (Dynamic)
        │   Content: {{cart_count}}
        │   Background: Primary
        │   Color: White
        │   Border radius: Circle
        │   Position: Absolute top-right
        │
        └── Text Widget
            Content: £{{cart_total}}
            Color: Primary
            Typography: 16px, bold

Animation:
├── Entrance: Bounce in
├── Hover: Scale 1.05
└── When item added: Shake animation
```

### 2. Floating "Order Now" Button (Mobile)

**Mobile only (<768px), Bottom of screen:**

```
POPUP (Type: Bottom Bar)
├── Show on: Mobile only
├── Position: Bottom, full width
├── Sticky: Yes
│
└── Button Widget
    Text: "ORDER NOW"
    Style: Primary button
    Link: Menu page
    Full width
    Padding: 18px
    Fixed at bottom
```

---

## 🎯 CUSTOM CSS FOR POLISH

Add to **Elementor → Custom CSS:**

```css
/* Smooth scrolling */
html {
    scroll-behavior: smooth;
}

/* Selection color */
::selection {
    background: #E8B44D;
    color: #3D1F1F;
}

/* Product hover effects */
.elementor-product {
    transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}

.elementor-product:hover {
    transform: translateY(-8px);
}

/* Button loading state */
.elementor-button.loading {
    pointer-events: none;
    opacity: 0.6;
}

.elementor-button.loading::after {
    content: "";
    width: 16px;
    height: 16px;
    margin-left: 10px;
    border: 2px solid #fff;
    border-top-color: transparent;
    border-radius: 50%;
    display: inline-block;
    animation: spin 0.6s linear infinite;
}

@keyframes spin {
    to { transform: rotate(360deg); }
}

/* Toast notification */
.added-to-cart-notification {
    position: fixed;
    top: 100px;
    right: 20px;
    background: #2D7A3E;
    color: white;
    padding: 16px 24px;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    z-index: 9999;
    animation: slideInRight 0.3s ease;
}

@keyframes slideInRight {
    from {
        transform: translateX(400px);
        opacity: 0;
    }
    to {
        transform: translateX(0);
        opacity: 1;
    }
}

/* Skeleton loading */
.skeleton {
    background: linear-gradient(
        90deg,
        #f0f0f0 25%,
        #e0e0e0 50%,
        #f0f0f0 75%
    );
    background-size: 200% 100%;
    animation: loading 1.5s infinite;
}

@keyframes loading {
    0% { background-position: 200% 0; }
    100% { background-position: -200% 0; }
}

/* Focus visible for accessibility */
*:focus-visible {
    outline: 2px solid #E8B44D;
    outline-offset: 2px;
}

/* Responsive image optimization */
img {
    max-width: 100%;
    height: auto;
}

/* Custom scrollbar */
::-webkit-scrollbar {
    width: 10px;
}

::-webkit-scrollbar-track {
    background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
    background: #E8B44D;
    border-radius: 5px;
}

::-webkit-scrollbar-thumb:hover {
    background: #D4A03D;
}
```

---

## 📱 MOBILE OPTIMIZATION CHECKLIST

### Performance:
- [ ] Enable lazy loading for all images
- [ ] Compress images to WebP format
- [ ] Minify CSS/JS in Elementor settings
- [ ] Use mobile-optimized breakpoints
- [ ] Test on real devices (iOS & Android)

### UX:
- [ ] Touch targets minimum 48px
- [ ] Readable font sizes (minimum 14px)
- [ ] Sticky header on mobile
- [ ] Hamburger menu working smoothly
- [ ] Forms easy to fill on mobile
- [ ] Checkout process streamlined

### Layout:
- [ ] All sections stack properly
- [ ] Images scale correctly
- [ ] No horizontal scroll
- [ ] Buttons full-width on mobile
- [ ] Cards in single column

---

## 🚀 LAUNCH CHECKLIST

### Pre-Launch:
- [ ] All pages built and tested
- [ ] Products imported and configured
- [ ] Images optimized (<200KB each)
- [ ] Forms tested and working
- [ ] Payment gateway tested
- [ ] Delivery zones configured
- [ ] Email notifications working
- [ ] Mobile responsive tested
- [ ] Cross-browser tested
- [ ] SEO titles/descriptions added
- [ ] Google Analytics installed
- [ ] SSL certificate active
- [ ] Backup system in place

### Post-Launch:
- [ ] Monitor order flow
- [ ] Test customer journey
- [ ] Check page load speeds
- [ ] Review error logs
- [ ] Gather user feedback
- [ ] Make iterative improvements

---

This comprehensive Elementor guide provides step-by-step instructions for building every page of your Orpington Rasoi website with pixel-perfect detail and professional polish!
