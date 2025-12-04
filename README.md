# Appit - Performance Appraisal System

A comprehensive web-based performance appraisal management system designed to streamline employee evaluation, feedback, and performance tracking.

## Overview

Appit is a full-stack application that enables organizations to:
- Conduct structured performance appraisals for employees
- Manage performance periods and timelines
- Track performance history and scores
- Generate analytics and reports
- Provide a user-friendly interface for administrators and employees

## Features

### Core Features
- **User Management**: Create and manage employee and administrator accounts
- **Appraisal Management**: Create, update, and track performance appraisals
- **Performance Scoring**: Automated scoring system for consistent evaluation
- **Period Management**: Organize appraisals by performance periods
- **Analytics Dashboard**: Visual insights into performance metrics
- **PDF Export**: Generate professional appraisal reports
- **Authentication**: Secure login and session management
- **Leaderboard**: Performance rankings and comparisons

### Admin Features
- Staff management and user provisioning
- Period creation and management
- System administration and data cleanup
- Batch operations and data seeding
- Performance history backfilling

## Tech Stack

### Frontend
- **React 18**: UI framework
- **Vite**: Build tool and development server
- **Context API**: State management (Auth, Data, Notifications)
- **CSS**: Custom styling with modern CSS features

### Backend
- **Node.js/Express**: Server framework
- **SQLite**: Database
- **Middleware**: Authentication and authorization

### Tools & Utilities
- PDF generation for reports
- Data validation
- Performance scoring algorithms

## Project Structure

```
Appit/
├── src/                          # Frontend application
│   ├── components/              # Reusable React components
│   │   ├── AnalyticsDashboard.jsx
│   │   └── Layout.jsx
│   ├── pages/                   # Page components
│   │   ├── AdminPanel.jsx
│   │   ├── AppraisalForm.jsx
│   │   ├── AppraisalList.jsx
│   │   ├── Dashboard.jsx
│   │   ├── Leaderboard.jsx
│   │   ├── Login.jsx
│   │   ├── PeriodManagement.jsx
│   │   └── StaffManagement.jsx
│   ├── context/                 # React contexts
│   │   ├── AuthContext.jsx
│   │   ├── DataContext.jsx
│   │   └── NotificationContext.jsx
│   ├── services/                # API services
│   │   └── api.js
│   ├── utils/                   # Utility functions
│   │   ├── pdfGenerator.js
│   │   ├── scoring.js
│   │   └── validation.js
│   ├── data/                    # Mock data
│   │   └── mockData.js
│   ├── App.jsx                  # Main app component
│   ├── main.jsx                 # Entry point
│   └── index.css                # Global styles
├── server/                       # Backend application
│   ├── controllers/             # Route controllers
│   │   ├── appraisalController.js
│   │   ├── authController.js
│   │   ├── periodController.js
│   │   └── userController.js
│   ├── models/                  # Database models
│   │   ├── Appraisal.js
│   │   ├── Period.js
│   │   ├── PerformanceHistory.js
│   │   └── User.js
│   ├── routes/                  # API routes
│   │   ├── appraisalRoutes.js
│   │   ├── authRoutes.js
│   │   ├── periodRoutes.js
│   │   └── userRoutes.js
│   ├── middleware/              # Express middleware
│   │   └── auth.js
│   ├── config/                  # Configuration
│   │   └── database.js
│   ├── server.js                # Main server file
│   ├── seed.js                  # Database seeding
│   ├── package.json             # Backend dependencies
│   └── Utility Scripts
│       ├── add-attachment-column.js
│       ├── backfill-history.js
│       ├── check-data.js
│       ├── cleanup-duplicates.js
│       ├── reset-system.js
│       └── update-history-score.js
├── public/                       # Static files
│   ├── favicon.png
│   └── reset-session.html
├── vite.config.js               # Vite configuration
├── package.json                 # Frontend dependencies
├── index.html                   # Main HTML file
└── DEPLOYMENT.md                # Deployment guide

```

## Installation

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn
- SQLite3

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/ex-commando/Appit.git
   cd Appit
   ```

2. **Install frontend dependencies**
   ```bash
   npm install
   ```

3. **Install backend dependencies**
   ```bash
   cd server
   npm install
   cd ..
   ```

4. **Configure environment**
   - Copy `.env.example` to `.env` in the server directory
   - Update database connection and other settings as needed

## Running the Application

### Development

1. **Start the backend server**
   ```bash
   cd server
   npm start
   ```
   The server runs on `http://localhost:3000` by default.

2. **In a new terminal, start the frontend development server**
   ```bash
   npm run dev
   ```
   The frontend runs on `http://localhost:5173` by default.

### Production

Refer to `DEPLOYMENT.md` for production deployment instructions.

## Database Setup

1. **Initialize database with seed data**
   ```bash
   cd server
   node seed.js
   ```

2. **Run data migrations/backfills**
   ```bash
   node backfill-history.js
   ```

3. **Reset system (if needed)**
   ```bash
   node reset-system.js
   ```

## API Documentation

The backend provides RESTful APIs for:

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration
- `POST /api/auth/logout` - User logout

### Users
- `GET /api/users` - List all users
- `POST /api/users` - Create new user
- `GET /api/users/:id` - Get user details
- `PUT /api/users/:id` - Update user
- `DELETE /api/users/:id` - Delete user

### Appraisals
- `GET /api/appraisals` - List appraisals
- `POST /api/appraisals` - Create appraisal
- `GET /api/appraisals/:id` - Get appraisal details
- `PUT /api/appraisals/:id` - Update appraisal
- `DELETE /api/appraisals/:id` - Delete appraisal

### Periods
- `GET /api/periods` - List performance periods
- `POST /api/periods` - Create period
- `GET /api/periods/:id` - Get period details
- `PUT /api/periods/:id` - Update period

## Usage

1. **Login** with your credentials
2. **Navigate** to the appropriate section (Dashboard, Appraisals, Reports, etc.)
3. **Create/Edit** appraisals as needed
4. **View** analytics and performance metrics
5. **Export** reports in PDF format

## Configuration

Key configuration files:
- `server/config/database.js` - Database configuration
- `vite.config.js` - Frontend build configuration
- `server/.env` - Backend environment variables

## Testing

Data validation utilities are available at `src/utils/validation.js` for form validation.

## Troubleshooting

### Database Issues
- Run `node check-data.js` to verify database integrity
- Run `node cleanup-duplicates.js` to remove duplicate records

### Performance Issues
- Check database indexes
- Verify API response times
- Review server logs

## Contributors

**Senior Developer**: Francis Adegbe  
**Co-Developer**: Matthias Malachi

## License

This project is proprietary and confidential. All rights reserved.

## Support

For issues, questions, or contributions, please contact the development team.

## Changelog

### Version 1.0.0 (Initial Release)
- Core appraisal management features
- User authentication and authorization
- Performance scoring system
- Analytics dashboard
- PDF report generation
- Admin panel for system management

## Future Enhancements

- Multi-language support
- Advanced filtering and search
- Integration with third-party HR systems
- Mobile application
- Real-time notifications
- Advanced analytics and AI-driven insights

---

**Last Updated**: December 4, 2025
