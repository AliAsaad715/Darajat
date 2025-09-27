# Darajat Educational Platform 📚

[![Flutter](https://img.shields.io/badge/Flutter-Framework-blue?logo=flutter)](https://flutter.dev/)
[![Laravel](https://img.shields.io/badge/Laravel-API-red?logo=laravel)](https://laravel.com/)
[![Livewire](https://img.shields.io/badge/Livewire-Dashboard-orange)](https://laravel-livewire.com/)

**Inspired by the Quranic verse:** { يرفع الله الذين آمنوا منكم والذين أوتوا العلم درجات }

Darajat is an innovative educational platform designed to facilitate knowledge sharing and learning through interactive courses, assessments, and community engagement.

## ✨ Features

### 🎓 Learning Experience
- **Video Courses** in various sciences and specialties 💻
- **Interactive Environment** (comments, replies, likes, views, ratings, attachment of explanation files) 👨‍💻
- **Detailed Profile** showcasing expertise, skills, and educational achievements 👤
- **Course Publishing** and knowledge sharing 👨‍🏫
- **Course Categorization** and easy search functionality 🔎
- **Exams and Certificates** delivered via email 📝

### 🎯 User Engagement
- **Notification System** 🔔
- **Motivation Flame** to track continuity and progress 🔥
- **Tasks and Incentive Badges** 🎖
- **OTP Verification** or **Google Authentication** for account creation 🚪

### 💰 Monetization
- **Electronic Payment System** 💸
- **Payment Process Notifications** via email 📨
- **Electronic Wallet** for earnings 👝

### 👨‍💼 Admin Dashboard
- **Course Management** 🔧
- **Content Filtering** for inappropriate material 🫣
- **Publication Request Control** 🖋
- **Platform Statistics** and user information viewing 📈
- **User Banning** for usage policy violations ⛔️

## 🛠 Technology Stack

**Frontend:** Flutter (Hamza Al-Najjar)  
https://github.com/hamza-alnaggar/Darajat.git

**Backend API:** Laravel (Ali Asaad + Omar Al-Dalati)  
**Admin Dashboard:** Laravel + Livewire with Blade (Omar Al-Dalati)

## 📸 Screenshots

You can view all screenshots of the project here:  
👉 [Screenshots Folder](./Screenshots)

## 🧪 API Testing with Postman
Postman Collection
We provide a comprehensive Postman collection for testing API endpoints:                                                     
👉 [Postman Collection](https://documenter.getpostman.com/view/39537559/2sB2xCi9dr#1008275a-b31a-4725-99a1-6424744718f1)

## 🚀 Getting Started

### Prerequisites
- Flutter SDK
- PHP >= 7.4
- Composer
- MySQL


### Installation

1. Clone the repository:
```bash
git clone https://github.com/AliAsaad715/Darajat
cd Darajat
```

2. Install backend dependencies:
```bash
cd backend
composer install
```

3. Set up environment configuration:
```bash
cp .env.example .env
php artisan key:generate
```

4. Configure your database settings in the `.env` file

5. Run migrations:
```bash
php artisan migrate
```

6. Install frontend dependencies:
```bash
cd ../frontend
flutter pub get
```

7. Run the application:
```bash
flutter run
```


### 📋 External Services

Before you can run this project, you must create accounts and set up the following services:

#### 1. Firebase Project
- **Purpose:** Used for **Push Notifications** (FCM) and **Google Authentication**.
- **Setup:** 
  1. Create a project in the [Firebase Console](https://console.firebase.google.com/)
  2. Enable Authentication (with Google sign-in) and Cloud Messaging
  3. Download the `google-services.json` (Android) and `GoogleService-Info.plist` (iOS) files
  4. Place these files in the appropriate directories in your Flutter project

#### 2. Stripe Account
- **Purpose:** Handles all electronic payments and payouts to instructors.
- **Setup:**
  1. Create a developer account at [Stripe](https://stripe.com/)
  2. Obtain your **Publishable Key** and **Secret Key** from the dashboard
  3. **Webhook Setup** (Essential for payment confirmation):
     - **Option 1 - Using ngrok** (Recommended for simplicity):
       ```bash
       # Install ngrok from https://ngrok.com/
       ngrok http 8000
       ```
     - **Option 2 - Using Stripe CLI**:
       ```bash
       # Install Stripe CLI from https://stripe.com/docs/stripe-cli
       stripe login
       stripe listen --forward-to localhost:8000/api/stripe/webhook
       ```
  4. In Stripe Dashboard → Developers → Webhooks, add your endpoint URL:
     - For ngrok: `https://your-ngrok-url.ngrok.io/api/stripe/webhook`
     - For CLI: Use the URL provided by the CLI
  5. Subscribe to these events: `payment_intent.succeeded`, `payment_intent.payment_failed`
  6. Add the webhook **Signing Secret** to your `.env` file
 
#### 3. Certifier Service Setup
- **Purpose:** Used to automatically generate and issue professional course completion certificates for users.
- **Setup:**
  1. **Create an Account:**
     - Sign up for a Certifier account at [certifier.io](https://certifier.io/) (or your chosen certificate service)
  
  2. **Obtain API Credentials:**
     - After registration, navigate to your account settings or API section
     - Generate an **Access Key** or **API Key** for authentication
     - Copy this key for use in your environment configuration

  3. **Create Certificate Templates:**
     - In your Certifier account, create certificate templates for different courses
     - Design templates with your preferred layout, logos, and signature fields
     - Configure dynamic fields (student name, course name, date, etc.)
     - Note the **Group ID** for each certificate template
    
  4. **Configure Dynamic Fields:**
     - Map your course and user data and **Group ID** with to Certifier's dynamic fields in the `getCertificate` function


## 📱 Platform Structure

```
darajat-platform/
├── backend/          # Laravel API
├── frontend/         # Flutter Application
└── dashboard/        # Admin Dashboard (Laravel + Livewire)
```

## 🤝 Contributing

We welcome contributions to Darajat Educational Platform! Please feel free to submit pull requests or open issues for bugs and feature requests.


## 📞 Contact

For questions or support, please contact us:
ali715asaad@gmail.com

---
