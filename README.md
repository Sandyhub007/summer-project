# 🏋️‍♂️ Gymcyclopedia - Your Complete Fitness Journey Companion

> A modern, full-stack fitness tracking web application built with **Supabase**, **HTML5**, **CSS3**, and **JavaScript**. Track your weight loss/gain goals, monitor daily progress, and stay motivated with visual progress tracking.

[![Live Demo](https://img.shields.io/badge/Demo-Live-brightgreen)](http://localhost:8001)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue)](https://github.com/Sandyhub007/summer-project)
[![Supabase](https://img.shields.io/badge/Database-Supabase-green)](https://supabase.com)

---

## 📋 Table of Contents

- [✨ Features](#-features)
- [🛠️ Technology Stack](#️-technology-stack)
- [🚀 Quick Start](#-quick-start)
- [📊 Database Schema](#-database-schema)
- [🎯 Progress Tracking Features](#-progress-tracking-features)
- [🔐 Authentication System](#-authentication-system)
- [📱 Responsive Design](#-responsive-design)
- [🗂️ Project Structure](#️-project-structure)
- [🔄 Development Workflow](#-development-workflow)
- [📈 Future Roadmap](#-future-roadmap)
- [🤝 Contributing](#-contributing)

---

## ✨ Features

### 🏠 **Dashboard & User Management**
- **Personalized Welcome Dashboard** - Custom greeting with user's fitness data
- **Secure User Authentication** - Email/password signup and login
- **Email Verification** - Secure account activation process
- **User Profile Management** - Height, weight, goals, and timeline tracking

### 📊 **Progress Tracking System**
- **Visual Progress Bar** - Real-time progress toward weight goals
- **Days Remaining Counter** - Countdown to goal deadline
- **Streak Counter** - Track consistent daily logging habits
- **Weight Loss/Gain Support** - Handles both weight loss and weight gain goals
- **BMI Calculator** - Automatic BMI calculation and display

### 🎨 **User Experience**
- **Modern Dark Theme** - Sleek black interface with premium styling
- **Responsive Design** - Works perfectly on desktop, tablet, and mobile
- **Smooth Animations** - Progress bars with gradient animations
- **Intuitive Navigation** - Clear login/logout state management

### 🔒 **Security & Data Protection**
- **Row Level Security (RLS)** - Users can only access their own data
- **Password Encryption** - Secure bcrypt password hashing
- **Real-time Session Management** - Automatic login state detection
- **Data Validation** - Client and server-side input validation

---

## 🛠️ Technology Stack

### **Frontend**
- **HTML5** - Semantic markup structure
- **CSS3** - Custom styling with CSS Grid and Flexbox
- **JavaScript (ES6+)** - Modern async/await patterns
- **Bootstrap 5.3.2** - Responsive UI components
- **Google Fonts (Poppins)** - Premium typography

### **Backend & Database**
- **Supabase** - Backend-as-a-Service platform
- **PostgreSQL** - Robust relational database
- **Supabase Auth** - Built-in authentication system
- **Supabase Realtime** - Real-time data synchronization

### **Development Tools**
- **Python HTTP Server** - Local development server
- **Git** - Version control
- **GitHub** - Code repository and collaboration

---

## 🚀 Quick Start

### **Prerequisites**
- Python 3.x installed
- Git installed
- Supabase account (free tier available)

### **1. Clone the Repository**
```bash
git clone https://github.com/Sandyhub007/summer-project.git
cd summer-project
```

### **2. Set Up Supabase Database**
1. Create a new project at [supabase.com](https://supabase.com)
2. Go to **SQL Editor** in your Supabase dashboard
3. Run the setup script:
   ```sql
   -- Copy and paste content from supabase-setup-safe.sql
   ```
4. Run the progress tracking enhancement:
   ```sql
   -- Copy and paste content from supabase-update-schema.sql
   ```

### **3. Configure Supabase Credentials**
Edit `GymcyclopediaMain/index.html` and update:
```javascript
const SUPABASE_URL = 'YOUR_SUPABASE_URL_HERE';
const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY_HERE';
```

### **4. Run the Application**
```bash
cd GymcyclopediaMain
python3 -m http.server 8001
```

### **5. Access the App**
Open your browser and navigate to: `http://localhost:8001`

---

## 📊 Database Schema

### **`user_profiles` Table**
```sql
- id (UUID) - Primary key, linked to auth.users
- email (TEXT) - User's email address
- name (TEXT) - Display name
- current_weight_kg (DECIMAL) - Current weight in kilograms
- goal_weight_kg (DECIMAL) - Target weight in kilograms
- start_weight_kg (DECIMAL) - Starting weight for progress calculation
- height_cm (INTEGER) - Height in centimeters
- months_to_goal (INTEGER) - Timeline to reach goal
- daily_calories (INTEGER) - Daily calorie target
- streak_days (INTEGER) - Current logging streak
- last_log_date (DATE) - Last activity log date
- created_at (TIMESTAMP) - Account creation date
- updated_at (TIMESTAMP) - Last profile update
```

### **`weight_logs` Table** *(Coming Soon)*
```sql
- id (UUID) - Primary key
- user_id (UUID) - Foreign key to auth.users
- weight_kg (DECIMAL) - Recorded weight
- log_date (DATE) - Date of weight entry
- notes (TEXT) - Optional notes
- created_at (TIMESTAMP) - Entry creation time
```

---

## 🎯 Progress Tracking Features

### **📈 Visual Progress Bar**
- **Real-time Calculation** - Automatically calculates progress percentage
- **Weight Loss/Gain Support** - Adapts to different goal types
- **Gradient Animation** - Smooth CSS transitions for visual appeal
- **Progress Indicators** - Shows weight lost/gained and remaining

### **⏰ Days Remaining Counter**
- **Smart Calculation** - Based on user's timeline and creation date
- **Visual Countdown** - Clear display of time left to reach goal
- **Motivation Factor** - Encourages consistent progress

### **🔥 Streak Counter**
- **Daily Logging Rewards** - Tracks consecutive days of activity
- **Automatic Updates** - Updates based on weight logging frequency
- **Gamification Element** - Encourages habit formation

---

## 🔐 Authentication System

### **User Registration**
- Email and password validation
- Automatic profile creation via database triggers
- Email verification requirement
- Default fitness values assigned

### **User Login**
- Secure password verification
- Session persistence across browser refreshes
- Automatic UI state management
- Real-time authentication status updates

### **Session Management**
- Automatic login state detection on page load
- Secure logout with session cleanup
- Protected routes and data access
- Real-time auth state changes

---

## 📱 Responsive Design

### **Mobile-First Approach**
- Responsive grid system using Bootstrap
- Touch-friendly interface elements
- Optimized typography scaling
- Mobile navigation patterns

### **Cross-Device Compatibility**
- **Desktop** - Full dashboard with all features
- **Tablet** - Adapted layout with touch controls
- **Mobile** - Condensed UI with essential features
- **PWA Ready** - Progressive Web App capabilities

---

## 🗂️ Project Structure

```
summer-project/
├── GymcyclopediaMain/
│   └── index.html                 # Main application file
├── supabase-setup-safe.sql        # Initial database setup (safe)
├── supabase-setup.sql             # Original database setup
├── supabase-update-schema.sql     # Progress tracking enhancements
└── README.md                      # Project documentation
```

---

## 🔄 Development Workflow

### **Feature Development Process**
1. **Create Feature Branch** - `git checkout -b feature/feature-name`
2. **Implement Changes** - Code new functionality
3. **Update Database** - Add necessary schema changes
4. **Test Locally** - Verify functionality works
5. **Update Documentation** - Update README with new features
6. **Commit Changes** - `git commit -m "feat: descriptive message"`
7. **Push to GitHub** - `git push origin feature/feature-name`

### **Version Control Standards**
- **Commit Messages** - Follow conventional commit format
- **Branch Naming** - Use feature/, bugfix/, hotfix/ prefixes
- **Documentation** - Update README with every major feature
- **Database Changes** - Include SQL migration scripts

---

## 📈 Future Roadmap

### **🎯 Phase 1: Enhanced Progress Tracking** *(In Progress)*
- [x] Visual progress bars
- [x] Days remaining counter
- [x] Basic streak tracking
- [ ] Weight trend charts
- [ ] Progress photos upload
- [ ] Achievement badges system

### **💪 Phase 2: Workout Management**
- [ ] Workout library and templates
- [ ] Exercise tracking and logging
- [ ] Custom workout creation
- [ ] Performance analytics

### **🍎 Phase 3: Nutrition Tracking**
- [ ] Calorie counting and food database
- [ ] Meal planning and recipes
- [ ] Nutritional goal tracking
- [ ] Barcode scanning for foods

### **👥 Phase 4: Social Features**
- [ ] Friend connections and challenges
- [ ] Progress sharing capabilities
- [ ] Community leaderboards
- [ ] Motivational messaging system

### **📊 Phase 5: Advanced Analytics**
- [ ] Comprehensive progress reports
- [ ] Goal prediction algorithms
- [ ] Health metric correlations
- [ ] Export data functionality

---

## 🤝 Contributing

We welcome contributions to Gymcyclopedia! Here's how you can help:

### **Ways to Contribute**
- 🐛 **Bug Reports** - Found an issue? Let us know!
- 💡 **Feature Requests** - Have ideas for improvements?
- 🔧 **Code Contributions** - Submit pull requests
- 📚 **Documentation** - Help improve our docs

### **Development Setup**
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 📞 Support & Contact

- **GitHub Issues** - [Report bugs or request features](https://github.com/Sandyhub007/summer-project/issues)
- **Email** - sandilyachimalamarri@example.com
- **Documentation** - Check this README for setup help

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Supabase Team** - For the amazing backend platform
- **Bootstrap Team** - For the responsive UI framework
- **Google Fonts** - For the beautiful Poppins typography
- **Open Source Community** - For inspiration and best practices

---

*Last Updated: January 2025*

**🎯 Ready to start your fitness journey? [Get started now!](http://localhost:8001)** 