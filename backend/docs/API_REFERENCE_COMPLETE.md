# API Reference Summary

This document provides a comprehensive overview of all available API endpoints in the DevOverflow backend system.

## Base URL

All API endpoints are prefixed with: `http://localhost:3000/api`

## Authentication

Most endpoints require authentication via Bearer token:
```
Authorization: Bearer <jwt_token>
```

Admin endpoints additionally require admin privileges (`isAdmin: true`).

## Endpoint Categories

### 1. Authentication (`/api/auth`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| POST | `/register` | No | User registration |
| POST | `/register-admin` | No | Admin registration |
| POST | `/login` | Yes | User login |
| GET | `/verify/:token` | No | Email verification |
| POST | `/resend-verification` | No | Resend verification email |
| POST | `/test-email` | No | Test email functionality |
| POST | `/setup-admin` | No | Setup admin (temporary) |
| POST | `/forgot-password` | No | Password reset request |
| POST | `/reset-password` | No | Reset password with token |
| GET | `/me` | Yes | Get current user profile |
| PUT | `/profile` | Yes | Update user profile |
| PUT | `/change-password` | Yes | Change user password |

### 2. Questions (`/api/questions`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/` | No | Get all questions with pagination |
| GET | `/search` | No | Search questions |
| GET | `/user/:userId` | No | Get questions by user |
| GET | `/:id` | No | Get question by ID |
| POST | `/` | Yes | Create new question |
| PUT | `/:id` | Yes | Update question |
| DELETE | `/:id` | Yes | Delete question |
| POST | `/:id/vote` | Yes | Vote on question |
| POST | `/:questionId/answers` | Yes | Create answer for question |

### 3. Answers (`/api/answers`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/question/:questionId` | No | Get answers by question |
| GET | `/user/:userId` | No | Get answers by user |
| PUT | `/:id` | Yes | Update answer |
| DELETE | `/:id` | Yes | Delete answer |
| POST | `/:id/vote` | Yes | Vote on answer |
| POST | `/:id/accept` | Yes | Accept answer |

### 4. Users (`/api/users`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/leaderboard` | No | Get user leaderboard |
| GET | `/search` | No | Search users |
| GET | `/:id/reputation` | No | Get user reputation |
| GET | `/:id/summary` | No | Get user summary |
| GET | `/:id/activity` | No | Get user activity |
| GET | `/:id/following` | No | Get user following list |
| GET | `/:id/followers` | No | Get user followers list |
| GET | `/:id` | No | Get user profile |
| GET | `/me` | Yes | Get current user profile |
| PUT | `/profile` | Yes | Update user profile |
| GET | `/` | Yes | Get all users (for friends search) |
| GET | `/friends` | Yes | Get user friends |
| POST | `/friends/:userId` | Yes | Add friend |
| DELETE | `/friends/:userId` | Yes | Remove friend |
| GET | `/settings` | Yes | Get user settings |
| PUT | `/settings` | Yes | Update user settings |
| GET | `/suggestions` | Yes | Get user suggestions |
| GET | `/notifications` | Yes | Get user notifications |
| PUT | `/notifications/read-all` | Yes | Mark all notifications as read |
| PUT | `/notifications/:id/read` | Yes | Mark notification as read |
| GET | `/:id/connection-status` | Yes | Get connection status |
| POST | `/:id/follow` | Yes | Follow user |
| DELETE | `/:id/follow` | Yes | Unfollow user |

### 5. Comments (`/api/comments`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/question/:questionId` | No | Get question comments |
| GET | `/answer/:answerId` | No | Get answer comments |
| POST | `/question/:questionId` | Yes | Add comment to question |
| POST | `/answer/:answerId` | Yes | Add comment to answer |
| PUT | `/:id` | Yes | Update comment |
| DELETE | `/:id` | Yes | Delete comment |

### 6. Bookmarks (`/api/bookmarks`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/` | Yes | Get user bookmarks |
| POST | `/` | Yes | Add bookmark |
| DELETE | `/:bookmarkId` | Yes | Remove bookmark |
| POST | `/question/:questionId` | Yes | Add question bookmark (legacy) |
| DELETE | `/question/:questionId` | Yes | Remove question bookmark (legacy) |
| GET | `/check/:questionId` | Yes | Check if question is bookmarked |

### 7. Chat (`/api/chat`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/sessions` | Yes | Get chat sessions |
| POST | `/sessions` | Yes | Create chat session |
| GET | `/sessions/:sessionId/messages` | Yes | Get chat messages |
| POST | `/sessions/:sessionId/messages` | Yes | Send chat message |
| DELETE | `/sessions/:sessionId` | Yes | Delete chat session |

### 8. Groups (`/api/groups`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/` | Yes | Get groups |
| POST | `/` | Yes | Create group |
| GET | `/:groupId` | Yes | Get group details |
| POST | `/:groupId/join` | Yes | Join group |
| POST | `/:groupId/leave` | Yes | Leave group |
| POST | `/:groupId/questions` | Yes | Post group question |
| GET | `/:groupId/questions` | Yes | Get group questions |

### 9. Gamification (`/api/gamification`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/reputation` | Yes | Get user reputation |
| GET | `/reputation/history` | Yes | Get reputation history |
| GET | `/badges` | Yes | Get user badges |
| GET | `/privileges` | Yes | Get user privileges |
| GET | `/leaderboard` | Yes | Get gamification leaderboard |

