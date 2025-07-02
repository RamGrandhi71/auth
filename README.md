# Auth Backend API

A Node.js/Express backend for authentication, user management, and email verification, featuring JWT-based authentication, password reset, and email notifications via Mailtrap.

## Features
- User registration with email verification
- JWT authentication (login/logout)
- Password reset via email
- Welcome and notification emails (Mailtrap)
- MongoDB (Mongoose) for data storage
- Secure cookies for session management

## Tech Stack
- Node.js
- Express.js
- MongoDB & Mongoose
- JWT (jsonwebtoken)
- bcryptjs (password hashing)
- Mailtrap (email service)
- dotenv (environment variables)
- cookie-parser, cors

## Getting Started

### Prerequisites
- Node.js (v18+ recommended)
- MongoDB instance (local or cloud)
- Mailtrap account (for email testing)

### Installation
1. Clone the repository:
   ```bash
   git clone <repo-url>
   cd auth
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Create a `.env` file in the root directory and add the following:
   ```env
   PORT=5000
   MONGO_URI=<your-mongodb-uri>
   JWT_SECRET=<your-jwt-secret>
   MAILTRAP_ENDPOINT=<your-mailtrap-endpoint>
   MAILTRAP_TOKEN=<your-mailtrap-token>
   CLIENT_URL=http://localhost:5173
   NODE_ENV=development
   ```

### Running the Server
- Development mode (with nodemon):
  ```bash
  npm run dev
  ```
- Production mode:
  ```bash
  npm start
  ```

## API Endpoints

### Auth
- `POST /api/auth/signup` — Register a new user
- `POST /api/auth/login` — Login
- `POST /api/auth/logout` — Logout
- `POST /api/auth/verify-email` — Verify email with code
- `POST /api/auth/forgot-password` — Request password reset
- `POST /api/auth/reset-password/:token` — Reset password
- `GET /api/auth/check-auth` — Check authentication (requires token)

## Folder Structure
```
backend/
  controllers/         # Route handlers (auth logic)
  db/                  # Database connection
  mailtrap/            # Email templates & Mailtrap config
  middleware/          # JWT verification middleware
  models/              # Mongoose models
  routes/              # Express routes
  utils/               # Utility functions (JWT, cookies)
  index.js             # Main server entry point
```

## License
MIT
