# 💊 Simbeye Pharmacy Platform - Complete Repository Overview

## What This Is

**Simbeye Pharmacy Online** is a full-stack e-pharmacy platform that enables customers to browse and purchase medicines with real-time inventory management, prescription uploads, and mobile money payment integration. It's built as a modern TypeScript application with React frontend and Node.js backend, designed to digitize pharmaceutical retail operations.

---

## 🏗️ Technology Stack

### Backend
- **Language:** TypeScript
- **Runtime:** Node.js
- **Framework:** Express.js
- **Key Libraries:**
  - Express (REST API framework)
  - TypeScript for type safety
  - File system-based data persistence (with local data storage)
  - Prescription upload handling

### Frontend
- **Framework:** React 18+ with TypeScript
- **Styling:** Tailwind CSS
- **Component Architecture:** Modular TSX components
- **Key Libraries:**
  - React for UI
  - Tailwind CSS for styling
  - SVG assets (react.svg, vite.svg)

---

## 📁 Repository Structure

```
simbeye-pharmacy/
├── server/                           Backend API Server
│   ├── src/
│   │   ├── index.ts                 Express server entry point
│   │   ├── seed.ts                  Database seeding with initial data
│   │   ├── helpers.ts               Utility functions
│   │   ├── routes/
│   │   │   ├── admin.ts             Admin dashboard APIs (login, orders, products, deliveries, prescriptions)
│   │   │   └── catalogue.ts         Product catalogue endpoints (browse, search, stock, categories)
│   │   ├── data/                    Local JSON data storage
│   │   └── uploads/                 User prescription uploads directory
│   ├── package.json                 Dependencies & scripts
│   ├── package-lock.json            Dependency lock file
│   └── .gitignore                   Git ignore rules
│
├── client/                           Frontend React Application
│   ├── src/
│   │   ├── App.tsx                  Main React component
│   │   ├── index.css                Global styles
│   │   ├── components/
│   │   │   ├── ProductCard.tsx      Medicine product display card
│   │   │   └── StockBadge.tsx       Inventory status component
│   │   └── assets/
│   │       ├── react.svg            React logo
│   │       ├── vite.svg             Vite logo
│   │       └── hero.png             Hero banner image
│   ├── tailwind.config.js           Tailwind CSS configuration
│   └── package.json                 Dependencies & scripts
│
├── Simbeye_Pharmacy_Platform.zip    Project archive (contains all above)
├── README.md                        Project documentation
└── .gitignore (root)                Root-level git ignore
```

### How It Fits Together

**Request Flow:**
1. **Customer browsing** → React frontend renders product listings from `ProductCard` components
2. **Fetch products** → Frontend calls `/catalogue/products` API endpoint
3. **Backend query** → Express server retrieves products from local `data/` storage via `catalogue.ts` route
4. **Real-time stock** → Stock information displayed via `StockBadge` component
5. **Admin operations** → Admin dashboard communicates with `/admin/*` routes for order/prescription management
6. **Prescription upload** → Files stored in `server/uploads/` directory
7. **Data persistence** → Local file-based storage using seed data and helper utilities

---

## 🚀 Getting Started

### Prerequisites
- **Node.js** v16+ installed
- **npm** or yarn package manager
- Git for version control

### Installation & Setup

**1. Clone the repository**
```bash
git clone https://github.com/samsonsimbeye01/simbeyepharm.git
cd simbeyepharm
```

**2. Backend Setup**
```bash
cd server
npm install
npm run dev          # Start development server with hot-reload
```

**3. Frontend Setup** (in a new terminal)
```bash
cd client
npm install
npm start            # Starts on http://localhost:3000
```

**4. Database Initialization**
```bash
cd server
npm run seed         # Populate initial pharmacy data
```

### Development Commands

**Server-side:**
```bash
npm run dev          # Hot-reload development server
npm start            # Production server
npm run seed         # Reinitialize database
npm test             # Run tests
```

**Client-side:**
```bash
npm start            # Development server (http://localhost:3000)
npm run build        # Optimized production build
npm run preview      # Preview production build
npm test             # Run tests
```

---

## 📖 API Architecture

### Admin Routes (`/routes/admin.ts`)
Endpoints for pharmacy administrators to manage the platform:

| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | `/admin/login` | Admin authentication |
| GET/POST | `/admin/orders` | Manage customer orders |
| GET/POST | `/admin/products` | Product CRUD operations |
| GET/POST | `/admin/deliveries` | Track and manage deliveries |
| GET/POST | `/admin/prescriptions` | Review and verify prescriptions |

### Catalogue Routes (`/routes/catalogue.ts`)
Public endpoints for browsing medicines:

