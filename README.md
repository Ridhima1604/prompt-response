
# User Management System

A complete end-to-end **MERN Stack (MongoDB + Express + React + Node.js)** project that manages users with secure authentication and role-based access control using **JWT Authentication**.

This system is built for organizations and teams to manage user accounts, roles, permissions, activity tracking, and secure access through a responsive dashboard.

---

## Deployed Link

https://usermgmtsystem-4.onrender.com/login
---

## Features

### Authentication & Security
- JWT-based authentication
- Secure login system
- Password hashing using bcrypt
- Protected API routes
- Role-based authorization
- Token persistence
- Logout functionality

### Role-Based Access Control (RBAC)
- Admin role
- User role
- Backend route protection
- Frontend role-based navigation
- Restrict access by permissions
- Extendable role system

### User Management
- View users
- Search users
- Filter users by role/status
- Create new user
- Update user
- Delete / deactivate user
- View individual user profile
- Update own profile

### Frontend Dashboard
- Login page
- Dashboard
- User list
- User details
- Profile page
- Role-based sidebar
- Responsive UI

### Audit & Activity Tracking
- createdAt
- updatedAt
- createdBy
- updatedBy
- User activity details

### Deployment Ready
- Localhost
- Render
- Vercel
- Railway
- Docker

---

# Dataset / Database

Database used: **MongoDB**

---

# User Roles

### Admin
- Full access to user management
- Create users
- Edit users
- Delete users
- Assign/change roles
- View all users

### Manager *(Optional)*
- View users
- Update non-admin users
- Limited admin controls

### User
- View own profile
- Update own profile
- Cannot access other users
- Cannot change role

---

# Authentication

### Login Fields
- Email / Username
- Password

### Security
- Password hashing using bcrypt
- JWT access token
- Protected routes
- Secure environment variables

### Optional
- Refresh token support

---

# Authorization (RBAC)

### Admin Permissions
- Create users
- Update users
- Delete users
- Change user roles

### Manager Permissions
- View users
- Update non-admin users

### User Permissions
- View own profile
- Update own profile

### Unauthorized Access
Returns:

- **401 → Unauthorized**
- **403 → Forbidden**

---

# User Management Features

### Admin Capabilities
- Paginated user list
- Search users
- Filter by role
- Filter by status
- Create new user
- Edit user
- Deactivate user
- View user details

### User Capabilities
- View own profile
- Update name
- Update password

---

# Audit Tracking

Track:

- createdAt
- updatedAt
- createdBy
- updatedBy

### Example
Show:

- Who created the user
- Last updated by
- Date and time

---

# Backend API

Built using **Node.js + Express.js**

## Endpoints

### POST `/register`
Register user

### POST `/login`
User login

### GET `/users`
Get all users

### GET `/users/:id`
Get user details

### POST `/users`
Create user

### PUT `/users/:id`
Update user

### DELETE `/users/:id`
Delete / deactivate user

### GET `/profile`
Current user profile

---

## Example Login Response

```json
{
  "token": "jwt_token_here",
  "user": {
    "name": "Admin User",
    "email": "admin@example.com",
    "role": "Admin"
  }
}
```

---

# Frontend Pages

- Login
- Dashboard
- User List
- User Details
- Profile Page

---

# Dashboard Features

- Role-based navigation
- Search bar
- Filters
- User cards / table
- Profile updates
- Loading indicators
- Error handling
- Protected routes

---

# Database Schema

## Users

| Field | Type |
|------|------|
| _id | ObjectId |
| name | String |
| email | String |
| password | String |
| role | String |
| status | String |
| createdAt | DateTime |
| updatedAt | DateTime |
| createdBy | ObjectId |
| updatedBy | ObjectId |

---

# Project Structure

```bash
user_management_system/
│
├── backend/
│   ├── server.js
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── utils/
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── context/
│   │   └── services/
│
├── .env
├── package.json
└── README.md
```

---

# Dependencies

```txt
react
node.js
express
mongodb
mongoose
jsonwebtoken
bcrypt
cors
dotenv
axios
react-router-dom
```

---

# Run Locally

## Clone repository

```bash
git clone <repository-url>
cd user_management_system
```

## Install backend dependencies

```bash
cd backend
npm install
```

## Start backend

```bash
npm run dev
```

## Install frontend dependencies

```bash
cd frontend
npm install
```

## Start frontend

```bash
npm start
```

---

# Docker Deployment

Build image

```bash
docker build -t user-management .
```

Run

```bash
docker run -p 5000:5000 user-management
```

---

# Deployment Platforms

You can deploy on:

- Render
- Railway
- Vercel
- Netlify
- Docker
- Localhost

---

# Final Output

Example:

```txt
Admin Dashboard
Users: 24
Role: Admin

Search users
Create user
Edit user
Delete user
```

---

# Project Goal

The goal of this project is to provide a secure and scalable user management system with authentication and role-based access control.

It combines:

- MERN Stack Development
- Authentication
- Authorization
- API Security
- User Management
- Dashboard UI
- Deployment

into one complete production-ready web application.

---

# Author

**Ridhima Pandey**
````

