# 🛍️ AuraCommerce — Next-Gen Luxury Full-Stack E-Commerce Platform

> **AuraCommerce** is an enterprise-grade, luxury full-stack e-commerce web application engineered with modern React, Vite, Express.js, and an ultra-refined Vanilla CSS design system. It features dynamic multi-currency support (Defaulting to **Indian Rupees ₹ INR**, with USD, EUR, and GBP), real-time inventory management, a slide-out cart drawer with free shipping progress meter, interactive checkout, order tracking milestones, and an integrated Merchant Admin Portal.

---

## ✨ Key Features

### 💎 Frontend Experience (React + Vite)
- **Dynamic Multi-Currency Engine**: Default active currency is **Indian Rupees (₹ INR)**, with an interactive switcher supporting USD ($), EUR (€), and GBP (£) with instant price recalibration across catalog, cart, checkout, and receipts.
- **Glassmorphism Navbar**: Sticky backdrop-blur navigation with brand glowing icon, live search with instant clear, quick category chips, wishlist counter badge, and animated cart counter.
- **Hero & Trust Architecture**: Luxury typography with animated pill badge, call-to-action buttons, and trust guarantees (Worldwide Courier, 2-Year Shield Guarantee, 30-Day Risk-Free Trial, 24/7 Concierge).
- **Interactive Catalog & Filters**:
  - Filter by category with live item counts.
  - Price range slider with real-time currency formatting.
  - Availability toggle ("In Stock Only").
  - Sorting: Featured, Price (Low to High), Price (High to Low), Top Rated, Most Reviewed.
  - Switch between Responsive Grid view and List view.
- **Product Quick View Modal**:
  - Multi-angle high-resolution gallery thumbnails.
  - Color finish swatches (e.g. Obsidian Black, Moonlight Silver, Nordic Dune).
  - Quantity counter with real-time subtotal calculation.
  - Urgency stock indicator badge.
  - 3 comprehensive tabs: *Overview & Guarantees*, *Engineering Specifications*, and *Collector Reviews*.
  - Verified review submission form with star rating.
- **Slide-Out Cart Drawer**:
  - Live Free Shipping threshold meter ("Add ₹X more to unlock Free Express Shipping").
  - Stepper controls to increment/decrement quantities or remove items.
  - Coupon code validation with instant feedback (`SAVE20`, `AURA10`, `WELCOME50`, `VIP30`).
  - Transparent price summary: Subtotal, Promo Discount, Express Shipping, Estimated Tax, and Grand Total.
- **3-Step Checkout Gateway**:
  - Step 1: Delivery contact and address fields (pre-filled or custom).
  - Step 2: Payment method (Credit Card with live 3D-styled card preview, UPI / NetBanking, Cash on Delivery).
  - Step 3: Order confirmation celebration screen with generated Order ID, BlueDart/DHL tracking number, and direct link to tracking.
- **Order Logistics & Tracking Hub**:
  - Visual status progress bar (1. Order Confirmed -> 2. Preparing at Atelier -> 3. In Express Transit -> 4. Delivered).
  - Comprehensive invoice breakdown, customer delivery details, and item thumbnails.
- **Wishlist Manager**:
  - 1-click save/unsave heart buttons with micro-animation.
  - "Move All To Bag" batch action.
- **Dark & Light Mode Engine**:
  - Instant toggle between sleek deep obsidian dark theme and crisp high-contrast light theme.

---

### 🛡️ Merchant Admin Portal
- Switch directly between the **Patron Store** and **Merchant Backoffice** with one click in the navbar.
- **Live Business KPIs**:
  - Gross Revenue (₹) with quarter trend indicators.
  - Total Order Fulfillments.
  - Average Order Value (AOV).
  - Total Active Stock & Low Stock Warnings.
- **Catalog Inventory Manager**:
  - View all products, ratings, and categories.
  - Add New Luxury Creation modal (publish directly to store).
  - Inline edit for pricing and stock quantity.
  - Delete product action with confirmation.
- **Fulfillment & Order Queue**:
  - Customer order list with items breakdown and payment method.
  - Live Status Controller dropdown (update order status between *Processing*, *Shipped*, and *Delivered* with instant persistence).

---

