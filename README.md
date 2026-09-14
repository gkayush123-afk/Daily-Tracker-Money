# 💰 Daily Money Tracker Pro

A comprehensive personal finance tracking web application with **cloud sync** across all devices.

## ✨ Features

- 💸 **Quick Add Expense** - Fast daily expense tracking
- 💵 **Income Tracking** - Track all income sources
- 🔄 **Recurring Expenses** - Auto-add monthly bills/subscriptions
- 🎯 **Savings Goals** - Set and track multiple goals
- 📊 **Smart Insights** - AI-powered spending analysis
- 📈 **Charts & Analytics** - Visual spending breakdown
- 💳 **Multiple Payment Methods** - Cash, UPI, Card tracking
- 🌙 **Dark Mode** - Eye-friendly theme
- 📱 **Responsive Design** - Works on mobile, tablet, desktop
- ☁️ **Cloud Sync** - Access your data from any device
- 🔐 **Secure Login** - Firebase authentication

## 🚀 Live Demo

[View Live Demo](https://gkayush123-afk.github.io/Daily-Tracker-Money/)

## 🔧 Setup Instructions

### Firebase Configuration (For Cloud Sync)

1. **Create Firebase Project:**
   - Go to [Firebase Console](https://console.firebase.google.com/)
   - Click "Add project" and follow the steps
   - Once created, click on your project

2. **Enable Authentication:**
   - In Firebase Console, go to "Authentication" → "Sign-in method"
   - Enable "Email/Password"

3. **Enable Realtime Database:**
   - Go to "Realtime Database" → "Create Database"
   - Choose location and start in **test mode** (for development)
   - **Important:** Update security rules:
   ```json
   {
     "rules": {
       "users": {
         "$uid": {
           ".read": "$uid === auth.uid",
           ".write": "$uid === auth.uid"
         }
       }
     }
   }
   ```

4. **Get Firebase Config:**
   - Go to Project Settings (gear icon) → General
   - Scroll to "Your apps" → Web app
   - Copy the `firebaseConfig` object

5. **Update Config in Code:**
   - Open `index.html`
   - Find the Firebase configuration section (around line 1212)
   - Replace the placeholder values with your actual Firebase config:
   ```javascript
   const firebaseConfig = {
       apiKey: "YOUR_ACTUAL_API_KEY",
       authDomain: "your-project.firebaseapp.com",
       projectId: "your-project-id",
       storageBucket: "your-project.appspot.com",
       messagingSenderId: "123456789012",
       appId: "1:123456789012:web:abc123",
       databaseURL: "https://your-project-default-rtdb.firebaseio.com"
   };
   ```

## 📖 Usage

### Without Firebase (Local Only)
- Open `index.html` in any browser
- Data saves to browser's localStorage
- Works offline but doesn't sync across devices

### With Firebase (Cloud Sync)
1. Complete Firebase setup above
2. Open the website
3. Create an account (Sign Up tab)
4. Login and start tracking!
5. Your data automatically syncs across all devices

## 🎯 How to Use

1. **Sign Up/Login** - Create account for cloud sync
2. **Quick Add** - Use the top form for fast expense entry
3. **Add Income** - Click green "Add Income" button
4. **Set Budget** - Go to Settings ⚙️ → Budget Settings
5. **View Analytics** - Scroll down for insights and charts
6. **Track Goals** - Click "Goals" to set savings targets
7. **Export Data** - Download CSV/PDF reports anytime

## 📱 Features Overview

### Quick Add Expense
- Amount, Category, Note (optional)
- One-click add with auto-date

### Dashboard Cards
- Available Balance
- Monthly Income
- Monthly Spend
- Savings Amount

### Smart Insights
- Highest spending category
- Wasteful spending %
- Savings rate
- Month-over-month comparison
- Budget alerts

### Charts
- Category breakdown (Doughnut)
- Daily spending trend (Line)
- Month comparison (Bar)
- Payment method breakdown
- Weekly breakdown

### Recurring Expenses
- Set day of month
- Auto-adds expenses
- Perfect for bills/subscriptions

### Savings Goals
- Multiple goals
- Progress tracking
- Target dates

## 🔒 Security

- Firebase Authentication for secure login
- Data stored per-user in Firebase Realtime Database
- Each user can only access their own data
- No data visible to other users

## 💾 Backup

Even with cloud sync, you can:
1. Settings → Download Backup (JSON file)
2. Keep backup files safe
3. Restore anytime with "Restore Backup"

## 🌐 Browser Support

- Chrome (recommended)
- Firefox
- Safari
- Edge
- Mobile browsers

## 📝 License

Free to use for personal projects.

## 👨‍💻 Author

Created with ❤️ by Ayush Kumar

## 🤝 Contributing

Feel free to fork and submit pull requests!

## 📧 Support

For issues or questions, open an issue on GitHub.

---

**Note:** This project uses Firebase for cloud sync. You need to set up your own Firebase project (free tier available) to enable multi-device sync.