### 10. Search (`/api/search`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/` | Yes | Advanced search |
| GET | `/suggestions` | Yes | Get search suggestions |
| GET | `/trending` | Yes | Get trending topics |

### 11. Notifications (`/api/notifications`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/` | Yes | Get all notifications |
| PUT | `/:id/read` | Yes | Mark notification as read |
| PUT | `/read-all` | Yes | Mark all notifications as read |
| DELETE | `/:id` | Yes | Delete notification |

### 12. Upload (`/api/upload`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| POST | `/` | Yes | Upload file |

### 13. Friends (`/api/friends`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| POST | `/add` | Yes | Add friend (alternative route) |
| POST | `/remove` | Yes | Remove friend (alternative route) |
| GET | `/profile/:id?` | Yes | Get friend profile |
| GET | `/admin/all` | Yes (Admin) | Get all friendships (admin only) |
| GET | `/admin/stats` | Yes (Admin) | Get friendship stats (admin only) |
| DELETE | `/admin/remove` | Yes (Admin) | Admin remove friendship |

### 14. AI Features (`/api/ai`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| GET | `/status` | No | Get AI service status |
| POST | `/similar-questions` | No | Get similar questions |
| POST | `/answer-suggestion` | Yes | Get AI answer suggestion |
| POST | `/tag-suggestions` | Yes | Get AI tag suggestions |
| POST | `/chatbot` | Yes | AI chatbot interaction |
| POST | `/question-improvements` | Yes | Get question improvements |
| POST | `/flowchart` | Yes | Create flowchart |
| GET | `/flowchart/:id` | Yes | Get flowchart metadata |
| GET | `/flowchart/:id/render` | Yes | Get flowchart render status |

### 15. Admin (`/api/admin`)

| Method | Endpoint | Auth Required | Description |
|--------|----------|---------------|-------------|
| POST | `/reports` | Yes | Create report |
| GET | `/reports` | Yes (Admin) | Get all reports |
| PUT | `/reports/:id/resolve` | Yes (Admin) | Resolve report |
| GET | `/stats` | Yes (Admin) | Get admin statistics |
| DELETE | `/content/:type/:id` | Yes (Admin) | Delete content |
| GET | `/users` | Yes (Admin) | Get all users |
| PUT | `/users/:id` | Yes (Admin) | Manage user |
| DELETE | `/users/:id` | Yes (Admin) | Delete user |
| PUT | `/users/:id/details` | Yes (Admin) | Update user details |
| GET | `/questions` | Yes (Admin) | Get all questions |
| PUT | `/questions/:id` | Yes (Admin) | Edit question |
| GET | `/answers` | Yes (Admin) | Get all answers |
| PUT | `/answers/:id` | Yes (Admin) | Edit answer |
| GET | `/comments` | Yes (Admin) | Get all comments |
| POST | `/comments` | Yes (Admin) | Add comment |
| PUT | `/comments/:id` | Yes (Admin) | Edit comment |
| DELETE | `/comments/:id` | Yes (Admin) | Delete comment |

## Response Format

All endpoints return responses in the following format:

### Success Response
```json
{
    "success": true,
    "message": "Operation successful",
    "data": {
        // Response data here
    }
}
```

### Error Response
```json
{
    "success": false,
    "message": "Error description"
}
```

## HTTP Status Codes

| Code | Description |
|------|-------------|
| 200 | Success |
| 201 | Created |
| 400 | Bad Request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Not Found |
| 429 | Too Many Requests |
| 500 | Internal Server Error |

## Pagination

Endpoints that return lists typically support pagination:

**Query Parameters:**
- `page`: Page number (default: 1)
- `limit`: Items per page (default: varies by endpoint)

**Response includes pagination info:**
```json
{
    "pagination": {
        "currentPage": 1,
        "totalPages": 10,
        "totalItems": 100,
        "hasNextPage": true,
        "hasPrevPage": false,
        "limit": 10
    }
}
```

## Common Parameters

### Query Parameters
- `page`: Page number for pagination
- `limit`: Number of items per page
- `search`: Search query string
- `sortBy`: Field to sort by
- `order`: Sort order (`asc` or `desc`)
- `filter`: Filter criteria (varies by endpoint)

### Path Parameters
- `:id`: Resource ID
- `:userId`: User ID
- `:questionId`: Question ID
- `:answerId`: Answer ID

## Rate Limiting

The API implements rate limiting to prevent abuse. Default limits are:
- 100 requests per 15 minutes for authenticated users
- 50 requests per 15 minutes for unauthenticated users
- Higher limits for admin users

## Security

- All sensitive endpoints require JWT authentication
- Admin endpoints require additional admin role verification
- Input validation and sanitization on all endpoints
- CORS enabled for frontend integration
- Rate limiting to prevent abuse

## Testing

Use the provided Postman collections for comprehensive API testing:
- Import all collection files from `/backend/POSTMAN/`
- Set up the environment with base URL and authentication tokens
- Run the login endpoint first to populate JWT tokens automatically

For detailed endpoint documentation, refer to the individual API documentation files in `/docs/api/`.