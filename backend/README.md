# DevOverflow Backend

## Description

The DevOverflow Backend is a robust RESTful API server built with Node.js and Express, serving as the core engine for the DevOverflow mobile Q&A platform. This backend provides comprehensive functionality for a developer-focused question and answer application, incorporating social features, gamification, AI assistance, and real-time capabilities.

The API handles user authentication, content management, social interactions, file uploads, and administrative operations. It integrates with MongoDB for data persistence, Google Generative AI for content assistance, and Cloudinary for media storage. The backend is designed to support cross-platform mobile applications while maintaining high performance and security standards.

## Features

### Core Functionality
- User registration and authentication with JWT tokens
- Email verification and password reset capabilities
- Profile management with customizable avatars and bios
- Question and answer management with rich text support
- Voting system for answers with reputation tracking
- Comment system for detailed discussions
- Bookmarking functionality for saving favorite content

### Social Features
- User following and friend networks
- Group creation and management
- Real-time chat messaging
- Notification system for user activities

### Advanced Features
- AI-powered content generation and suggestions using Google Generative AI
- Gamification system with badges and reputation points
- Comprehensive search and filtering capabilities
- File upload support with Cloudinary integration
- Admin panel for content moderation and user management
- Rate limiting and security middleware

### Technical Features
- RESTful API design with consistent endpoints
- CORS configuration for mobile app integration
- Compression and optimization for performance
- Comprehensive error handling and logging
- Database indexing for efficient queries

## Tech Stack

### Runtime Environment
- **Node.js**: Server-side JavaScript runtime (version 18.0.0 or higher)
- **Express.js**: Web application framework for building APIs

### Database
- **MongoDB**: NoSQL database for data storage
- **Mongoose**: ODM for MongoDB with schema validation

### Authentication & Security
- **JWT (JSON Web Tokens)**: Token-based authentication
- **bcryptjs**: Password hashing
- **express-rate-limit**: API rate limiting

### External Services
- **Google Generative AI**: AI-powered content assistance
- **Cloudinary**: Cloud-based media storage and management
- **Nodemailer**: Email service for notifications and verification

### Development Tools
- **Nodemon**: Development server with auto-restart
- **Compression**: Response compression middleware

### Additional Libraries
- **Axios**: HTTP client for external API calls
- **Multer**: File upload handling
- **Marked**: Markdown parsing
- **Sanitize-HTML**: HTML sanitization for security

## Prerequisites

Before setting up the backend, ensure you have the following installed:

- **Node.js**: Version 18.0.0 or higher
- **MongoDB**: Local installation or MongoDB Atlas account
- **Git**: Version control system
- **npm**: Node package manager (comes with Node.js)

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/OMCHOKSI108/Devoverflow-Backend.git
cd Devoverflow-Backend/backend
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Environment Configuration

Create a `.env` file in the backend root directory with the following required variables:

```env
# Database Configuration
MONGODB_URI=mongodb://localhost:27017/devoverflow
# For MongoDB Atlas, use:
# MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/devoverflow

# JWT Configuration
JWT_SECRET=your_super_secret_jwt_key_here
JWT_EXPIRE=30d

# Admin User Configuration
ADMIN_NAME=DevOverflow Admin
ADMIN_USERNAME=admin
ADMIN_EMAIL=admin@devoverflow.com
ADMIN_PASSWORD=admin123
ADMIN_LOCATION=Your City

# Google Gemini AI API Configuration
GEMINI_API_KEY=your_gemini_api_key_here

# Email Configuration (for notifications and verification)
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_app_password

# Cloudinary Configuration (for file uploads)
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret

# Optional: Application Port
PORT=5000
```

## Running the Application

### Development Mode

```bash
npm run dev
```

This starts the server with Nodemon, which automatically restarts on file changes.

### Production Mode

```bash
npm start
```

### Admin Panel Setup

The backend includes an admin panel for content management:

```bash
# Install admin panel dependencies
npm run admin:install

# Start admin panel in development mode
npm run admin
```

## API Documentation

The backend provides comprehensive API documentation available in the `docs/` directory:

- `API_DOCS.md`: Complete API endpoint reference with examples
- `API_ENDPOINTS_DOCUMENTATION.txt`: Detailed endpoint specifications
- `API_ENDPOINTS_SPECIFICATION.txt`: Technical specifications
- `authentication.md`: Authentication flow documentation
- `data-models.md`: Database schema and model definitions
- `error-handling.md`: Error response formats and handling

### API Base URL
```
http://localhost:5000/api
```

### Key API Endpoints

- **Authentication**: `/api/auth` - User registration, login, verification
- **Questions**: `/api/questions` - CRUD operations for questions
- **Answers**: `/api/answers` - Answer management and voting
- **Users**: `/api/users` - User profiles and social features
- **AI**: `/api/ai` - AI-powered content assistance
- **Admin**: `/api/admin` - Administrative operations
- **Upload**: `/api/upload` - File upload handling

All protected endpoints require JWT authentication via the Authorization header:
```
Authorization: Bearer <your-jwt-token>
```

## Database Models

The application uses MongoDB with the following primary data models:

- **User**: User accounts with profiles, reputation, and badges
- **Question**: Questions with tags, categories, and metadata
- **Answer**: Answers with voting and acceptance tracking
- **Comment**: Comments on questions and answers
- **Bookmark**: User bookmarks for saved content
- **ChatMessage/ChatSession**: Real-time messaging system
- **Group**: User groups and communities
- **Notification**: User notifications and activity feeds
- **Report**: Content moderation reports

Each model includes automatic timestamps and follows consistent validation rules.

## Testing

### Running Tests

```bash
npm test
```

### Test Setup

```bash
npm run test:setup
```

The test suite includes API endpoint testing and database seeding utilities.

## Deployment

The backend is configured for deployment on platforms like Render, Heroku, or AWS. Key deployment considerations:

- Environment variables must be configured in the deployment platform
- MongoDB connection should use a cloud instance (MongoDB Atlas recommended)
- CORS settings should be configured for production domains
- Rate limiting and security middleware are production-ready

Refer to `docs/DEPLOYMENT_GUIDE.md` for detailed deployment instructions.

## Security Features

- JWT-based authentication with configurable expiration
- Password hashing using bcryptjs
- Input sanitization and validation
- Rate limiting to prevent abuse
- CORS configuration for cross-origin requests
- Secure file upload handling
- Admin-only endpoints for sensitive operations

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure all contributions include appropriate tests and documentation updates.

## License

This project is licensed under the ISC License. See the LICENSE file for details.

## Support

For support and questions:
- Check the documentation in the `docs/` directory
- Review existing issues on GitHub
- Create a new issue for bugs or feature requests

## Version

Current version: 1.0.0