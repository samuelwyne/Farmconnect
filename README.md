🌾 FarmConnect - README

Smart Farming & E-Commerce Platform for Ugandan Agriculture

---

📋 Table of Contents

1. Project Overview
2. Features
3. Technology Stack
4. Installation Guide
5. Usage Guide
6. User Roles
7. Database Structure
8. API Endpoints
9. Deployment Guide
10. Testing Accounts
11. Troubleshooting
12. Future Roadmap
13. Contributing
14. License

---

🚀 Project Overview

FarmConnect is a comprehensive web-based platform that connects Ugandan farmers directly with buyers, eliminating middlemen and ensuring fair prices for both parties. The platform includes smart farming tools, real-time chat (text, voice, and images), order tracking, payment processing, and agricultural advisory services.

Problem Solved

· Farmers struggle to find markets for their produce
· Buyers pay inflated prices due to middlemen
· Lack of transparent pricing information
· No direct communication channel between farmers and buyers
· Limited access to agricultural advice and market data

Solution

FarmConnect provides a one-stop platform where farmers can list their products, buyers can purchase directly, and both parties can communicate seamlessly while accessing valuable farming insights.

---

✨ Features

👨‍🌾 Farmer Features

Feature Description Status
Product Management Add, edit, delete products with images ✅
Order Management View incoming orders, mark as shipped ✅
Revenue Tracking View total earnings and sales analytics ✅
Chat System Text, voice, and image messaging with buyers ✅
Smart Farming Tools AI advisor, market prices, weather alerts ✅
Profile Management Edit personal and farm information ✅

🛒 Buyer Features

Feature Description Status
Product Browsing Search and filter products by category ✅
Order Placement Buy products with delivery address ✅
Payment Processing Mobile money (M-PESA/Airtel) and card ⚠️ Demo
Order Tracking Track order status in real-time ✅
Ratings & Reviews Rate products after delivery ✅
Wishlist Save favorite products for later ✅
Chat System Communicate directly with farmers ✅

👑 Authority Features

Feature Description Status
User Management Approve/reject new user registrations ✅
Revenue Analytics View platform revenue and subscriptions ✅
Ad Management Manage featured advertisements ✅
User Monitoring Track active farmers and buyers ✅

🌱 Smart Farming Tools

Tool Description
AI Farm Advisor Planting tips, pest control advice
Live Market Prices Real-time commodity prices in Uganda
Weather Advisory 3-day farming forecast
Aflatoxin Alert Harvest safety and storage tips
Crop Disease Doctor Diagnose common crop diseases
Fertilizer Calculator Calculate fertilizer requirements

---

🛠 Technology Stack

Frontend

Technology Purpose
HTML5 Structure
CSS3 Styling & Responsive Design
JavaScript (ES6+) Interactivity & Logic
Chart.js Analytics & Data Visualization
CryptoJS Password Hashing

Storage

Technology Purpose
LocalStorage Client-side data persistence (demo)

APIs & Integrations

Service Purpose
Chart.js Analytics charts
CryptoJS SHA-256 password hashing
Web Speech API Voice message recording

---

💻 Installation Guide

Prerequisites

· Modern web browser (Chrome, Firefox, Safari, Edge)
· Text editor (VS Code recommended)
· Local server (for camera/microphone access)

Step 1: Download the Project

```bash
# Clone the repository
git clone https://github.com/your-username/farmconnect.git

# Navigate to project directory
cd farmconnect
```

Step 2: File Structure

Ensure you have the following files in your project folder:

```
farmconnect/
├── index.html          # Landing page
├── login.html          # Login page
├── registration.html   # Registration page
├── payment.html        # Payment page
├── dashboard.html      # Main dashboard 
└── README.md           # Documentation
```

Step 3: Run Locally

Option A: Using Python (Recommended)

```bash
# Python 3
python -m http.server 8080

# Python 2
python -m SimpleHTTPServer 8080
```

Then open: http://localhost:8080

Option B: Using VS Code Live Server

1. Install "Live Server" extension
2. Right-click index.html
3. Select "Open with Live Server"

Option C: Using Node.js

```bash
# Install serve globally
npm install -g serve

# Run the server
serve .
```

Step 4: Enable Microphone (For Voice Messages)

· Chrome/Edge: Allow microphone access when prompted
· Firefox: Click "Allow" in the permission dialog
· Safari: Go to Settings → Websites → Microphone → Allow

Note: Voice messages require HTTPS or localhost for security reasons.

---

📖 Usage Guide

First Time Setup

1. Open index.html in your browser
2. Click "Join as Farmer" or "Join as Buyer"
3. Fill registration form
4. Complete payment (demo mode - UGX 5,000)
5. Wait for admin approval (or use test accounts)
6. Login to access your dashboard

