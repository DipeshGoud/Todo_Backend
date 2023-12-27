# Todo Backend Documentation

## Introduction

This document provides an overview and documentation for the Todo backend server. The server is designed to manage user-specific todos with authentication.

## Table of Contents

1. [Project Setup](#1-project-setup)
2. [Database Setup](#2-database-setup)
3. [User Model](#3-user-model)
4. [Authentication](#4-authentication)
5. [Todo Model](#5-todo-model)
6. [User-Specific Todos](#6-user-specific-todos)
7. [Todo Routes](#7-todo-routes)
8. [Middleware for Authentication](#8-middleware-for-authentication)
9. [Testing](#9-testing)

## 1. Project Setup

- **Dependencies:**
  - Express
  - Mongoose
  - Cors
  - Jsonwebtoken
  - Bcrypt

- **Installation:**
  ```bash
  npm install express mongoose cors jsonwebtoken bcrypt
File Structure:
go
Copy code
todo-backend/
├── node_modules/
├── models/
│   ├── Todo.js
│   └── User.js
├── routes/
│   └── todo.js
├── middleware/
│   └── auth.js
├── index.js
└── package.json
2. Database Setup
Connection:
MongoDB
Connection URI: mongodb://localhost:27017/todo
3. User Model
Schema:

Username (String, required, unique)
Password (String, required)
Password Hashing:

Bcrypt used for password hashing.
4. Authentication
Middleware:
JWT (Json Web Token) for authentication.
Token generated during user login.
5. Todo Model
Schema:
Title (String, required)
Description (String, required)
Completed (Boolean, default: false)
CreatedAt (Date, default: current date)
User (Reference to User model)
6. User-Specific Todos
Todos are associated with the authenticated user.
User ID extracted from JWT during authentication.
7. Todo Routes
GET /todos:

Get user-specific todos.
POST /todos:

Create a new todo for the authenticated user.
PUT /todos/:id:

Update a todo for the authenticated user.
DELETE /todos/:id:

Delete a todo for the authenticated user.
8. Middleware for Authentication
Middleware:
authenticateToken middleware for JWT verification.
9. Testing
Test routes using tools like Postman.
Ensure authentication for relevant routes.





