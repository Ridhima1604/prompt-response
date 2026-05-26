# Prompt – User Management System

# Context and Role

As a Senior Full-Stack MERN Developer and Software Architect, you are responsible for designing and developing a production-ready User Management System using the MERN stack. The application must support secure authentication, role-based authorization (RBAC), user lifecycle management, audit tracking, and scalable deployment practices.

Your goal is to build a clean, maintainable, secure, and deployment-ready full-stack web application that demonstrates strong backend architecture, frontend integration, API security, and real-world engineering practices.

---

# Objective

Create a complete end-to-end MERN Stack application that:

- Create a comprehensive end to end MERN Stack app that
- Supports Role Based Access Control (RBAC)
- Helps users with different access levels / permissions
- Separate user and admin capabilities
- Provides scalable backend architecture and reusable frontend components
- Provides secure REST APIs
- Deploys frontend and backend publicly
- Follows clean coding standards and production-level practices

---

# Technology Stack

## Frontend

- React.js
- React Hooks
- Context API
- React Router
- Axios
- Tailwind CSS

## Backend

- Node.js
- Express.js

## Database

- MongoDB

## Authentication

- JWT Authentication
- Access Token
- Refresh Token (optional but preferred)
- bcrypt password hashing

---

# Authentication Requirements

Implement secure authentication with:

- User registration (optional)
- User login using:
  - Email or username
  - Password
- Secure password hashing using bcrypt
- Protected routes
- Session persistence
- Refresh token mechanism (preferred)

Ensure:

- Expired token handling
- Secure cookie handling if using cookies
- Environment-based secret management
- Proper authentication error handling

---

# Authorization (RBAC)

Implement backend route protection using role-based middleware.

## Examples

### Admin Can

- Create users
- Delete users
- Change roles
- View all users
- Update all users

### Manager Can

- View users
- Update non-admin users

### User Can

- Access only own profile
- Update own profile

Unauthorized access must return:

- 401 Unauthorized
- 403 Forbidden

---

# User Management Features

## Admin Features

- Paginated user listing
- Search users
- Filter by:
  - Role
  - Status
- Create users
- Edit users
- Soft delete/deactivate users
- View single user details
- Auto-generated password support (optional)

## User Features

- View profile
- Update profile
- Update password
- Restrict role editing
- Restrict access to other profiles

---

# Audit & Activity Tracking

Track the following fields:

- createdAt
- updatedAt
- createdBy
- updatedBy

Provide audit visibility in:

- User detail page
- Admin dashboard

Include:

- Last updated user
- Creation timestamps
- Update timestamps

---

# Backend Architecture Requirements

Design a scalable backend structure with:

- Controllers
- Routes
- Middleware
- Services
- Models
- Utilities
- Validators
- Config management

Implement:

- Centralized error handling
- Async error wrappers
- Request validation
- Secure environment configuration
- Structured API responses
- Logging system
- Input sanitization
- MongoDB query protection

## Recommended Folder Structure

```bash
backend/
│── src/
│   ├── controllers/
│   ├── routes/
│   ├── middleware/
│   ├── models/
│   ├── services/
│   ├── validators/
│   ├── utils/
│   ├── config/
│   └── app.js
```

---

# Frontend Requirements

Build a clean and responsive frontend with:

## Pages

- Login
- Dashboard
- User List
- User Details
- My Profile
- Unauthorized Page

## Features

- Role-based navigation
- Protected routes
- Persist authentication state
- Dynamic UI rendering based on roles
- Form validation
- Loading states
- Error handling
- Responsive design

## UI/UX

- Clean modern interface
- Reusable components
- Proper navigation flow
- Mobile responsiveness

---

# API Design & Security Requirements

Ensure:

- RESTful API architecture
- Proper HTTP methods
- Backend validation
- Secure JWT handling
- Hidden sensitive data
- Password hashing
- Secure headers
- Environment variable usage

Protect against:

- Injection attacks
- Unauthorized access
- Token misuse
- Sensitive data exposure

Implement:

- Rate limiting
- Helmet middleware
- CORS configuration
- Request logging

---

# Database Requirements

Design scalable MongoDB schemas for:

## User Schema

### Fields

- name
- email
- password
- role
- status
- createdBy
- updatedBy
- timestamps

Include:

- Validation
- Indexing
- Secure password exclusion
- Soft delete support

---

# Data Processing Requirements

Validate:

- Email format
- Required fields
- Password strength
- MongoDB ObjectIds

Secure data handling:

- Trim and normalize inputs
- Hash passwords using bcrypt
- Hide sensitive data from API responses

Ensure all APIs return structured JSON responses.

---

# Performance & Scalability

Ensure:

- Optimized MongoDB queries
- Pagination support
- Efficient API responses
- Reusable architecture
- Scalable RBAC system
- Low response latency
- Efficient frontend rendering
- Maintainable codebase

Support:

- Future role additions
- Feature extensibility
- Horizontal scaling

---

# Error Handling & Validation

Implement:

- Centralized error middleware
- Request validation
- Graceful API failures
- Invalid JWT handling
- Invalid input handling
- Meaningful error messages
- Authentication failure handling

Prevent:

- Data leakage
- Invalid database operations
- Unauthorized updates

---

# Expected Output

The final solution should demonstrate:

- Production-ready MERN architecture
- Secure authentication system
- Scalable RBAC implementation
- Clean frontend UI/UX
- Secure REST APIs
- Maintainable backend structure
- Proper deployment practices
- Real-world engineering standards
- Strong code quality and scalability principles
