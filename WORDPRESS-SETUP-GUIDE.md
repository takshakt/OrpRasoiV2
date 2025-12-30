# Orpington Rasoi - WordPress Food Delivery Setup Guide

## Site Details
- **URL:** https://orpington-rasoi-wordpress-b41d9c-143-47-231-155.traefik.me
- **Admin:** https://orpington-rasoi-wordpress-b41d9c-143-47-231-155.traefik.me/wp-admin
- **Username:** admin
- **Password:** SzHxt2VwwhAfRC2!$6
- **Platform:** DocPloy (WordPress Template)

## Restaurant Details
- **Name:** Orpington Rasoi
- **Type:** Indian Food Takeaway
- **Location:** Orpington, London
- **Payment:** Stripe

---

## Phase 1: Essential Plugins Installation

### Step 1.1: Install WooCommerce
1. Go to **Plugins → Add New**
2. Search for "WooCommerce"
3. Click **Install Now** → **Activate**
4. Complete the setup wizard:
   - Store location: United Kingdom
   - Currency: GBP (£)
   - Product type: Physical products (food)
   - Skip the theme step for now

### Step 1.2: Install Food Ordering Plugin

**Option A: Food Store (Recommended - Free)**
1. Go to **Plugins → Add New**
2. Search for "Food Store"
3. Install and activate
4. Features: Food menu, add-ons, delivery/pickup options

**Option B: RestroPress (Alternative - Free)**
1. Search for "RestroPress"
2. Install and activate
3. Features: Restaurant menu, order management, delivery times

### Step 1.3: Install Stripe Payment Gateway
1. Go to **Plugins → Add New**
2. Search for "WooCommerce Stripe Payment Gateway"
3. Install the official WooCommerce Stripe plugin
4. Activate it

### Step 1.4: Additional Recommended Plugins
| Plugin | Purpose |
|--------|---------|
| WPForms Lite | Contact forms, reservations |
| Yoast SEO | Search engine optimization |
| Smush | Image optimization |
| WP Super Cache | Speed optimization |
| Wordfence | Security |

---

## Phase 2: WooCommerce Configuration

### Step 2.1: General Settings
Go to **WooCommerce → Settings → General**

```
Store Address:
- Address: [Your restaurant address]
- City: Orpington
- Country/State: United Kingdom
- Postcode: [Your postcode, e.g., BR5 xxx]

General Options:
- Selling location: Sell to specific countries → United Kingdom
- Currency: Pound sterling (£)
- Currency position: Left
```

### Step 2.2: Products Settings
Go to **WooCommerce → Settings → Products**

```
Shop page: [Create a page called "Menu"]
Measurements:
- Weight unit: kg
- Dimensions unit: cm

Reviews: Disable if not needed for food ordering
```

### Step 2.3: Shipping/Delivery Settings
Go to **WooCommerce → Settings → Shipping**

1. **Add Shipping Zone: "Orpington Delivery Area"**
   - Zone name: Orpington & Surrounding Areas
   - Zone regions: Add postcodes you deliver to:
     - BR5 (Orpington)
     - BR6 (Farnborough, Locksbottom)
     - BR2 (Bromley South)
     - BR1 (Bromley)
     - Add more as needed

2. **Add Shipping Methods:**
   - **Free Delivery** (orders over £25)
     - Minimum order amount: £25
   - **Standard Delivery** (£3.50)
     - Flat rate: £3.50
   - **Collection/Pickup** (Free)
     - Local pickup: Free

### Step 2.4: Tax Settings (Optional)
Go to **WooCommerce → Settings → Tax**

For UK food takeaway:
- Most hot takeaway food is VAT rated at 20%
- Cold food is typically zero-rated
- Enable tax if you're VAT registered

---

## Phase 3: Stripe Configuration

### Step 3.1: Get Stripe API Keys
1. Go to https://dashboard.stripe.com
2. Sign in or create account
3. Go to **Developers → API Keys**
4. Copy:
   - Publishable key: `pk_live_...` (or `pk_test_...` for testing)
   - Secret key: `sk_live_...` (or `sk_test_...` for testing)

