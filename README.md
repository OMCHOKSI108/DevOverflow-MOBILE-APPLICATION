# DevOverflow - Mobile Q&A Application

A comprehensive question-and-answer platform designed for developers, featuring a Flutter mobile application and a robust Node.js backend API. The platform combines Stack Overflow-style Q&A functionality with social features, AI integration, and gamification elements.

## Table of Contents

- [Project Overview](#project-overview)
- [Architecture](#architecture)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Getting Started](#getting-started)
- [Backend API](#backend-api)
- [Mobile Application](#mobile-application)
- [Documentation](#documentation)
- [Deployment](#deployment)
- [Team](#team)
- [License](#license)

## Project Overview

DevOverflow is a full-stack mobile application that enables developers to:

- Ask and answer technical questions
- Build reputation through community engagement
- Discover and connect with other developers
- Bookmark valuable content for future reference
- Receive AI-powered assistance for coding queries
- Participate in gamified learning experiences

## Architecture

```
DevOverflow-MOBILE-APPLICATION/
├── backend/                 # Node.js Express API Server
│   ├── controllers/         # API endpoint handlers
│   ├── models/             # MongoDB data models
│   ├── routes/             # API route definitions
│   ├── middleware/         # Authentication & validation
│   ├── docs/               # API documentation
│   └── POSTMAN/            # API testing collections
└── devoverflow/            # Flutter mobile application
    ├── lib/                # Flutter source code
    ├── android/            # Android platform files
    ├── ios/                # iOS platform files
    └── docs/               # Mobile app documentation
```

## Features

### Core Functionality
- **User Authentication**: JWT-based registration, login, and email verification
- **Question Management**: Create, edit, delete, and search questions with tags
- **Answer System**: Comprehensive answering with voting and acceptance features
- **Comment System**: Threaded comments on questions and answers
- **Voting Mechanism**: Upvote/downvote system for content quality control
- **Reputation System**: Point-based user reputation with leaderboards

### Social Features
- **User Profiles**: Comprehensive profile management with bio and activity tracking
- **Friend System**: Connect with other developers and track friend activities
- **Bookmarks**: Save interesting questions and organize collections
- **Notifications**: Real-time updates for user interactions and content changes

### Advanced Features
- **AI Integration**: Google Gemini-powered chatbot for coding assistance
- **Search & Discovery**: Advanced search with filtering and sorting capabilities
- **Content Moderation**: Admin panel for content management and user moderation
- **File Upload**: Cloudinary integration for image and document uploads
- **Email Services**: Automated email notifications and password reset functionality

### Gamification
- **Reputation Points**: Earn points through quality contributions
- **Achievement System**: Unlock achievements for various activities
- **Leaderboards**: Compete with other developers in knowledge sharing
- **Progress Tracking**: Monitor learning progress and contribution statistics

## Technology Stack

### Backend
- **Runtime**: Node.js 18+
- **Framework**: Express.js 4.18
- **Database**: MongoDB with Mongoose ODM
- **Authentication**: JWT (JSON Web Tokens)
- **File Storage**: Cloudinary CDN
- **Email Service**: Nodemailer with Gmail SMTP
- **AI Integration**: Google Gemini API
- **Documentation**: MkDocs with Material theme

### Mobile Application
- **Framework**: Flutter 3.8.1+
- **Language**: Dart
- **State Management**: Provider/Riverpod
- **HTTP Client**: Dio/HTTP package
- **Local Storage**: SharedPreferences & Secure Storage
- **UI Components**: Material Design 3

### Development Tools
- **API Testing**: Postman collections
- **Version Control**: Git with GitHub
- **Deployment**: Render.com (Backend), GitHub Pages (Documentation)
- **Environment Management**: dotenv for configuration

## Getting Started

### Prerequisites
- Node.js 18 or higher
- Flutter SDK 3.8.1 or higher
- MongoDB database (local or cloud)
- Gmail account for email services
- Cloudinary account for file uploads
- Google Gemini API key

### Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create environment file:
   ```bash
   cp .env.example .env
   ```

4. Configure environment variables:
   ```env
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   EMAIL_USER=your_gmail_address
   EMAIL_PASS=your_gmail_app_password
   CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
   CLOUDINARY_API_KEY=your_cloudinary_api_key
   CLOUDINARY_API_SECRET=your_cloudinary_api_secret
   GEMINI_API_KEY=your_google_gemini_api_key
   ```

5. Start the development server:
   ```bash
   npm run dev
   ```

### Mobile Application Setup

1. Navigate to the Flutter directory:
   ```bash
   cd devoverflow
   ```

2. Install Flutter dependencies:
   ```bash
   flutter pub get
   ```

3. Configure environment variables:
   ```bash
   # Create .env file in the devoverflow directory
   API_BASE_URL=https://devoverflow-backend.onrender.com/api
   ```

4. Run the application:
   ```bash
   flutter run
   ```

## Backend API

The backend API is deployed and accessible at: **https://devoverflow-backend.onrender.com**

### API Documentation
- **Interactive Documentation**: Available at the deployed backend URL
- **Postman Collections**: Located in `backend/POSTMAN/` directory
- **MkDocs Documentation**: Comprehensive API reference with examples

### Key Endpoints
- **Authentication**: `/api/auth/` (register, login, password reset)
- **Questions**: `/api/questions/` (CRUD operations, search, voting)
- **Answers**: `/api/answers/` (create, update, vote, accept)
- **Users**: `/api/users/` (profiles, friends, reputation)
- **AI Features**: `/api/ai/` (chatbot, code suggestions)
- **Admin Panel**: `/api/admin/` (content moderation, user management)

### Authentication
All protected endpoints require a JWT token in the Authorization header:
```
Authorization: Bearer <your_jwt_token>
```

## Mobile Application

The Flutter mobile application provides a native experience across iOS and Android platforms with:

### Key Features
- Responsive Material Design UI
- Offline capability with local caching
- Push notifications for real-time updates
- Dark/light theme support
- Advanced search and filtering
- Rich text editor for questions and answers
- Image upload and preview functionality

### Supported Platforms
- Android 5.0+ (API level 21+)
- iOS 11.0+

## Documentation

Comprehensive documentation is available in multiple formats:

1. **API Documentation**: `backend/docs/` directory containing:
   - Complete API reference
   - Authentication guides
   - Data model specifications
   - Integration examples

2. **Mobile Integration Guide**: Step-by-step guide for mobile developers
3. **Postman Collections**: Ready-to-use API testing collections
4. **MkDocs Site**: Interactive documentation with search functionality

## Deployment

### Backend Deployment (Render.com)
The backend is deployed on Render.com with:
- Automatic deployments from GitHub
- Environment variable management
- SSL/TLS encryption
- Global CDN distribution

**Live API**: https://devoverflow-backend.onrender.com

### Documentation Deployment
API documentation is built using MkDocs and can be deployed to:
- GitHub Pages
- Netlify
- Vercel
- Custom hosting platforms

### Mobile App Distribution
- **Android**: APK build for direct installation
- **iOS**: IPA build for TestFlight or App Store distribution
- **Development**: Flutter development server for testing

## Team

**Academic Project - Mobile Application Development Course**

### Development Team
- **OM CHOKSI** (23AIML010)
  - GitHub: [@omchoksi108](https://github.com/omchoksi108)
  - Role: Full-stack development, API design, mobile integration

- **DEV PATEL** (23AIML047)  
  - GitHub: [@devpatel0005](https://github.com/devpatel0005)
  - Role: Mobile app development, UI/UX design, testing

### Repository
- **GitHub**: [DevOverflow-MOBILE-APPLICATION](https://github.com/OMCHOKSI108/DevOverflow-MOBILE-APPLICATION)
- **License**: Educational/Academic Use

## License

This project is developed for educational purposes as part of the Mobile Application Development course. All rights reserved to the development team and academic institution.

---

**Note**: This is an academic project designed to demonstrate full-stack mobile application development capabilities, including API design, mobile app development, and modern deployment practices.