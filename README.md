# 🎓 Automated Student Attendance System

A comprehensive, modern attendance management system built with React, Node.js, and MongoDB. Features real-time QR code generation, geofencing, analytics, and multi-role support for educational institutions.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/node.js-18+-green.svg)
![React](https://img.shields.io/badge/react-18+-blue.svg)
![MongoDB](https://img.shields.io/badge/mongodb-6+-green.svg)

## ✨ Features

### 🔐 Authentication & Authorization
- **JWT-based authentication** with access & refresh tokens
- **Role-based access control** (Admin, Faculty, Student)
- **Secure password hashing** with bcrypt
- **HTTP-only cookies** for refresh token storage

### 📱 Attendance Management
- **Dynamic QR Code Generation** with HMAC signatures
- **Real-time QR rotation** (20-second intervals) for security
- **Geofencing verification** using Haversine formula
- **Device fingerprinting** to prevent fraud
- **Location spoofing detection**
- **Multiple attendance sources** (QR, Face, Zoom, etc.)

### 🌐 Real-time Features
- **WebSocket integration** with Socket.IO
- **Live QR code updates** for active sessions
- **Real-time attendance notifications**
- **Session monitoring** for faculty

### 📊 Analytics & Reporting
- **Comprehensive dashboards** for all user roles
- **Attendance statistics** and trends
- **Class performance metrics**
- **Student engagement analytics**
- **Audit logging** for all system activities

### 🎯 Advanced Features
- **Online session support** (Zoom integration)
- **Geofencing with customizable radius**
- **Rate limiting** and security headers
- **Responsive design** with Tailwind CSS
- **Progressive Web App** capabilities

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   React Client  │◄──►│  Express API    │◄──►│   MongoDB       │
│   (Frontend)    │    │   (Backend)     │    │  (Database)     │
└─────────────────┘    └─────────────────┘    └─────────────────┘
        │                       │
        │              ┌─────────────────┐
        └──────────────►│   Socket.IO     │
                       │ (Real-time)     │
                       └─────────────────┘
```

### Tech Stack

**Frontend:**
- React 18 + Vite
- Tailwind CSS + Framer Motion
- Zustand (State Management)
- React Router DOM
- Socket.IO Client
- Axios

**Backend:**
- Node.js + Express
- MongoDB + Mongoose
- Socket.IO
- JWT Authentication
- bcrypt + Helmet
- Rate Limiting

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ 
- MongoDB 6+
- npm or yarn

### Installation

1. **Clone the repository**
```bash
git clone <repository-url>
cd attendance-system
```

2. **Install dependencies**
```bash
# Install server dependencies
cd server
npm install

# Install client dependencies
cd ../client
npm install
```

3. **Environment Setup**
```bash
# Server environment
cd server
cp .env.example .env
# Edit .env with your configuration

# Client environment  
cd ../client
cp .env.example .env
# Edit .env with your API URL
```

4. **Database Setup**
```bash
# Make sure MongoDB is running
# Seed the database with initial admin user
cd server
npm run seed
```

5. **Start the application**
```bash
# Terminal 1: Start server
cd server
npm run dev

# Terminal 2: Start client
cd client
npm run dev
```

6. **Access the application**
- Frontend: http://localhost:5173
- Backend API: http://localhost:5000
- Default admin: Check your .env file

## 📁 Project Structure

```
attendance-system/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/         # Route components
│   │   ├── store/         # Zustand state management
│   │   ├── utils/         # Helper functions
│   │   └── App.jsx        # Main app component
│   ├── public/            # Static assets
│   └── package.json
├── server/                # Node.js backend
│   ├── src/
│   │   ├── config/        # Database configuration
│   │   ├── controllers/   # Business logic
│   │   ├── middleware/    # Auth, validation, etc.
│   │   ├── models/        # MongoDB schemas
│   │   ├── routes/        # API endpoints
│   │   ├── services/      # External services
│   │   ├── utils/         # Helper functions
│   │   └── server.js      # Main server file
│   ├── seed.js           # Database seeding
│   └── package.json
└── README.md
```

## 🔧 Configuration

### Server Environment Variables

```env
NODE_ENV=development
PORT=5000
MONGODB_URI=mongodb://localhost:27017/attendance_system
JWT_ACCESS_SECRET=your_access_token_secret
JWT_REFRESH_SECRET=your_refresh_token_secret
JWT_ACCESS_EXPIRY=15m
JWT_REFRESH_EXPIRY=7d
QR_SECRET=your_qr_signing_secret
QR_ROTATION_INTERVAL=20000
CLIENT_URL=http://localhost:5173
```

### Client Environment Variables

```env
VITE_API_URL=http://localhost:5000/api
```

## 🎯 Usage

### For Administrators
1. **User Management**: Create and manage faculty/student accounts
2. **System Analytics**: Monitor overall attendance trends
3. **Audit Logs**: Track all system activities
4. **Class Management**: Oversee all classes and sessions

### For Faculty
1. **Class Creation**: Set up classes with schedules
2. **Session Management**: Start/stop attendance sessions
3. **QR Code Generation**: Dynamic QR codes for attendance
4. **Analytics**: View class-specific attendance reports
5. **Geofencing**: Set location boundaries for sessions

### For Students
1. **QR Scanning**: Mark attendance via QR codes
2. **Location Verification**: Automatic geofencing validation
3. **Attendance History**: View personal attendance records
4. **Analytics**: Track attendance patterns and streaks

## 🔒 Security Features

### Authentication Security
- **JWT tokens** with short expiry (15 minutes)
- **Refresh token rotation** for enhanced security
- **HTTP-only cookies** prevent XSS attacks
- **bcrypt hashing** with salt rounds

### Attendance Security
- **HMAC-signed QR codes** prevent forgery
- **Time-based rotation** (20-second intervals)
- **Geofencing verification** using Haversine formula
- **Device fingerprinting** to detect suspicious activity
- **Location spoofing detection**

### API Security
- **Rate limiting** (500 requests/15 minutes)
- **CORS protection** with specific origins
- **Helmet.js** for security headers
- **Input validation** and sanitization

## 📊 API Documentation

### Authentication Endpoints
```
POST /api/auth/register    # User registration
POST /api/auth/login       # User login
POST /api/auth/refresh     # Token refresh
POST /api/auth/logout      # User logout
GET  /api/auth/profile     # Get user profile
```

### Class Management
```
GET    /api/classes        # Get all classes
POST   /api/classes        # Create new class
GET    /api/classes/:id    # Get specific class
PUT    /api/classes/:id    # Update class
DELETE /api/classes/:id    # Delete class
```

### Session Management
```
GET    /api/sessions       # Get sessions
POST   /api/sessions       # Create session
GET    /api/sessions/:id   # Get specific session
PUT    /api/sessions/:id   # Update session
DELETE /api/sessions/:id   # Delete session
```

### Attendance
```
GET  /api/attendance       # Get attendance records
POST /api/attendance/mark  # Mark attendance
GET  /api/attendance/stats # Get attendance statistics
```

## 🧪 Testing

```bash
# Run server tests
cd server
npm test

# Run client tests
cd client
npm test
```

## 🚀 Deployment

### Production Build

```bash
# Build client
cd client
npm run build

# Start server in production
cd server
NODE_ENV=production npm start
```

### Environment Setup
1. Set `NODE_ENV=production`
2. Use strong JWT secrets
3. Configure MongoDB connection string
4. Set up reverse proxy (nginx)
5. Enable HTTPS
6. Configure CORS for production domain

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support and questions:
- Create an issue in the repository
- Check the documentation in `/docs`
- Review the API documentation

## 🔄 Changelog

### v1.0.0
- Initial release
- QR code attendance system
- Geofencing support
- Real-time updates
- Multi-role authentication
- Analytics dashboard

---

**Built with ❤️ for educational institutions**