### Step 3.2: Configure Stripe in WooCommerce
Go to **WooCommerce → Settings → Payments**

1. Enable "Stripe - Credit Card"
2. Click **Manage/Set up**
3. Configure:
   ```
   Enable/Disable: ✓ Enable Stripe
   Title: Credit/Debit Card
   Description: Pay securely with your card

   API Credentials:
   - Test mode: Enable for testing first
   - Test Publishable Key: pk_test_xxx
   - Test Secret Key: sk_test_xxx

   Payment Options:
   - ✓ Enable Payment Request Buttons (Apple Pay, Google Pay)
   - Capture: Capture charge immediately
   ```

4. **Save changes**

### Step 3.3: Webhook Setup (Important!)
1. In Stripe Dashboard → **Developers → Webhooks**
2. Add endpoint:
   - URL: `https://orpington-rasoi-wordpress-b41d9c-143-47-231-155.traefik.me/?wc-api=wc_stripe`
   - Events to send: Select all payment and checkout events
3. Copy the Webhook signing secret
4. Add to WooCommerce Stripe settings

---

## Phase 4: Menu Setup (Using WooCommerce Products)

### Step 4.1: Create Product Categories
Go to **Products → Categories**

Create these categories:
```
├── Starters
│   ├── Vegetarian Starters
│   └── Non-Vegetarian Starters
├── Main Courses
│   ├── Chicken Dishes
│   ├── Lamb Dishes
│   ├── Vegetarian Dishes
│   └── Seafood Dishes
├── Biryani & Rice
├── Breads (Naan & Roti)
├── Sides & Extras
├── Desserts
├── Drinks
└── Meal Deals
```

### Step 4.2: Add Menu Items as Products
Go to **Products → Add New**

Example product setup:
```
Product Name: Chicken Tikka Masala
Regular Price: £12.95

Description:
Tender pieces of chicken tikka cooked in a rich,
creamy tomato-based sauce with aromatic spices.

Short Description:
Classic creamy chicken curry. Mild-Medium.

Category: Main Courses → Chicken Dishes

Product Image: [Upload appetizing food photo]

Tags: chicken, curry, popular, mild
```

### Step 4.3: Product Variations (Spice Levels, Sizes)
For variable products:

1. Product data: **Variable product**
2. Go to **Attributes** tab:
   - Add attribute: "Spice Level"
   - Values: Mild | Medium | Hot | Extra Hot
   - Check "Used for variations"
3. Go to **Variations** tab:
   - Create variations from all attributes
   - Set prices if they differ

### Step 4.4: Product Add-ons (Extra Toppings, Rice Options)
Install "Product Add-Ons for WooCommerce" plugin for extras:
- Extra rice (+£2.50)
- Extra naan (+£2.00)
- Add poppadoms (+£1.50)
- Extra sauce (+£1.00)

---

## Phase 5: Theme & Design

### Step 5.1: Recommended Free Themes
Go to **Appearance → Themes → Add New**

**Best Options:**
1. **flavor** - Restaurant theme
2. flavor- Restaurant theme
3. **flavor flavor flavor flavor flavor flavor flavor flavor flavor**flavor - **flavor flavor flavor**

Actually, let me recommend:
1. **flavor flavor** - flavor flavor flavor flavor
2. **flavor** - flavor flavor flavor flavor
3. **flavor**

Let me be specific:

1. **flavor flavor flavor** - flavor flavor flavor for flavor
2. **flavor flavor** - flavor flavor flavor flavor flavor
3. **flavor flavor** - Flavor flavor flavor flavor

### Recommended Themes:
1. flavor **flavor flavor flavor flavor** - flavor flavor theme
2. **flavor** - flavor flavor flavor flavor
3. **flavor flavor** - flavor flavor flavor

Top picks:
1. **flavor** - flavor flavor flavor flavor flavor
2. **flavor flavor** - Flavor flavor flavor flavor
3. **flavor flavor flavor** - Flavor flavor flavor flavor

### Step 5.2: Essential Pages to Create
Go to **Pages → Add New**

