# Project Structure

## Root Directory
```
attendance-system/
├── client/                    # React frontend application
├── server/                    # Node.js backend application
├── .gitignore                # Git ignore rules
├── API_DOCUMENTATION.md      # Complete API reference
├── CHANGELOG.md              # Version history and changes
├── CONTRIBUTING.md           # Contribution guidelines
├── LICENSE                   # MIT License
├── README.md                 # Project overview and setup
└── START_PROJECT.bat         # Windows startup script
```

## Client Structure
```
client/
├── public/                   # Static assets
│   └── logo.svg
├── src/
│   ├── components/          # Reusable React components
│   │   ├── AnimatedBackground.jsx
│   │   ├── AttendanceChart.jsx
│   │   ├── AttendanceHeatmap.jsx
│   │   ├── CountUpAnimation.jsx
│   │   ├── CreateZoomMeeting.jsx
│   │   ├── DeviceInfo.jsx
│   │   ├── FeatureCard.jsx
│   │   ├── FloatingShapes.jsx
│   │   ├── Footer.jsx
│   │   ├── GlassCard.jsx
│   │   ├── GradientText.jsx
│   │   ├── Loader.jsx
│   │   ├── LocationPicker.jsx
│   │   ├── Navbar.jsx
│   │   ├── NotificationBell.jsx
│   │   ├── NotificationCenter.jsx
│   │   ├── ProgressRing.jsx
│   │   ├── QRDisplay.jsx
│   │   ├── Sidebar.jsx
│   │   ├── StatsCard.jsx
│   │   ├── StreakCounter.jsx
│   │   └── VoiceToggle.jsx
│   ├── pages/               # Page components
│   │   ├── AdminDashboard.jsx
│   │   ├── Analytics.jsx
│   │   ├── AuditLogs.jsx
│   │   ├── AutoAttendance.jsx
│   │   ├── FacultyDashboard.jsx
│   │   ├── Home.jsx
│   │   ├── Login.jsx
│   │   ├── OnlineSession.jsx
│   │   ├── OnlineSessionMonitor.jsx
│   │   ├── Register.jsx
│   │   ├── ScanQR.jsx
│   │   ├── StartSession.jsx
│   │   ├── StudentAnalytics.jsx
│   │   ├── StudentAttendance.jsx
│   │   └── StudentDashboard.jsx
│   ├── store/               # State management
│   │   ├── authStore.js
│   │   └── sessionStore.js
│   ├── utils/               # Utility functions
│   │   ├── axiosInstance.js
│   │   ├── deviceFingerprint.js
│   │   └── voiceAnnouncements.js
│   ├── lib/                 # Helper libraries
│   │   └── utils.js
│   ├── App.jsx              # Main app component
│   ├── App.css              # App styles
│   ├── main.jsx             # Entry point
│   └── index.css            # Global styles
├── .env                     # Environment variables (not in git)
├── .env.example             # Environment template
├── .gitignore               # Client-specific ignores
├── index.html               # HTML template
├── package.json             # Dependencies
├── postcss.config.js        # PostCSS configuration
├── tailwind.config.js       # Tailwind CSS configuration
└── vite.config.js           # Vite configuration
```

## Server Structure
```
server/
├── src/
│   ├── config/              # Configuration files
│   │   └── db.js           # Database connection
│   ├── controllers/         # Request handlers
│   │   ├── analyticsController.js
│   │   ├── attendanceController.js
│   │   ├── authController.js
│   │   ├── classController.js
│   │   ├── onlineSessionController.js
│   │   ├── sessionController.js
│   │   └── zoomController.js
│   ├── middleware/          # Custom middleware
│   │   ├── auditLogger.js
│   │   ├── auth.js
│   │   ├── errorHandler.js
│   │   └── role.js
│   ├── models/              # Database schemas
│   │   ├── Attendance.js
│   │   ├── AuditLog.js
│   │   ├── Class.js
│   │   ├── Notification.js
│   │   ├── OnlineSession.js
│   │   ├── Session.js
│   │   └── User.js
│   ├── routes/              # API routes
│   │   ├── analyticsRoutes.js
│   │   ├── attendanceRoutes.js
│   │   ├── auditRoutes.js
│   │   ├── authRoutes.js
│   │   ├── classRoutes.js
│   │   ├── notificationRoutes.js
│   │   ├── onlineSessionRoutes.js
│   │   ├── sessionRoutes.js
│   │   └── zoomRoutes.js
│   ├── services/            # Business logic
│   │   └── zoomService.js
│   ├── utils/               # Utility functions
│   │   ├── deviceFingerprint.js
│   │   ├── generateToken.js
│   │   ├── geofencing.js
│   │   ├── notificationService.js
│   │   ├── proxyDetection.js
│   │   └── qr.js
│   └── server.js            # Express app entry point
├── .env                     # Environment variables (not in git)
├── .env.example             # Environment template
├── .gitignore               # Server-specific ignores
├── package.json             # Dependencies
└── seed.js                  # Database seeding script
```

## Key Files Description

### Root Level
- **README.md**: Complete project documentation with setup instructions
- **API_DOCUMENTATION.md**: Detailed API endpoint documentation
- **CHANGELOG.md**: Version history and feature additions
- **CONTRIBUTING.md**: Guidelines for contributors
- **LICENSE**: MIT License terms
- **START_PROJECT.bat**: Quick start script for Windows

### Configuration Files
- **.env.example**: Template for environment variables
- **.gitignore**: Files to exclude from version control
- **package.json**: Project dependencies and scripts

### Frontend Key Files
- **App.jsx**: Main application with routing
- **main.jsx**: React entry point
- **axiosInstance.js**: Configured HTTP client
- **authStore.js**: Authentication state management
- **tailwind.config.js**: UI styling configuration

### Backend Key Files
- **server.js**: Express server setup with Socket.IO
- **db.js**: MongoDB connection configuration
- **auth.js**: JWT authentication middleware
- **errorHandler.js**: Global error handling
- **seed.js**: Database initialization script

## Technology Stack

### Frontend
- React 18
- Vite
- TailwindCSS
- Framer Motion
- Socket.IO Client
- Zustand
- Axios
- Recharts

### Backend
- Node.js
- Express
- MongoDB + Mongoose
- Socket.IO
- JWT
- bcryptjs
- Helmet
- CORS

## File Count Summary
- **Total Components**: 20
- **Total Pages**: 15
- **Total Controllers**: 7
- **Total Models**: 7
- **Total Routes**: 9
- **Total Utilities**: 6
- **Total Middleware**: 4

## Excluded from Git
- node_modules/
- .env files
- Log files
- Build outputs
- IDE configurations
- OS-specific files
