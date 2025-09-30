# DevOverflow API Testing - Postman Collections

This directory contains comprehensive Postman collections for testing all DevOverflow backend APIs. The collections are organized by functionality and include both public and protected endpoints.

## 📁 Collection Files

### Core Collections
1. **Authentication_API_Collection.json** - Complete authentication system
2. **Questions_Answers_API_Collection.json** - Q&A functionality  
3. **Users_Social_API_Collection.json** - User management and social features
4. **Comments_Bookmarks_API_Collection.json** - Comments and bookmarking system
5. **Chat_Groups_Gamification_API_Collection.json** - Chat, groups, and gamification
6. **Search_Notifications_Upload_API_Collection.json** - Search, notifications, and file upload
7. **Admin_API_Collection.json** - Admin panel and moderation tools
8. **DevOverflow_AI_Postman_Collection.json** - AI-powered features (existing)

### Environment Files
- **DevOverflow_Complete_Environment.json** - Complete environment variables
- **DevOverflow_Environment.postman_environment.json** - Basic environment (existing)

### Legacy Files
- **FINAL_ALL_API.json** - Previous comprehensive collection (existing)

## 🚀 Quick Start

### 1. Import Collections
1. Open Postman
2. Click **Import** button
3. Select all `.json` files from this directory
4. Import the environment file: `DevOverflow_Complete_Environment.json`

### 2. Set Environment
1. Select "DevOverflow Complete Environment" from environment dropdown
2. Update `base_url` if your backend runs on different port
3. The `jwt_token` will be auto-populated when you login

### 3. Authentication Flow
1. Run **Authentication API → Public Auth Endpoints → Login User**
2. The JWT token will be automatically saved to environment
3. Now you can test protected endpoints

## 📋 Collection Details

### 🔐 Authentication API Collection
- **Public Routes**: Register, Login, Email Verification, Password Reset
- **Protected Routes**: Profile Management, Password Change
- **Features**: Auto JWT token extraction and environment variable setting

### ❓ Questions & Answers API Collection  
- **Questions**: CRUD operations, voting, search, filtering
- **Answers**: Create, update, delete, vote, accept answers
- **Features**: Pagination, sorting, tag filtering

### 👥 Users & Social API Collection
- **User Management**: Profiles, settings, reputation, activity
- **Social Features**: Follow/unfollow, friends, user discovery
- **Notifications**: Mark as read, bulk operations

### 💬 Comments & Bookmarks API Collection
- **Comments**: Add to questions/answers, edit, delete
- **Bookmarks**: Save questions, organize, search bookmarks
- **Features**: Legacy and new bookmark API support

### 🎮 Chat, Groups & Gamification API Collection
- **Chat System**: Sessions, messages, direct messaging
- **Groups**: Create, join, group-specific questions
- **Gamification**: Reputation, badges, leaderboards, privileges

### 🔍 Search, Notifications & Upload API Collection
- **Advanced Search**: Multi-criteria search with filters
- **Notifications**: Real-time notification management
- **File Upload**: Images, attachments, avatar uploads

### ⚙️ Admin API Collection
- **User Management**: Ban, suspend, promote users
- **Content Moderation**: Edit/delete questions, answers, comments
- **Reporting System**: Handle reports, moderation actions
- **Analytics**: Admin statistics and insights

### 🤖 AI API Collection (Existing)
- **AI Features**: Question suggestions, answer generation, tag suggestions
- **Chatbot**: AI-powered assistance
- **Flowcharts**: Generate and render flowcharts

## 🔧 Environment Variables

### Auto-Populated Variables
- `jwt_token` - Automatically set by login requests
- `base_url` - API base URL
- `api_base_url` - Full API path

### Test Data Variables
- `sample_question_id` - Set after creating a question
- `sample_answer_id` - Set after creating an answer  
- `sample_user_id` - Set after user operations
- `admin_email` / `admin_password` - Default admin credentials
- `test_user_email` / `test_user_password` - Default test user

## 📝 Testing Workflow

### Basic Testing Flow
1. **Setup**: Import collections and environment
2. **Authenticate**: Login as admin or test user
3. **Create Content**: Create questions, answers, comments
4. **Test Features**: Vote, bookmark, follow users
5. **Admin Tasks**: Test moderation, user management

### Advanced Testing
1. **Bulk Operations**: Test pagination, bulk updates
2. **Edge Cases**: Invalid data, permissions, rate limiting
3. **Integration**: Test cross-feature functionality
4. **Performance**: Large datasets, concurrent requests

## 🛠️ API Coverage

### Complete Endpoint Coverage
- ✅ Authentication (Login, Register, Password Reset)
- ✅ Questions & Answers (CRUD, Voting, Search)
- ✅ Users & Profiles (Management, Social Features)
- ✅ Comments & Bookmarks (Organization, Search)
- ✅ Chat & Groups (Messaging, Communities)
- ✅ Gamification (Reputation, Badges, Leaderboards)
- ✅ Search & Notifications (Real-time, Advanced Search)
- ✅ Admin & Moderation (User Management, Content Control)
- ✅ File Upload (Images, Attachments)
- ✅ AI Features (Suggestions, Chatbot, Flowcharts)

### HTTP Methods Covered
- **GET**: Data retrieval, search, filtering
- **POST**: Create operations, authentication
- **PUT**: Update operations, settings
- **DELETE**: Remove content, cleanup

### Authentication Types
- **Public**: No authentication required
- **Protected**: JWT token required
- **Admin Only**: Admin role required

## 🎯 Best Practices

### Request Organization
- Collections organized by feature area
- Folders separate public vs protected endpoints
- Descriptive names and documentation

### Environment Management
- Use environment variables for reusable data
- Auto-populate tokens and IDs where possible
- Separate development/production environments

### Testing Strategy
- Test public endpoints first
- Authenticate before protected endpoints
- Create test data before testing operations
- Clean up test data when needed

## 🔍 Troubleshooting

### Common Issues
1. **401 Unauthorized**: Check JWT token is set in environment
2. **404 Not Found**: Verify endpoint URLs and IDs
3. **500 Server Error**: Check backend server is running
4. **Validation Errors**: Review request body format

### Debug Tips
- Check Postman Console for detailed request/response
- Verify environment variables are populated
- Test with Postman's built-in API documentation
- Use test scripts for automated validation

## 📈 Future Enhancements

### Planned Additions
- Automated test scripts with assertions
- Mock server configurations
- Performance testing scenarios
- API documentation generation
- CI/CD integration examples

---

**Note**: Keep this documentation updated as new endpoints are added or existing ones are modified. Each collection includes comprehensive examples and is ready for immediate testing.