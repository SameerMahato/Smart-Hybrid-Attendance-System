# Client - Student Attendance System

React frontend for the attendance management system with modern UI and real-time features.

## Tech Stack

- **React 18** - UI framework
- **Vite** - Build tool and dev server
- **Tailwind CSS** - Styling framework
- **Zustand** - State management
- **React Router** - Client-side routing
- **Socket.IO Client** - Real-time communication
- **Axios** - HTTP client
- **Framer Motion** - Animations

## Features

- Responsive design with Tailwind CSS
- Real-time QR code updates via WebSocket
- Role-based dashboards (Admin, Faculty, Student)
- QR code scanning for attendance
- Location-based attendance verification
- Interactive analytics and charts
- JWT authentication with auto-refresh

## Development

### Prerequisites
- Node.js 18+
- Running backend server

### Setup
```bash
npm install
cp .env.example .env
npm run dev
```

### Environment Variables
```env
VITE_API_URL=http://localhost:5000/api
```

### Available Scripts
```bash
npm run dev      # Start development server
npm run build    # Build for production
npm run preview  # Preview production build
```

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── AnimatedBackground.jsx
│   ├── AttendanceChart.jsx
│   ├── QRDisplay.jsx
│   └── ...
├── pages/              # Route components
│   ├── Login.jsx
│   ├── AdminDashboard.jsx
│   ├── FacultyDashboard.jsx
│   └── ...
├── store/              # Zustand stores
│   ├── authStore.js
│   └── sessionStore.js
├── utils/              # Helper functions
│   └── axiosInstance.js
├── App.jsx             # Main app component
└── main.jsx           # Entry point
```

## Key Components

### Authentication
- JWT token management with automatic refresh
- Protected routes based on user roles
- Persistent auth state with localStorage

### Real-time Features
- Socket.IO integration for live QR updates
- Real-time session monitoring
- Live attendance notifications

### UI Components
- Responsive design for mobile and desktop
- Modern glass-morphism design
- Animated backgrounds and transitions
- Interactive charts and analytics

## Build & Deploy

```bash
npm run build
```

The build artifacts will be stored in the `dist/` directory, ready for deployment to any static hosting service.