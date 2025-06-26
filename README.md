# 💪 Gymcyclopedia - Fitness Tracking Web App

A comprehensive fitness tracking application built with vanilla JavaScript and Supabase, featuring workout management, exercise library, progress tracking, and user authentication.

## 🚀 Features

### ✅ Currently Implemented
- **User Authentication** - Sign up, login, logout, password reset
- **Exercise Library** - 21+ pre-loaded exercises with categories
- **Workout Creation** - Build custom workout routines
- **Real-time Workout Sessions** - Timer, exercise tracking, progress monitoring
- **Progress Dashboard** - Weight tracking, goal progress, streak counting
- **Workout History** - Track completed sessions and performance
- **Responsive Design** - Mobile-friendly interface with modern dark theme

### 🔄 In Progress
- Database integration (fallback to localStorage when database not set up)
- Enhanced workout session tracking with detailed performance data

### 📅 Planned Features
- Exercise form videos and detailed instructions
- Nutrition tracking and meal planning
- Social features and workout sharing
- Advanced analytics and insights
- Mobile app with PWA capabilities

## 🛠️ Tech Stack

- **Frontend**: HTML5, CSS3, Bootstrap 5, Vanilla JavaScript
- **Backend**: Supabase (PostgreSQL, Auth, RLS)
- **Styling**: Custom CSS with glass morphism effects
- **Fonts**: Google Fonts (Poppins)

## 📋 Project Structure

```
GymcyclopediaMain/
├── GymcyclopediaMain/
│   ├── index.html          # Main dashboard and authentication
│   ├── workouts.html       # Workout management and sessions
│   └── reset-password.html # Password reset page
├── supabase-setup.sql      # Main database setup
├── supabase-workouts-schema.sql # Workout tables and data
├── supabase-update-schema.sql   # Schema updates
└── README.md              # This file
```

## 🚀 Next Action Plan

### Phase 1: Database Setup (IMMEDIATE)

1. **Apply Database Schema**
   ```sql
   -- Go to Supabase Dashboard > SQL Editor
   -- Run supabase-workouts-schema.sql
   ```
   This will create:
   - Exercise library (21 exercises)
   - Workout management tables
   - Session tracking tables
   - Row Level Security policies
   - Views and functions for statistics

2. **Test Database Connection**
   - Open workouts.html
   - Check browser console for database connection messages
   - Verify exercises load from database instead of fallback

### Phase 2: Enhanced Functionality (NEXT WEEK)

1. **Improve Workout Sessions**
   - Add set-by-set tracking
   - Rest timer between sets
   - Exercise notes and form cues
   - Photo/video exercise demonstrations

2. **Analytics Dashboard**
   - Weekly/monthly progress charts
   - Personal records tracking
   - Exercise frequency analysis
   - Goal achievement tracking

3. **Social Features**
   - Share workouts with friends
   - Community challenges
   - Workout templates library

### Phase 3: Mobile & Advanced Features (NEXT MONTH)

1. **Progressive Web App (PWA)**
   - Offline functionality
   - Push notifications for workout reminders
   - Home screen installation

2. **Nutrition Module**
   - Calorie tracking
   - Macro nutrient analysis
   - Meal planning

3. **AI-Powered Features**
   - Workout recommendations
   - Form analysis (future)
   - Personalized coaching tips

## 🔧 Setup Instructions

### Prerequisites
- Modern web browser
- Supabase account (free tier available)
- Basic knowledge of SQL for database setup

### Local Development

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd GymcyclopediaMain
   ```

2. **Set up Supabase**
   - Create account at [supabase.com](https://supabase.com)
   - Create new project
   - Note your project URL and anon key
   - Update Supabase credentials in HTML files

3. **Apply Database Schema**
   - Open Supabase Dashboard
   - Go to SQL Editor
   - Copy and run `supabase-workouts-schema.sql`
   - Verify tables are created

4. **Serve the files**
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Or use any local web server
   ```

5. **Access the application**
   - Open `http://localhost:8000`
   - Sign up for a new account
   - Start creating workouts!

## 📊 Database Schema

### Core Tables
- `exercises` - Exercise library with categories and instructions
- `workouts` - User-created workout routines
- `workout_exercises` - Exercises within each workout
- `workout_sessions` - Completed workout instances
- `workout_session_exercises` - Performance data for each exercise

### Views
- `workout_details` - Complete workout information with exercises
- `workout_history` - Session history with completion stats

### Functions
- `get_user_workout_stats()` - Comprehensive user statistics

## 🔒 Security

- Row Level Security (RLS) enabled on all tables
- Users can only access their own data
- Email verification required for account activation
- Secure password reset flow

## 🚀 Deployment

### Recommended Hosting Options
1. **Vercel** (Recommended)
   - Automatic deployments from Git
   - Built-in CDN and SSL
   - Free tier available

2. **Netlify**
   - Drag and drop deployment
   - Form handling capabilities
   - Free tier with custom domains

3. **GitHub Pages**
   - Free hosting for static sites
   - Automatic deployment from repository

### Environment Variables
Update the following in your HTML files:
```javascript
const SUPABASE_URL = 'your-project-url'
const SUPABASE_ANON_KEY = 'your-anon-key'
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 Changelog

### Version 2.0 (Current)
- Added comprehensive workout session management
- Enhanced UI with real-time timers
- Improved database integration with fallbacks
- Added detailed exercise tracking

### Version 1.0
- Basic workout creation and management
- User authentication system
- Exercise library integration
- Progress tracking dashboard

## 📞 Support

For issues and questions:
1. Check the browser console for error messages
2. Verify Supabase connection and database setup
3. Ensure all SQL scripts have been applied
4. Check network connectivity

## 🎯 Current Priority Tasks

1. **Apply database schema** - Run `supabase-workouts-schema.sql`
2. **Test workout session flow** - Create and start a workout
3. **Verify data persistence** - Check if workouts save to database
4. **Mobile responsiveness** - Test on different screen sizes
5. **Performance optimization** - Monitor load times and API calls

---

**Ready to transform your fitness journey? Let's build something amazing! 💪** 