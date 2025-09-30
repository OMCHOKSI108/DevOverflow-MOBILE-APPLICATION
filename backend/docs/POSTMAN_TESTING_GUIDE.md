# Postman API Testing Guide

This guide explains how to set up and use the comprehensive Postman collections for testing the DevOverflow backend API.

## Overview

The DevOverflow backend includes 8 organized Postman collections covering all API endpoints:

1. **Authentication API** - User registration, login, password management
2. **Questions & Answers API** - Q&A functionality with CRUD operations
3. **Users & Social API** - User management, social features, friends
4. **Comments & Bookmarks API** - Comments and bookmarking system
5. **Chat, Groups & Gamification API** - Chat, groups, and gamification features
6. **Search, Notifications & Upload API** - Search, notifications, file upload
7. **Admin API** - Complete admin panel and moderation tools
8. **AI Features API** - AI-powered features and suggestions

## Quick Setup

### Step 1: Import Collections

1. Open Postman
2. Click **Import** button
3. Navigate to `/backend/POSTMAN/` directory
4. Select all `.json` files and import them
5. Import the environment file: `DevOverflow_Complete_Environment.json`

### Step 2: Set Environment

1. Select "DevOverflow Complete Environment" from the environment dropdown
2. Update `base_url` if your backend runs on a different port (default: `http://localhost:3000`)
3. The `jwt_token` will be automatically populated when you login

### Step 3: Start Testing

1. Run **Authentication API → Login User** first
2. The JWT token will be automatically saved to environment variables
3. Now you can test any protected endpoints

## Collection Details

### 🔐 Authentication API Collection

**File:** `Authentication_API_Collection.json`

**Features:**
- Auto JWT token extraction and environment variable setting
- Complete auth flow testing
- Password reset functionality
- Profile management

**Key Endpoints:**
- User Registration and Admin Registration
- Login with automatic token saving
- Email verification and resend
- Password reset flow
- Profile updates and password changes

**Testing Flow:**
```
1. Register new user OR Login existing user
2. JWT token automatically saved
3. Test profile management endpoints
4. Test password change functionality
```

### ❓ Questions & Answers API Collection

**File:** `Questions_Answers_API_Collection.json`

**Features:**
- Complete CRUD operations for questions and answers
- Voting system testing
- Search and filtering
- Pagination support

**Key Endpoints:**
- Create, read, update, delete questions
- Create, read, update, delete answers
- Vote on questions and answers
- Accept answers
- Search with filters

**Testing Flow:**
```
1. Create a new question
2. Create answers for the question
3. Test voting on both questions and answers
4. Test answer acceptance
5. Test search and filtering
```

### 👥 Users & Social API Collection

**File:** `Users_Social_API_Collection.json`

**Features:**
- User profile management
- Social features (follow/unfollow, friends)
- User discovery and suggestions
- Notification management

**Key Endpoints:**
- User profiles and settings
- Friend management
- Follow/unfollow functionality
- User suggestions and discovery
- Notification management

**Testing Flow:**
```
1. Get and update user profile
2. Search for other users
3. Add friends and follow users
4. Test notification system
5. Check user activity and reputation
```

### 💬 Comments & Bookmarks API Collection

**File:** `Comments_Bookmarks_API_Collection.json`

**Features:**
- Comment system for questions and answers
- Bookmark management
- Legacy bookmark API support

**Key Endpoints:**
- Add comments to questions/answers
- Edit and delete comments
- Bookmark questions
- Manage bookmark collections

**Testing Flow:**
```
1. Add comments to questions and answers
2. Edit and delete comments
3. Bookmark questions
4. Manage bookmark collections
```

### 🎮 Chat, Groups & Gamification API Collection

**File:** `Chat_Groups_Gamification_API_Collection.json`

**Features:**
- Real-time chat functionality
- Group management and participation
- Gamification system (reputation, badges, leaderboards)

**Key Endpoints:**
- Chat sessions and messaging
- Group creation and management
- Reputation and badge system
- Leaderboards and achievements

**Testing Flow:**
```
1. Create chat sessions
2. Send and receive messages
3. Create and join groups
4. Check reputation and badges
5. View leaderboards
```

### 🔍 Search, Notifications & Upload API Collection

**File:** `Search_Notifications_Upload_API_Collection.json`

**Features:**
- Advanced search with filters
- Notification management
- File upload functionality
- Alternative friend API routes

**Key Endpoints:**
- Advanced search with multiple criteria
- Notification CRUD operations
- File uploads (images, documents)
- Alternative friend management routes

**Testing Flow:**
```
1. Test advanced search with various filters
2. Manage notifications
3. Upload files and attachments
4. Test alternative API routes
```

### ⚙️ Admin API Collection

**File:** `Admin_API_Collection.json`

**Features:**
- Complete administrative functionality
- User management and moderation
- Content management
- Comprehensive analytics

**Key Endpoints:**
- User management (ban, suspend, promote)
- Content moderation (edit, delete)
- Report handling
- Admin analytics and statistics

**Testing Flow:**
```
1. Login as admin user
2. View admin statistics
3. Manage users (promote, ban, etc.)
4. Moderate content
5. Handle reports
```

### 🤖 AI Features API Collection

**File:** `DevOverflow_AI_Postman_Collection.json` (existing)

**Features:**
- AI-powered question suggestions
- Answer generation
- Tag suggestions
- Flowchart creation

