# 🖥️ CS02 Computer Store

> A Full-Stack E-Commerce Platform for PC Components and Custom PC Building

[![Frontend](https://img.shields.io/badge/Frontend-Next.js%2016-black?logo=next.js)](frontend/)
[![Backend](https://img.shields.io/badge/Backend-Spring%20Boot%203.5-green?logo=spring)](backend/)
[![API Gateway](https://img.shields.io/badge/Gateway-Go-00ADD8?logo=go)](backend/api-gateway/)
[![AI Service](https://img.shields.io/badge/AI-FastAPI-009688?logo=fastapi)](backend/AI-service/)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker)](docker-compose.yml)

---

## 📋 Project Overview

CS02 Computer Store is a comprehensive **microservices-based e-commerce platform** designed for selling computer hardware, PC components, and custom-built PCs. The platform features an AI-powered PC Builder assistant, complete shopping experience, and a full admin dashboard.

### 🎯 Key Features

- **🛍️ Complete E-Commerce** - Product catalog, cart, wishlist, checkout
- **🔧 PC Builder** - 8-step wizard with compatibility checking
- **🤖 AI BuilderBot** - Natural language PC recommendations
- **👤 User Accounts** - Profile, orders, addresses, payment methods
- **📊 Admin Dashboard** - Inventory, analytics, customer management
- **🌙 Dark Mode** - System-aware theme switching
- **📱 Responsive** - Mobile, tablet, and desktop support

---

## 🏗️ Architecture

```
┌──────────────────────────────────────────────────────────────────────┐
│                     Frontend (Next.js - Port 3000)                   │
└────────────────────────────────┬─────────────────────────────────────┘
                                 │
                                 ▼
┌──────────────────────────────────────────────────────────────────────┐
│                    API Gateway (Go - Port 8080)                      │
│              JWT Auth │ Routing │ CORS │ Load Balancing              │
└───────────────────────────────────────────────────────────────────────┘
         │         │         │         │         │         │
         ▼         ▼         ▼         ▼         ▼         ▼
     ┌───────┐ ┌───────┐ ┌───────┐ ┌───────┐ ┌───────┐ ┌───────┐
     │ User  │ │Product│ │ Order │ │ Cart  │ │Support│ │  AI   │
     │ 8081  │ │ 8082  │ │ 8083  │ │ 8084  │ │ 8085  │ │ 8089  │
     └───┬───┘ └───┬───┘ └───┬───┘ └───┬───┘ └───┬───┘ └───────┘
         │         │         │         │         │
         ▼         ▼         ▼         ▼         ▼
     ┌─────────────────────────────────────────────────┐
     │     PostgreSQL │ MongoDB │ Redis │ Kafka        │
     └─────────────────────────────────────────────────┘
```

---

## 📦 Microservices

### Service Completion Checklist

| Service | Port | Status | Completion |
|---------|------|--------|------------|
| [Frontend](frontend/README.md) | 3000 | ✅ Complete | 95% |
| [API Gateway](backend/api-gateway/README.md) | 8080 | ✅ Complete | 100% |
| [User Identity Service](backend/user-identity-service/README.md) | 8081 | ✅ Complete | 85% |
| [Product Catalogue Service](backend/product-catalogue-service/README.md) | 8082 | ✅ Complete | 95% |
| [Order Service](backend/order-service/README.md) | 8083 | ✅ Complete | 80% |
| [Shopping Cart Service](backend/shoppingcart-wishlist-service/README.md) | 8084 | ✅ Complete | 95% |
| [Support Service](backend/support-service/README.md) | 8085 | ✅ Complete | 95% |
| [Content Service](backend/content-service/README.md) | 8086 | ✅ Complete | 85% |
| [Notifications Service](backend/notifications-service/README.md) | 8087 | ✅ Complete | 90% |
| [Reporting Service](backend/reporting-and-analysis-service/README.md) | 8088 | ⚠️ Partial | 70% |
| [AI Service](backend/AI-service/README.md) | 8089 | ✅ Complete | 100% |

### Overall Project Status: **~90% Complete** ✅

---

## 🛠️ Technology Stack

### Frontend
| Technology | Purpose |
|------------|---------|
| Next.js 16 | React framework (App Router) |
| TypeScript | Type-safe JavaScript |
| Tailwind CSS 4 | Utility-first styling |
| Zustand | State management |
| Framer Motion | Animations |

### Backend
| Technology | Purpose |
|------------|---------|
| Spring Boot 4.0.0 | Java microservices (8 services) |
| Go (Chi) | API Gateway |
| FastAPI | AI Service (Python) |
| Spring Security | Authentication |
| Spring Data JPA | PostgreSQL ORM |
| Spring Data MongoDB | MongoDB ODM |

### Infrastructure
| Technology | Purpose |
|------------|---------|
| PostgreSQL 15 | Relational database |
| MongoDB | Document database |
| Redis 7 | Cache & sessions |
| Kafka | Event streaming |
| Docker Compose | Container orchestration |

---

## 🚀 Quick Start

### Prerequisites

- Docker & Docker Compose
- Node.js 18+ (for frontend development)
- Java 17+ (for backend development)
- Go 1.20+ (for gateway development)

### 1. Clone the Repository

```bash
git clone https://github.com/CSO2/cs02-computer-store.git
cd cs02-computer-store
```

### 2. Start Backend Services

```bash
# Start all services with Docker Compose
docker-compose up -d

# Or use the startup script
chmod +x start-services.sh
./start-services.sh
```

### 3. Start Frontend

```bash
cd frontend
npm install
npm run dev
```

### 4. Access the Application

| Service | URL |
|---------|-----|
| Frontend | http://localhost:3000 |
| API Gateway | http://localhost:8080 |
| Swagger (User Service) | http://localhost:8081/swagger-ui.html |

### Demo Credentials

```
Customer: demo@example.com / password123
Admin: admin@example.com / admin123
```

---

## 📁 Project Structure

```
cs02-computer-store/
├── .github/                    # GitHub organization profile
├── backend/
│   ├── AI-service/             # Python/FastAPI AI service
│   ├── api-gateway/            # Go API gateway
│   ├── content-service/        # Java/Spring content management
│   ├── notifications-service/  # Java/Spring notifications
│   ├── order-service/          # Java/Spring order processing
│   ├── product-catalogue-service/ # Java/Spring product catalog
│   ├── reporting-and-analysis-service/ # Java/Spring analytics
│   ├── shoppingcart-wishlist-service/ # Java/Spring cart
│   ├── support-service/        # Java/Spring support tickets
│   └── user-identity-service/  # Java/Spring authentication
├── frontend/                   # Next.js frontend application
├── Databases/                  # Database schemas and docs
├── docker-compose.yml          # Docker orchestration
├── start-services.sh           # Startup script
└── README.md                   # This file
```

---

## 📊 Feature Checklist

### E-Commerce Features

- [x] Product catalog with categories
- [x] Product search and filtering
- [x] Shopping cart (Redis-backed)
- [x] Wishlist management
- [x] Product comparison (up to 4)
- [x] Checkout flow (4 steps)
- [x] Order history and tracking
- [x] Product reviews and ratings

### PC Builder Features

- [x] 8-step build wizard
- [x] Component compatibility checking
- [x] Save builds (public/private)
- [x] AI-powered recommendations
- [x] Build gallery
- [x] Price tracking

### User Features

- [x] Registration and login
- [x] JWT authentication
- [x] Profile management
- [x] Address management
- [x] Payment methods
- [x] Recently viewed
- [x] Loyalty rewards/tiers
- [x] Order notifications

### Admin Features

- [x] Dashboard with KPIs
- [x] Order management
- [x] Product management
- [x] Stock management
- [x] Customer list
- [x] Analytics charts
- [x] Support tickets
- [x] Store locations

### Missing/Planned Features

- [ ] Payment gateway integration (Stripe/PayPal)
- [ ] Password reset via email
- [ ] OAuth2 social login
- [ ] Real-time notifications (WebSocket)
- [ ] Advanced analytics
- [ ] Unit/E2E tests

---

## 🔗 API Documentation

### Gateway Routes

| Route | Service | Auth |
|-------|---------|------|
| `/api/auth/*` | User Identity | No |
| `/api/users/*` | User Identity | Yes |
| `/api/products/*` | Product Catalogue | No |
| `/api/cart/*` | Shopping Cart | Yes |
| `/api/wishlist/*` | Shopping Cart | Yes |
| `/api/orders/*` | Order Service | Yes |
| `/api/support/*` | Support Service | Yes |
| `/api/content/*` | Content Service | No |
| `/api/notifications/*` | Notifications | Yes |
| `/api/analytics/*` | Reporting | Admin |
| `/api/ai/*` | AI Service | No |

---

## 🗄️ Databases

| Database | Type | Purpose |
|----------|------|---------|
| `users_db` | PostgreSQL | User accounts, auth |
| `products_db` | PostgreSQL | Product catalog (alternative) |
| `CSO2_product_catalogue_service` | MongoDB | Products, categories, reviews |
| `CSO2_content_service` | MongoDB | Blog, FAQ, testimonials |
| `CSO2_notifications_service` | MongoDB | Notifications |
| `CSO2_shoppingcart_wishlist_service` | MongoDB | Wishlists, saved builds |
| Redis | In-memory | Shopping cart, sessions |

See [Databases README](Databases/README.md) for full schema documentation.

---

## 🐳 Docker Commands

```bash
# Start all services
docker-compose up -d

# Stop all services
docker-compose down

# View logs
docker-compose logs -f [service-name]

# Rebuild a specific service
docker-compose up -d --build [service-name]

# Clean up volumes
docker-compose down -v
```

---

## 🧪 Testing

```bash
# Frontend
cd frontend
npm run lint
npm run build

# Backend (each service)
cd backend/[service-name]
./mvnw test

# API Gateway
cd backend/api-gateway
go test ./...
```

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Team

**CS02 Development Team**

---

## 📞 Support

For support, please:
- Open an issue on GitHub
- Contact: support@cs02.example.com

---

<p align="center">
  Made with ❤️ by the CS02 Team
</p>
