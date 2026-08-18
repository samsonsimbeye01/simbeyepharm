# 💊 Simbeye Pharmacy Online

A modern, full-stack e-pharmacy platform enabling customers to browse medicines, manage prescriptions, and place orders seamlessly. Built with TypeScript, React, and Node.js for a robust healthcare delivery experience.

---

## 🌟 Features

### Customer Features
- 🏥 **Browse Medicines & Health Products** - Comprehensive product catalogue with detailed descriptions
- 📊 **Real-Time Stock Tracking** - Live inventory updates and price information
- 📋 **Prescription Management** - Upload and manage digital prescriptions
- 🛒 **Smart Shopping Cart** - Add, remove, and modify products with ease
- 💳 **Secure Checkout** - Streamlined payment process via mobile money (Mobil)
- 📦 **Order Tracking** - Monitor delivery status in real-time
- ⭐ **Product Ratings & Reviews** - Customer feedback system

### Admin Features
- 🔐 **Admin Dashboard** - Secure login and management interface
- 📈 **Inventory Management** - Stock control and product management
- 📲 **Order Management** - Process and track customer orders
- 🚚 **Delivery Tracking** - Manage and monitor deliveries
- 📄 **Prescription Handling** - Review and verify customer prescriptions
- 📊 **Sales Analytics** - Monitor platform performance and insights

---

## 🏗️ Technology Stack

### Backend
- **Runtime**: Node.js
- **Language**: TypeScript
- **Framework**: Express.js (implied from project structure)
- **Features**: 
  - RESTful API architecture
  - Admin route handlers
  - Product catalogue management
  - Database integration for orders and inventory

### Frontend
- **Framework**: React 18+
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Components**:
  - Product cards for medicine display
  - Stock management UI
  - Shopping cart interface
  - Admin dashboard
  - Checkout flow

### Database & Utilities
- Seed data functionality for initial setup
- Helper utilities for common operations

---

## 📁 Project Structure

```
simbeye-pharmacy/
├── server/                    # Backend application
│   ├── src/
│   │   ├── index.ts          # Server entry point
│   │   ├── seed.ts           # Database seeding
│   │   ├── helpers.ts        # Utility functions
│   │   └── routes/
│   │       ├── admin.ts      # Admin endpoints
│   │       └── catalogue.ts  # Product catalogue endpoints
│   ├── package.json          # Dependencies
│   └── data/                 # Local data storage
│
├── client/                    # Frontend application
│   ├── src/
│   │   ├── App.tsx           # Main application component
│   │   ├── index.css         # Global styles
│   │   ├── components/
│   │   │   ├── ProductCard.tsx      # Medicine product display
│   │   │   └── StockDisplay.tsx     # Inventory component
│   │   └── assets/           # Images and SVGs
│   ├── tailwind.config.js    # Tailwind CSS configuration
│   └── package.json          # Dependencies
│
└── README.md                  # This file
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn package manager
- Mobile money account for payments

### Installation

**1. Clone the repository**
```bash
git clone https://github.com/samsonsimbeye01/simbeyepharm.git
cd simbeyepharm
```

**2. Setup Backend**
```bash
cd server
npm install
npm run dev    # Start development server
```

**3. Setup Frontend**
```bash
cd client
npm install
npm start      # Start React development server
```

**4. Database Seeding**
```bash
cd server
npm run seed   # Populate initial data
```

---

## 📖 API Endpoints

### Admin Routes
- `GET/POST /admin/login` - Admin authentication
- `GET/POST /admin/orders` - Manage orders
- `GET/POST /admin/products` - Product management
- `GET/POST /admin/deliveries` - Delivery tracking
- `GET/POST /admin/prescriptions` - Prescription verification

### Catalogue Routes
- `GET /catalogue/products` - Fetch all medicines
- `GET /catalogue/products/:id` - Get product details
- `GET /catalogue/search` - Search medicines
- `GET /catalogue/categories` - Browse categories
- `GET /catalogue/stock/:id` - Check real-time stock

---

## 🔒 Security Features

- Secure admin authentication
- Prescription verification workflow
- Order validation and processing
- Real-time data encryption for payment information
- Role-based access control (RBAC)

---

## 💳 Payment Integration

The platform integrates with **Mobile Money (Mobil)** for seamless payment processing:
- Secure transaction handling
- Multiple payment options
- Transaction confirmation and receipts

---

## 🛠️ Development

### Available Scripts

**Server:**
```bash
npm run dev      # Start with hot-reload
npm start        # Production build
npm run seed     # Initialize database
npm test         # Run tests
```

**Client:**
```bash
npm start        # Development server (localhost:3000)
npm run build    # Production build
npm run preview  # Preview production build
npm test         # Run tests
```

---

## 📊 Features Roadmap

- [ ] Multi-language support
- [ ] SMS/Email notifications
- [ ] Customer loyalty rewards program
- [ ] Insurance integration
- [ ] Doctor consultation feature
- [ ] Advanced analytics dashboard
- [ ] Mobile app (React Native)
- [ ] AI-powered medicine recommendations

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 📧 Support

For issues, questions, or feedback:
- Create an GitHub Issue
- Contact: samsonsimbeye01@github.com
- Website: [Your website here]

---

## 🙏 Acknowledgments

- Built with ❤️ for the healthcare community
- Special thanks to all contributors
- Inspired by modern e-commerce best practices

---

**Made with ❤️ by Samson Simbeye** | [GitHub](https://github.com/samsonsimbeye01) | [LinkedIn]()