Farmer Workflow

```
1. Login → Farmer Dashboard
2. Click "Add Product" → Fill product details
3. Upload product image (optional)
4. Submit → Product appears in marketplace
5. View orders in "Orders Received" section
6. Click "Mark as Shipped" when order is processed
7. Chat with buyers via order card
```

Buyer Workflow

```
1. Login → Buyer Dashboard
2. Browse products (search/filter by category)
3. Click "Buy Now" on desired product
4. Enter quantity and delivery address
5. Confirm order → Payment modal appears
6. Select payment method (Mobile Money/Card)
7. Complete payment (demo mode)
8. Track order status in "My Orders"
9. Rate product after delivery
10. Chat with farmer via order card
```

Smart Farming Tools

Click any tool card in the Farmer Dashboard:

· AI Farm Advisor - Get planting and pest control tips
· Live Market Prices - View current crop prices
· Weather Advisory - Check 3-day forecast
· Aflatoxin Alert - Learn about harvest safety
· Crop Disease Doctor - Diagnose plant problems
· Fertilizer Calculator - Calculate fertilizer needs

---

👥 User Roles

1. Farmer

· Purpose: Sell agricultural products
· Permissions: Add products, manage orders, chat with buyers, view analytics
· Default Test Account: farmer@farmconnect.com / farmer123

2. Buyer

· Purpose: Purchase fresh produce
· Permissions: Browse products, place orders, rate products, chat with farmers
· Default Test Account: buyer@farmconnect.com / buyer123

3. Authority (Admin)

· Purpose: Manage platform users and content
· Permissions: Approve users, manage ads, view revenue
· Default Test Account: admin@farmconnect.com / admin123

---

📊 Database Structure

localStorage Keys Used

Key Description Data Type
users User accounts Array
farmconnect_products Product listings Array
farmconnect_orders Order records Array
farmconnect_messages Chat messages Object
farmconnect_ratings Product ratings Object
farmconnect_wishlist Buyer wishlists Array
farmconnect_ads Advertisements Array
currentUser Logged-in user Object

User Object Structure

```javascript
{
    id: "farmer_john",
    name: "John Mubiru",
    email: "farmer@farmconnect.com",
    passwordHash: "hashed_password",
    type: "farmer", // farmer, buyer, authority
    phone: "+256700000001",
    location: "Kampala, Uganda",
    verified: true,
    subscription: {
        active: true,
        expiryDate: "2024-12-31T00:00:00.000Z"
    },
    status: "approved", // pending, approved
    lastActive: "2024-01-01T00:00:00.000Z"
}
```

Product Object Structure

```javascript
{
    id: "prod_1234567890",
    farmerId: "farmer_john",
    farmerName: "John Mubiru",
    name: "Fresh Maize",
    category: "grains",
    description: "Freshly harvested maize",
    price: 1200,
    quantity: 100,
    unit: "kg",
    image: "🌽",
    imageData: "base64_image_string",
    rating: 4.5
}
```

Order Object Structure

```javascript
{
    id: "ord_1234567890",
    productId: "prod_1234567890",
    productName: "Fresh Maize",
    farmerId: "farmer_john",
    farmerName: "John Mubiru",
    buyerId: "buyer_sarah",
    buyerName: "Sarah Namukasa",
    quantity: 5,
    unit: "kg",
    price: 1200,
    totalAmount: 6000,
    status: "pending", // pending, shipped, delivered, cancelled
    paymentStatus: "pending", // pending, paid
    deliveryAddress: "Kampala, Uganda",
    orderDate: "2024-01-01T00:00:00.000Z"
}
```

---

🔌 API Endpoints

External APIs Used

Endpoint Purpose Method
https://api.commodities.ninja/v2/commodity-prices Live market prices GET
https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js Analytics charts GET
https://cdnjs.cloudflare.com/ajax/libs/crypto-js/4.2.0/crypto-js.min.js Password hashing GET

Internal Functions (No backend required)

All data operations are handled via JavaScript functions:

Function Purpose
checkAuth() Validate user session
loadFarmerData() Load farmer-specific data
loadBuyerData() Load buyer-specific data
addProduct() Create new product
buyProduct() Place new order
sendTextMessage() Send chat message
exportData() Export analytics data

---

🚀 Deployment Guide

Option 1: Deploy to Netlify (Free)

```bash
# 1. Sign up at netlify.com
# 2. Drag and drop your project folder
```

HTTPS Requirement

For voice messages and camera access, your site must be served over HTTPS. Netlify and Vercel provide free SSL certificates automatically.

---

🧪 Testing Accounts

Use these credentials to test different user roles:

Farmer Account

