
# Secure User Authentication System

## Description
This project is a simple but secure user authentication system developed using Node.js, Express for the backend, and React for the frontend, with MySQL as the database. It includes features for user registration, login, and secure handling of user data with hashing, JWT authentication, input validation, and CSRF protection.

## Features
- User registration and login functionality
- Password hashing with bcrypt
- JWT-based user authentication
- CSRF protection for state-changing requests
- HTTPS support (recommended for production)
- Input validation to prevent common vulnerabilities such as SQL injection and XSS

---

## Technologies Used
### Backend
- **Node.js**
- **Express.js**
- **MySQL**
- **bcryptjs** for password hashing
- **jsonwebtoken** for JWT generation
- **csurf** for CSRF protection
- **dotenv** for environment variable management
- **express-validator** for input validation

### Frontend
- **React**
- **axios** for HTTP requests

---

## Prerequisites
- Node.js installed on your machine
- MySQL installed and running
- Basic knowledge of JavaScript, React, and MySQL

---

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/auth-system.git
cd auth-system
```

### 2. Backend Setup

#### 2.1 Install Dependencies
```bash
cd backend
npm install
```

#### 2.2 Configure Environment Variables
Create a `.env` file in the `backend` directory with the following content:
```env
PORT=5000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=auth_db
JWT_SECRET=your_jwt_secret
```

#### 2.3 Database Setup
Run the following SQL commands to create the database and `users` table:
```sql
CREATE DATABASE IF NOT EXISTS auth_db;
USE auth_db;

CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  username VARCHAR(255) NOT NULL UNIQUE,
  password VARCHAR(255) NOT NULL
);
```

#### 2.4 Run the Backend
```bash
npm run start
```

### 3. Frontend Setup

#### 3.1 Install Dependencies
```bash
cd frontend
npm install
```

#### 3.2 Run the Frontend
```bash
npm start
```

---

## Project Structure

### Backend (`/backend`)
```
backend/
  ├── node_modules/
  ├── .env
  ├── server.js
  ├── package.json
  └── README.md
```

### Frontend (`/frontend`)
```
frontend/
  ├── node_modules/
  ├── public/
  ├── src/
      ├── App.js
      └── index.js
  ├── package.json
  └── README.md
```

---

## API Endpoints

### 1. Register User
**Endpoint**: `/register`  
**Method**: `POST`  
**Description**: Register a new user with a username and password.  
**Request Body**:
```json
{
  "username": "exampleUser",
  "password": "password123"
}
```
**Response**:
- **201 Created**: User registered successfully.
- **400 Bad Request**: Validation error.
- **500 Internal Server Error**: Registration failed.

### 2. Login User
**Endpoint**: `/login`  
**Method**: `POST`  
**Description**: Log in an existing user and receive a JWT.  
**Request Body**:
```json
{
  "username": "exampleUser",
  "password": "password123"
}
```
**Response**:
- **200 OK**: Login successful, returns a JWT token.
- **401 Unauthorized**: Invalid username or password.
- **500 Internal Server Error**: Authentication failed.

---

## Security Features
- **Password Hashing**: Passwords are hashed and salted using `bcryptjs` before storing in the database.
- **JWT Authentication**: JSON Web Tokens are used for stateless authentication.
- **CSRF Protection**: State-changing requests are protected using `csurf` tokens.
- **Input Validation**: Inputs are validated using `express-validator` to prevent SQL injection and XSS attacks.
- **HTTPS**: Recommended for production to secure all communications between the client and server.

---

## Usage Instructions
1. Register a new user by providing a username and password.
2. Log in with the registered credentials to receive a JWT token.
3. Use the JWT token for authenticated requests in the application.

---

## Improvements
- Implement role-based access control for different user roles.
- Add user session management with token blacklisting.
- Integrate a password reset feature.
- Implement frontend form validation and user-friendly error messages.

---

## Contributing
If you wish to contribute to this project, feel free to fork the repository, make your changes, and create a pull request.

---

## License
This project is open-source and available under the [MIT License](LICENSE).

---

## Contact
For questions or suggestions, you can reach out to me at [sumitmahour24@example.com].

---

Happy coding!

---


