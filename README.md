Copyright © 2024 Prajith Puthankulam. All rights reserved.

# Royal Taste Food Products Website

A beautiful e-commerce website for authentic Kerala traditional food products built with React, TypeScript, Vite, and Hono.

## Features

- 🛒 Full shopping cart system
- 📱 WhatsApp order integration
- 🔍 Product quick view modal
- 💌 Contact form with database storage
- 📧 Newsletter signup
- 🎨 Beautiful responsive design
- 🌟 28 traditional Kerala products across 4 categories
- 📊 Contact form submissions management
- 🔐 Secure form validation and rate limiting

## Tech Stack

- **Frontend**: React 19, TypeScript, Tailwind CSS
- **Backend**: Hono.js
- **Database**: Vercel Postgres (production), SQLite (local development)
- **Build Tool**: Vite
- **Deployment**: Vercel

## Local Development Setup

### Prerequisites

- Node.js 18+ installed
- npm or yarn package manager

### Step 1: Clone and Install Dependencies

```bash
# Clone the repository (or download the source code)
git clone <your-repo-url>
cd royal-taste-foods

# Install dependencies
npm install

# Install additional dependencies for local development
npm install better-sqlite3 @types/better-sqlite3 --save-dev
```

### Step 2: Environment Setup

Create a `.env.local` file in the root directory:

```env
# Local development environment
NODE_ENV=development
VITE_API_URL=http://localhost:5173/api

# Optional: Add your actual WhatsApp number
VITE_WHATSAPP_NUMBER=919876543210

# Contact form notifications (optional)
CONTACT_NOTIFICATION_EMAIL=your-email@example.com
```

### Step 3: Database Setup

The app will automatically create a local SQLite database when you run it for the first time. The database file will be created as `local.db` in your project root.

### Step 4: Run Development Server

```bash
npm run dev
```

Your app will be available at `http://localhost:5173`

### Step 5: Build for Production

```bash
npm run build
```

## Deployment to Vercel

### Step 1: Prepare for Deployment

1. Make sure your code is pushed to a Git repository (GitHub, GitLab, or Bitbucket)

2. Install Vercel CLI (optional, but recommended):
```bash
npm install -g vercel
```

### Step 2: Deploy to Vercel

#### Option A: Using Vercel Dashboard

1. Go to [vercel.com](https://vercel.com) and sign up/log in
2. Click "New Project"
3. Import your Git repository
4. Vercel will automatically detect it's a Vite project
5. Configure environment variables in the Vercel dashboard:
   - Add any environment variables you need
   - Set `NODE_ENV=production`
6. Deploy!

#### Option B: Using Vercel CLI

```bash
# Login to Vercel
vercel login

# Deploy (from your project directory)
vercel

# Follow the prompts:
# - Link to existing project or create new one
# - Confirm settings
# - Deploy!
```

### Step 3: Environment Variables on Vercel

In your Vercel dashboard, go to Project Settings > Environment Variables and add:

```
NODE_ENV=production
VITE_WHATSAPP_NUMBER=your_actual_whatsapp_number
CONTACT_NOTIFICATION_EMAIL=your-email@example.com
```

**Important Notes:**
- `VITE_WHATSAPP_NUMBER`: Your business WhatsApp number (without + or country code)
- `CONTACT_NOTIFICATION_EMAIL`: Email for receiving contact form notifications (optional)

### Step 4: Set Up Vercel Postgres Database

1. **In Vercel Dashboard:**
   - Go to Storage tab
   - Click "Create Database"
   - Select "Postgres"
   - Choose your region
   - Click "Create"

2. **Database Environment Variables:**
   - Vercel will automatically add these environment variables:
     - `POSTGRES_URL`
     - `POSTGRES_HOST`
     - `POSTGRES_DATABASE`
     - `POSTGRES_USERNAME`
     - `POSTGRES_PASSWORD`

3. **Database Schema:**
   - The contact_submissions table will be created automatically on first API call
   - No manual setup required

### Step 5: Custom Domain (Optional)

1. In Vercel dashboard, go to Project Settings > Domains
2. Add your custom domain
3. Follow the DNS configuration instructions

## Production Deployment Checklist

### 🔒 Security Setup (Required)

1. **Set Environment Variables in Vercel**
   ```
   NODE_ENV=production
   VITE_WHATSAPP_NUMBER=your_actual_whatsapp_number
   CONTACT_NOTIFICATION_EMAIL=your-email@example.com
   ```

### 🚀 Deployment Steps

1. **Deploy to Vercel**
   - Connect your GitHub repository
   - Deploy automatically

2. **Test Critical Functions**
   - Contact form submission
   - WhatsApp integration
   - Product catalog display
   - Shopping cart functionality

### 🔍 Post-Deployment Verification

- [ ] Contact form working
- [ ] WhatsApp button functional
- [ ] Rate limiting active
- [ ] Security headers present
- [ ] No console errors in production
- [ ] Product images loading correctly

## Project Structure

```
src/
├── react-app/              # Frontend React application
│   ├── components/         # Reusable UI components
│   ├── contexts/          # React contexts (Cart, etc.)
│   ├── hooks/             # Custom React hooks
│   ├── pages/             # Page components
│   └── main.tsx           # React app entry point
├── worker/                # Backend API (Hono.js)
│   └── index.ts           # API routes and handlers
└── shared/                # Shared types and utilities
    └── types.ts           # TypeScript type definitions
```

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally
- `npm run lint` - Run ESLint
- `npm run check` - Type check and build verification

## Features Overview

### Shopping Cart
- Add products to cart with quantity selection
- View cart with item management
- WhatsApp order integration with complete order details

### Product Catalog
- 28 authentic Kerala food products
- 4 categories: Puttupodi, Powders, Rava, Ready Mixes
- Quick view modal for product details
- Product filtering by category

### Contact & Communication
- Contact form with database storage
- Newsletter signup
- WhatsApp integration for quick orders
- Business information and location details

## Customization

### WhatsApp Number
Update the phone number in `src/react-app/components/WhatsAppButton.tsx`:

```typescript
phoneNumber = "9061854239",
```

### Business Information
Update company details in the page components under `src/react-app/pages/`

### Product Images
Replace placeholder images with actual product photos by updating the image URLs in the product data.

## Support

For any issues or questions, please check the documentation or create an issue in the repository.

## License

This project is proprietary software for Royal Taste Food Products.
