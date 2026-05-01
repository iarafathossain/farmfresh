# FarmFresh

## Introduction

**FarmFresh** is a web platform that connects farmers directly to customers, allowing them to sell their fresh farm products without any middlemen. It ensures transparency, fairness, and freshness for both farmers and consumers.

## UI/UX

The design of FarmFresh focuses on a farming-themed aesthetic combined with an e-commerce experience.

- The interface uses soothing green tones to reflect the freshness of agriculture.
- Both light and dark themes are included for accessibility.
- Every UI element clearly communicates its purpose, ensuring a smooth and intuitive user journey.
- Each process in the app is well-connected for a seamless experience.

## Features

### Farmer Features

- **Product Management**
  - Add products with title, description, images, discount, price, and more.
  - Update, edit, or delete existing products.
  - Activate/deactivate listed products easily.
  - Advanced filters and pagination for quick navigation.
- **Order Management**
  - View and track all product orders from the “My Orders” page.
  - Update order status (Placed → Confirmed → Shipped → Delivered).
  - Smart filters for quick order search.
- **Profile Management**
  - Edit profile details, including role and personal info.

### Customer Features

- **Cart Management**
  - Add, increment, decrement, and delete products from the cart.
  - Smart cart page to manage products and navigate to checkout.
  - Simulated payment process for order placement.
  - Orders can be canceled before farmer confirmation; canceled orders can be replaced.
  - Downloadable order receipt as a professional PDF including farmer and order details.

### Filtering and Searching

- Case-insensitive search for products by title and description.
- Filter products by price, category, features, and location.
- Sort products for better browsing experience.

### Review System

- Customers can review a product only once.
- Reviews are allowed only after the product is successfully delivered.

### Email Configuration

- Order confirmation emails.
- Order status update notifications.
- Password reset key emails.

### UI Navigation

The **Navbar** is common across all pages but adapts based on user login status.

- **If not logged in:** Show **Login** and **Signup** buttons.
- **If logged in as a Farmer:** Show menu items: `Home`, `Add Product`, `Manage Products`, `About`, `Logout`.
- **If logged in as a Customer:** Show menu items: `Home`, `Products`, `Farmers`, `My Orders`, `About`, `Logout`.

### Authentication

- Complete authentication flow with **Email** and **Google** credentials.
  - Login and Register using Email/Password or Google.
  - Password reset system with email confirmation.
  - Middleware-protected routes.
  - Refresh and Access Token setup for secure sessions.

## Project Structure

```text
src/
├── actions/          # Server actions for auth, products, and reviews
├── app/              # App Router pages, layouts, route handlers, and UI shells
├── auth.ts           # NextAuth configuration and handlers
├── auth.config.ts    # Shared auth configuration
├── components/       # Reusable UI and feature components
├── config/           # Centralized environment configuration
├── context/          # React context helpers
├── data/             # Static or seed-like data
├── hooks/            # Custom React hooks
├── libs/             # Database, cloud, and third-party helpers
├── middleware.ts     # Route protection and middleware logic
├── models/           # Mongoose models
├── providers/        # Client providers and app-level wrappers
├── queries/          # Read/query helpers for database access
├── reducers/         # Reducers for state management
├── services/         # Email and upload services
├── types/            # Shared TypeScript types
├── utils/            # Utility helpers
└── validations/      # Form and input validation helpers
```

## App Routing Structure

```text
src/app/
├── page.tsx                    # Home page
├── layout.tsx                  # Root layout and global providers
├── loading.tsx                 # Global loading UI
├── error.tsx                   # Global error boundary UI
├── not-found.tsx               # 404 page
├── about/page.tsx              # About page
├── add-product/page.tsx        # Farmer-only add product page
├── cart/page.tsx               # Cart page
├── farmers/page.tsx            # Public farmers listing page
├── forgot-password/page.tsx    # Forgot password page
├── login/page.tsx              # Login page
├── manage-products/page.tsx    # Farmer product management page
├── my-orders/page.tsx          # Orders page for logged-in users
├── payment-process/page.tsx    # Payment and checkout flow
├── products/page.tsx           # Products listing and filtering page
├── products/[productId]/page.tsx        # Product details page
├── products/edit/[editProductId]/page.tsx # Edit product page
├── profile/page.tsx            # Profile page
├── register/page.tsx           # Registration page
├── reset-password/page.tsx     # Reset password page
├── reviews/page.tsx            # Reviews listing page
├── success/[orderId]/page.tsx   # Order success page
├── api/                        # Route handlers
│   ├── auth/[...nextauth]/route.ts
│   ├── cart/route.ts
│   ├── favorite/route.ts
│   ├── og/route.ts
│   └── send-email/
│       ├── order-invoice/route.ts
│       ├── order-status-update/route.ts
│       ├── send-reset-password/route.ts
│       └── send-reset-success/route.ts
├── @authInterceptedModel/      # Intercepted auth modal route segment
│   ├── default.tsx
│   ├── (.)login/
│   └── (.)register/
```

## Page Access and Functionality

- Only farmer-type users can access the **Add Product** page to create new products.
- Farmers can manage their products using the **Manage Products** page - edit, publish/unpublish, delete, search, or filter items.
- All users, including guests, can view registered farmers on the **Farmers** page.
- The **Cart** page supports product review, removal, and checkout-related actions.
- The **Reviews** page lists customer reviews and the **Product Details** page supports product-specific review actions.
- Proper handling of **Loading**, **Error**, and **Not Found** states is implemented.
- The **Home** and **Product Details** pages include SEO metadata for social sharing.
- Breadcrumb navigation is implemented across product and account flows.

## Tech Stack

- **Next.js 14 (with TypeScript):** Framework for building server-side rendered React applications.
- **Yarn:** Dependency manager for fast and reliable installations.
- **File-based Routing (Pages & API):** Automatic route generation for pages and API endpoints.
- **Server Actions:** Simplifies server-side data mutation.
- **React Icons:** Ready-to-use icons as React components.
- **React Toastify:** Provides toast notifications for user feedback.
- **Nodemailer (SMTP):** Handles email sending securely.
- **ESLint:** Ensures consistent code quality and formatting.
- **React PDF:** Generates PDF documents from React components.
- **Next Themes:** Enables dark and light theme toggling.
- **Next Auth:** Provides authentication using email, credentials, or Google.
- **bcryptjs:** Secure password hashing library.
- **Cloudinary:** Cloud-based image storage and optimization.

## How to Clone and Run the Project

Follow these steps to get started:

```bash
# 1. Copy one of the following repository URLs:

# HTTPS
https://github.com/iarafathossain/farmfresh.git

# 2. Clone the repository
git clone <your-selected-url>

# 3. Navigate to the project directory
cd farmfresh-reactive-accelerator-final-assignment-m11

# 4. Install dependencies
yarn

# 5. Start the development server
yarn run dev
```

© 2025 Arafat Hossain – All Rights Reserved.