## Environment Variables

### Core Variables

| Variable | Description | Auto-Populated |
|----------|-------------|----------------|
| `base_url` | API base URL | No |
| `api_base_url` | Full API path | No |
| `jwt_token` | Authentication token | Yes (on login) |

### Test Data Variables

| Variable | Description | Usage |
|----------|-------------|-------|
| `admin_email` | Default admin email | Login testing |
| `admin_password` | Default admin password | Login testing |
| `test_user_email` | Test user email | General testing |
| `test_user_password` | Test user password | General testing |
| `sample_question_id` | Sample question ID | Populate after creating |
| `sample_answer_id` | Sample answer ID | Populate after creating |
| `sample_user_id` | Sample user ID | User operations |

### Environment Setup

1. **Development Environment:**
   ```
   base_url: http://localhost:3000
   api_base_url: http://localhost:3000/api
   ```

2. **Production Environment:**
   ```
   base_url: https://your-production-domain.com
   api_base_url: https://your-production-domain.com/api
   ```

## Testing Workflows

### Basic Testing Workflow

1. **Authentication Setup**
   ```
   1. Import collections and environment
   2. Run "Login User" to get JWT token
   3. Token automatically saved to environment
   4. All protected endpoints now work
   ```

2. **Content Creation Flow**
   ```
   1. Create a question
   2. Create answers for the question
   3. Add comments to both
   4. Test voting and bookmarking
   5. Save IDs to environment variables
   ```

3. **Social Features Flow**
   ```
   1. Search for users
   2. Follow users and add friends
   3. Test notifications
   4. Check user activity
   ```

4. **Admin Testing Flow**
   ```
   1. Login as admin
   2. View dashboard statistics
   3. Test user management
   4. Test content moderation
   5. Handle reports
   ```

### Advanced Testing

1. **Pagination Testing**
   ```
   - Test with different page sizes
   - Navigate through multiple pages
   - Verify pagination metadata
   ```

2. **Search Testing**
   ```
   - Test basic text search
   - Test with filters and tags
   - Test sorting options
   - Test edge cases (empty results)
   ```

3. **Error Handling Testing**
   ```
   - Test with invalid IDs
   - Test unauthorized access
   - Test with malformed data
   - Test rate limiting
   ```

## Best Practices

### Request Organization

1. **Use Folders:** Collections are organized by functionality
2. **Descriptive Names:** Each request has a clear, descriptive name
3. **Documentation:** Each request includes descriptions and examples

### Variable Management

1. **Environment Variables:** Use variables for reusable data
2. **Auto-Population:** Leverage scripts to auto-populate tokens and IDs
3. **Multiple Environments:** Set up separate dev/staging/production environments

### Testing Strategy

1. **Sequential Testing:** Test public endpoints before protected ones
2. **Data Dependencies:** Create test data before testing operations on it
3. **Cleanup:** Clean up test data when needed
4. **Error Cases:** Test both success and error scenarios

### Collaboration

1. **Shared Collections:** Export and share collection files
2. **Environment Templates:** Provide environment templates for team members
3. **Documentation:** Keep collection documentation updated
4. **Version Control:** Track collection changes in version control

## Troubleshooting

### Common Issues

1. **401 Unauthorized**
   - Check if JWT token is set in environment
   - Verify token hasn't expired
   - Ensure you're logged in

2. **404 Not Found**
   - Verify endpoint URLs are correct
   - Check if resource IDs exist
   - Ensure backend server is running

3. **403 Forbidden**
   - Check if admin privileges are required
   - Verify user has necessary permissions
   - Ensure proper role assignment

4. **500 Server Error**
   - Check backend server logs
   - Verify database connection
   - Check for missing environment variables

### Debug Tips

1. **Console Logs:** Check Postman Console for detailed request/response
2. **Environment Check:** Verify all required environment variables are set
3. **Network Tab:** Use browser dev tools to inspect network requests
4. **Backend Logs:** Check backend server logs for errors

## Advanced Features

### Pre-request Scripts

Collections include pre-request scripts for:
- Token validation
- Dynamic variable generation
- Request preprocessing

### Test Scripts

Collections include test scripts for:
- Automatic token extraction
- Response validation
- Environment variable updates

### Mock Servers

Consider setting up Postman mock servers for:
- Frontend development before backend completion
- Testing error scenarios
- API documentation examples

## Integration with CI/CD

### Newman (Postman CLI)

```bash
# Install Newman
npm install -g newman

# Run collection
newman run collection.json -e environment.json

# Generate reports
newman run collection.json -e environment.json -r html,json
```

### Automated Testing

```javascript
// Example test script
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Response has required fields", function () {
    const jsonData = pm.response.json();
    pm.expect(jsonData).to.have.property('success');
    pm.expect(jsonData.success).to.be.true;
});
```

## Resources

- [Postman Documentation](https://learning.postman.com/docs/)
- [Newman CLI Tool](https://github.com/postmanlabs/newman)
- [API Testing Best Practices](https://learning.postman.com/docs/writing-scripts/test-scripts/)
- [Environment Management](https://learning.postman.com/docs/sending-requests/managing-environments/)

---

This guide provides comprehensive instructions for using the DevOverflow Postman collections effectively. For specific endpoint details, refer to the individual API documentation files in the `/docs/api/` directory.