### 🚀 Backend REST API (Node.js & Express)
- **Modular Routes**:
  - `GET /api/products`: Filter by category, search term, min/max price, sorting, stock.
  - `GET /api/products/:id`: Fetch individual product details and reviews.
  - `POST /api/products`: Create new product (Admin).
  - `PUT /api/products/:id`: Update price and stock (Admin).
  - `DELETE /api/products/:id`: Remove product (Admin).
  - `POST /api/products/:id/reviews`: Add verified customer review.
  - `GET /api/categories`: Retrieve all categories and counts.
  - `POST /api/coupons/validate`: Validate promo codes and calculate discounts.
  - `GET /api/orders`: Retrieve all customer orders.
  - `POST /api/orders`: Place new order and auto-decrement inventory stock.
  - `PATCH /api/orders/:id/status`: Update fulfillment status.
  - `POST /api/auth/login` & `POST /api/auth/register`: Authentication engine.
  - `GET /api/analytics`: Aggregate real-time KPIs and sales statistics.
  - `GET /api/health`: Service health check endpoint.
- **Data Persistence**: Atomic, self-initializing JSON/SQLite database with 12 pre-seeded high-fidelity products, categories, active promo codes, and initial sample orders.

---

## 🛠️ Project Structure

```
AuraCommerce/
├── package.json               # Root scripts (concurrently runs client & server)
├── README.md                  # Comprehensive documentation
├── server/                    # Backend API
│   ├── package.json           # Express, CORS, dotenv
│   ├── server.js              # Server entry, routes, static hosting
│   ├── data/
│   │   ├── seedData.js        # Seed products, categories, coupons, orders
│   │   ├── store.js           # CRUD data layer & analytics calculation
│   │   └── db.json            # Persistent JSON database
│   └── routes/
│       ├── products.js        # Products REST endpoints
│       ├── categories.js      # Categories endpoint
│       ├── coupons.js         # Promo validation endpoint
│       ├── orders.js          # Orders & status endpoints
│       ├── auth.js            # Authentication endpoints
│       └── analytics.js       # Admin KPIs endpoint
└── client/                    # Frontend React + Vite
    ├── package.json           # React 18, Lucide React, Vite
    ├── vite.config.js         # Proxy configuration (/api -> port 5000)
    ├── index.html             # Google Fonts (Outfit, Plus Jakarta Sans), SEO
    └── src/
        ├── main.jsx           # React DOM root
        ├── App.jsx            # Routing and view coordination
        ├── index.css          # Vanilla CSS Luxury Design System
        ├── context/
        │   └── StoreContext.jsx # Global state (Cart, Wishlist, Theme, Currency ₹)
        ├── services/
        │   └── api.js         # Fetch client for all backend endpoints
        └── components/
            ├── Navbar.jsx
            ├── HeroBanner.jsx
            ├── ProductCatalog.jsx
            ├── ProductCard.jsx
            ├── ProductQuickViewModal.jsx
            ├── CartDrawer.jsx
            ├── CheckoutModal.jsx
            ├── OrdersView.jsx
            ├── WishlistView.jsx
            ├── AdminDashboard.jsx
            ├── AuthModal.jsx
            ├── NotificationToast.jsx
            └── Footer.jsx
```

---

## ⚡ Quick Start Guide

### 1. Installation
Install all dependencies for root, backend server, and frontend client with one command:
```bash
npm run install:all
```
*(Or install inside `server` and `client` directories with `npm install`)*

### 2. Run in Development Mode
Launch both the Express backend (`http://localhost:5000`) and the Vite React frontend (`http://localhost:5173`) concurrently:
```bash
npm run dev
```

### 3. Open the App in Your Browser
- **Frontend Store**: [http://localhost:5173](http://localhost:5173)
- **Backend API Health**: [http://localhost:5000/api/health](http://localhost:5000/api/health)

### 4. Build for Production
To build the frontend bundle into `client/dist`:
```bash
npm run build
```
Once built, you can run the standalone production server:
```bash
npm start
```
The Express server will automatically serve both the REST API and the optimized React frontend on `http://localhost:5000`!

---

## 🔑 Demo Accounts & Promo Codes

### Demo Login Accounts (1-Click Fill in Sign In Modal):
- **Store Admin**: `admin@aura.com` / `admin`
- **Customer Patron**: `alex@aura.com` / `password123`

### Active Promo Codes (Try in Cart Drawer):
- **`SAVE20`**: 20% off entire order on purchases over ₹12,975 ($150)
- **`AURA10`**: 10% off entire order on purchases over ₹4,325 ($50)
- **`WELCOME50`**: Flat ₹4,325 ($50) discount on orders over ₹17,300 ($200)
- **`VIP30`**: 30% off for VIP patrons on orders over ₹25,950 ($300)

---

## 📜 License
MIT License. Built for high-performance e-commerce experiences.