| Method | Endpoint | Purpose |
|--------|----------|---------|
| GET | `/catalogue/products` | Fetch all medicines |
| GET | `/catalogue/products/:id` | Get product details |
| GET | `/catalogue/search?q=term` | Search medicines by name |
| GET | `/catalogue/categories` | List product categories |
| GET | `/catalogue/stock/:id` | Check real-time stock level |

---

## 🛠️ Key Components & Features

### Frontend Components

**ProductCard.tsx**
- Displays individual medicine products
- Shows price, description, and availability
- Add to cart functionality
- Product image and details

**StockBadge.tsx**
- Visual indicator of product availability
- Stock level status
- Color-coded inventory alerts

**App.tsx**
- Main application root component
- Navigation and routing
- State management for cart and user session

### Backend Utilities

**seed.ts**
- Initializes database with sample medicines
- Sets up default admin credentials
- Populates categories and pricing

**helpers.ts**
- Common utility functions
- Data validation
- API response formatting
- Error handling

---

## 🔒 Security & Features

### Implemented
✅ **Prescription Management** - Upload and verify digital prescriptions  
✅ **Real-time Stock Updates** - Live inventory tracking  
✅ **Order Processing** - Complete order workflow  
✅ **Admin Authentication** - Secure login for administrators  
✅ **Delivery Tracking** - Monitor order shipment status  

### Future Enhancements
🔄 Role-Based Access Control (RBAC)  
🔄 Payment gateway encryption  
🔄 Email/SMS notifications  
🔄 Prescription OCR validation  
🔄 Customer ratings system  

---

## 💳 Payment & Checkout

- **Supported Payment Methods:** Mobile Money (Mobil integration), Card, Cash on Delivery
- **Checkout Flow:** 
  1. Add medicines to cart
  2. Review order summary
  3. Select delivery/collection option
  4. Enter shipping address
  5. Choose payment method
  6. Confirm and process payment
  7. Receive order confirmation

---

## 📊 Data Models

### Medicine/Product
```typescript
{
  id: string
  name: string
  description: string
  price: number
  stock: number
  category: string
  image: string
}
```

### Order
```typescript
{
  id: string
  customerId: string
  items: OrderItem[]
  total: number
  status: "pending" | "processing" | "shipped" | "delivered"
  createdAt: Date
  deliveryDate?: Date
}
```

### Prescription
```typescript
{
  id: string
  customerId: string
  fileUrl: string
  status: "pending" | "verified" | "rejected"
  uploadedAt: Date
  verifiedBy?: string
}
```

---

## 📈 Project Roadmap

- [ ] **Multi-language Support** (English, French, etc.)
- [ ] **Push Notifications** (Order updates, promotions)
- [ ] **Customer Loyalty Program** (Points, rewards, discounts)
- [ ] **Insurance Integration** (Claim processing)
- [ ] **Telemedicine Features** (Doctor consultations)
- [ ] **Advanced Analytics** (Sales reports, inventory forecasting)
- [ ] **Mobile App** (React Native for iOS/Android)
- [ ] **AI Recommendations** (Medicine suggestions based on history)

---

## 🤝 Contributing

We welcome contributions! Here's how to get involved:

1. **Fork** the repository
2. **Create** a feature branch: `git checkout -b feature/your-feature`
3. **Commit** changes: `git commit -m 'Add your feature'`
4. **Push** to branch: `git push origin feature/your-feature`
5. **Open** a Pull Request with a clear description

### Development Guidelines
- Write TypeScript for type safety
- Follow existing code structure
- Test new features thoroughly
- Update documentation as needed
- Keep commits atomic and descriptive

---

## 📧 Support & Contact

**Issues & Bug Reports:**
- Open a GitHub Issue with detailed description
- Include steps to reproduce
- Add relevant screenshots/logs

**Questions & Feedback:**
- Email: samsonsimbeye01@gmail.com
- GitHub: [@samsonsimbeye01](https://github.com/samsonsimbeye01)

**Documentation:**
- See [README.md](./README.md) for quick start
- Check route files for API documentation
- Review seed.ts for data structure examples

---

## 📝 License

This project is licensed under the **MIT License**. See LICENSE file for details.

---

## 🎉 Acknowledgments

- Built with care for the healthcare community
- Inspired by modern e-commerce best practices
- Special thanks to all contributors and users
- Designed to improve medicine accessibility

---

**Simbeye Pharmacy Platform** | Built with ❤️ by Samson Simbeye  
[GitHub](https://github.com/samsonsimbeye01) | simbeyepharm

---

### Quick Links
- 📱 **Frontend**: `client/src/`
- 🔌 **Backend**: `server/src/`
- 📚 **API Routes**: `server/src/routes/`
- 🎨 **Components**: `client/src/components/`
- 💾 **Database**: `server/data/` (local storage)
- 📤 **Uploads**: `server/uploads/` (prescriptions)