Field Value
Email farmer@farmconnect.com
Password farmer123
Name John Mubiru
Location Kampala, Uganda

Buyer Account

Field Value
Email buyer@farmconnect.com
Password buyer123
Name Sarah Namukasa
Location Kampala, Uganda

Authority (Admin) Account

Field Value
Email admin@farmconnect.com
Password admin123
Name Administrator

Note: These accounts are automatically created when the app first runs.

---

🐛 Troubleshooting

Common Issues & Solutions

Issue Solution
Dashboard not showing Clear localStorage: localStorage.clear() in Console
"Loading..." not changing Refresh page (Ctrl+F5) or check Console for errors
Voice recording not working Ensure HTTPS/localhost and allow microphone permission
Images not displaying Check file size (< 2MB) and format (JPEG, PNG)
Session expired too quickly Session timer is 30 minutes by default
Products not saving Check localStorage quota (max ~5MB)
Chat messages not sending Ensure you have an active order

Debugging Steps

1. Open Developer Tools (F12)
2. Check Console tab for errors
3. Check Application tab → Local Storage to view data
4. Run in Console:
   ```javascript
   console.log(localStorage.getItem('currentUser'));
   console.log(localStorage.getItem('farmconnect_products'));
   ```

Clearing All Data

```javascript
// Run in Console to reset everything
localStorage.clear();
location.reload();
```

---

🗺 Future Roadmap

Phase 1: Production Ready (1-2 weeks)

· Deploy to HTTPS (Netlify/Vercel)
· Add Supabase backend (replace localStorage)
· Integrate Paystack/Flutterwave (real payments)
· Add real M-PESA/Airtel Money integration

Phase 2: Enhanced Features (2-4 weeks)

· Password reset functionality
· Email verification
· Bulk product upload (CSV)
· Order invoice generation (PDF)
· Push notifications via Firebase

Phase 3: Mobile & Offline (1-2 months)

· Convert to PWA for offline access
· Android APK via Capacitor
· iOS app via Capacitor
· Offline mode with IndexedDB

Phase 4: Advanced Features (3-6 months)

· AI disease detection from photos
· Real-time delivery tracking with maps
· Multi-language support (Luganda, Runyankole)
· WhatsApp sharing integration
· Farmer verification badges

---

🤝 Contributing

How to Contribute

1. Fork the repository
2. Create a feature branch
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Commit changes
   ```bash
   git commit -m "Add amazing feature"
   ```
4. Push to branch
   ```bash
   git push origin feature/amazing-feature
   ```
5. Open a Pull Request

Code Style Guidelines

· Use 2 spaces for indentation
· Use camelCase for variables and functions
· Use kebab-case for CSS classes
· Add comments for complex logic
· Keep functions small and focused

Reporting Issues

Use GitHub Issues to report bugs or suggest features:

```markdown
**Bug Description**: [Describe the issue]
**Steps to Reproduce**: 
1. Go to...
2. Click on...
**Expected Behavior**: [What should happen]
**Screenshots**: [If applicable]
**Environment**: [Browser, OS]
```

---

📄 License

This project is proprietary and confidential. Unauthorized copying, distribution, or use of this software is strictly prohibited.

© 2024 FarmConnect. All rights reserved.

---

📞 Contact & Support

Channel Information
Email samuelsekasi201@gmail.com
Phone +256749140861
Website https://farmconnect.com
Address Kampala, Uganda

Support Hours

· Monday - Friday: 8:00 AM - 6:00 PM (EAT)
· Saturday: 9:00 AM - 1:00 PM (EAT)
· Sunday: Closed

---

🙏 Acknowledgments

· Uganda National Farmers Federation - Agricultural guidance
· Ministry of Agriculture - Market data support
· All beta testers - Valuable feedback

---

📊 Project Statistics

Metric Value
Total Lines of Code ~3,500
JavaScript Functions 85+
CSS Styles 300+
HTML Elements 200+
Features Implemented 35+
User Roles 3
File Size ~150KB

---

🏆 Version History

Version Date Changes
1.0.0 2024-01-01 Initial release
1.1.0 2024-02-01 Added voice messages
1.2.0 2024-03-01 Added image sharing in chat
1.3.0 2024-04-01 Added analytics & export
2.0.0 2024-05-01 Complete rewrite with all features

---

✅ Quick Start Checklist

```markdown
☐ Download/clone the project
☐ Run local server (python -m http.server 8080)
☐ Open http://localhost:8080
☐ Register as Farmer or Buyer
☐ Login with test accounts or your own
☐ Explore features based on your role
☐ Deploy to Netlify for public access
```

---

Built with ❤️ for Ugandan farmers and buyers

FarmConnect - Connecting Farmers to Your Table 🌾