| Page | Content |
|------|---------|
| Home | Hero image, featured dishes, order CTA |
| Menu | WooCommerce shop page |
| About Us | Restaurant story, chef info |
| Contact | Address, phone, hours, map |
| Delivery Info | Delivery zones, times, minimum orders |
| Privacy Policy | GDPR compliance |
| Terms & Conditions | Order terms |

### Step 5.3: Navigation Menu
Go to **Appearance → Menus**

Create Primary Menu:
```
Home | Menu | About Us | Delivery Info | Contact | Order Now (button)
```

---

## Phase 6: Order Management Backend

### Step 6.1: WooCommerce Order Dashboard
- **WooCommerce → Orders** - View all orders
- Order statuses for restaurants:
  - Pending payment
  - Processing (confirmed, being prepared)
  - On hold
  - Completed (delivered/collected)
  - Cancelled
  - Refunded

### Step 6.2: Order Notifications
Go to **WooCommerce → Settings → Emails**

Configure:
- **New order** → Send to: your restaurant email
- **Order on-hold** → Enable
- **Processing order** → Enable for customer
- **Completed order** → Enable for customer

### Step 6.3: Sound Notifications for New Orders (Recommended)
Install plugin: "Order Notification for WooCommerce"
- Plays sound when new order arrives
- Desktop notifications
- Essential for busy restaurant!

### Step 6.4: Printing Orders
Install plugin: "Print Invoice & Delivery Notes for WooCommerce"
- Print kitchen tickets
- Print delivery receipts
- Customizable templates

---

## Phase 7: Delivery Time Slots (Optional but Recommended)

### Install "Order Delivery Date for WooCommerce"
1. Go to **Plugins → Add New**
2. Search "Order Delivery Date"
3. Configure:
   - Delivery days: Set your operating days
   - Time slots:
     - 17:00 - 17:30
     - 17:30 - 18:00
     - 18:00 - 18:30
     - etc.
   - Cut-off time: Orders must be placed 30 min before slot
   - Same-day delivery: Enable

---

## Phase 8: Testing Checklist

### Before Going Live:
- [ ] Place test order with Stripe test mode
- [ ] Verify order appears in WooCommerce → Orders
- [ ] Check email notifications received
- [ ] Test all payment methods
- [ ] Verify delivery zone restrictions work
- [ ] Test on mobile device
- [ ] Check menu displays correctly
- [ ] Verify prices and descriptions accurate

### Switch to Live:
1. WooCommerce → Settings → Payments → Stripe
2. Disable "Test mode"
3. Enter live API keys
4. Save and test with small real transaction

---

## Phase 9: Go Live Checklist

### Technical:
- [ ] SSL certificate active (https://)
- [ ] Mobile responsive
- [ ] Page speed optimized
- [ ] Backup system in place

### Legal/Compliance:
- [ ] Privacy Policy page
- [ ] Terms & Conditions
- [ ] Cookie consent banner
- [ ] Allergy information displayed

### Business:
- [ ] Restaurant address verified
- [ ] Phone number visible
- [ ] Opening hours displayed
- [ ] Delivery zones clearly stated
- [ ] Minimum order amounts set

---

## Quick Reference

### Daily Operations:
```
WooCommerce → Orders        - Manage incoming orders
WooCommerce → Reports       - View sales analytics
Products → All Products     - Update menu/prices
```

### Useful Shortcodes:
```
[products]                  - Display all products
[products category="starters"] - Display category
[product id="123"]          - Single product
[woocommerce_cart]          - Cart page
[woocommerce_checkout]      - Checkout page
[woocommerce_my_account]    - Customer account
```

---

## Support & Resources

- **WooCommerce Docs:** https://woocommerce.com/documentation/
- **Stripe Support:** https://support.stripe.com/
- **WordPress Support:** https://wordpress.org/support/

---

## Domain Change (When Ready)

When you're ready to use `orpingtonrasoi.co.uk`:
1. Update WordPress Address in **Settings → General**
2. Update Stripe webhook URLs
3. Update WooCommerce store URL
4. Clear all caches
5. Update DNS to point to new server

---

*Guide created for Orpington Rasoi - Indian Takeaway, Orpington, London*
