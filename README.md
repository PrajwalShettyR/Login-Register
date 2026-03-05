Login / Register Authentication System

## Description

A full-stack authentication application built with **React** (Frontend) and **Flask** (Backend). This project provides a simple yet functional user registration and login system with secure credential handling. Users can create new accounts and authenticate using their credentials. The application features a clean, responsive UI and a RESTful API backend for handling all authentication operations.

**Key Features:**
- User registration with form validation
- Secure login authentication
- Session management
- Responsive UI design
- RESTful API architecture

---

 ## Technology Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React.js, HTML5, CSS3 |
| Backend | Flask, Python |
| Database | SQLite/PostgreSQL (configurable) |
| Authentication | JWT (JSON Web Tokens) |
| HTTP Client | Axios / Fetch API |

---

## File Structure

```
Login-Register/
│
├── Backend/
│   ├── app.py                 # Flask application entry point
│   ├── requirements.txt        # Python dependencies
│   ├── config.py              # Configuration settings
│   ├── models.py              # Database models
│   ├── routes.py              # API endpoints
│   └── utils.py               # Helper functions
│
├── frontend/
│   ├── public/
│   │   ├── index.html         # HTML entry point
│   │   └── favicon.ico        # Favicon
│   ├── src/
│   │   ├── components/
│   │   │   ├── LoginForm.js   # Login component
│   │   │   └── RegisterForm.js# Register component
│   │   ├── pages/
│   │   │   ├── Login.js       # Login page
│   │   │   └── Register.js    # Register page
│   │   ├── App.js             # Main App component
│   │   ├── App.css            # Main styles
│   │   └── index.js           # React entry point
│   ├── package.json           # Node dependencies
│   └── .gitignore             # Git ignore file
│
├── README.md                   # Project documentation
└── .gitignore                 # Root .gitignore
```


---

## Installation Instructions

### Prerequisites
- **Node.js** (v14 or higher)
- **Python** (v3.7 or higher)
- **pip** (Python package manager)
- **npm** or **yarn** (Node package manager)

### Backend Setup

1. **Navigate to the Backend directory:**
   ```bash
   cd Backend
   ```

2. **Create a virtual environment:**
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment:**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

5. **Run the Flask server:**
   ```bash
   python app.py
   ```
   The server will run on `http://localhost:5000`

### Frontend Setup

1. **Navigate to the frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm start
   ```
   The app will open at `http://localhost:3000`

---

## Usage Examples

### Registration Flow

1. Open the application at `http://localhost:3000`
2. Click on **"Sign Up"** or navigate to the registration page
3. Fill in the form with:
   - Email address
   - Password (minimum 8 characters recommended)
   - Confirm password
4. Click **"Register"**
5. On success, you'll be redirected to the login page

### Login Flow

1. Navigate to the login page
2. Enter your registered email and password
3. Click **"Login"**
4. On successful authentication, you'll be redirected to the dashboard/home page
5. Your session will be maintained for future requests

### Example Credentials (for testing)
```
Email: user@example.com
Password: password123
```

---

## API Documentation

### Base URL
```
http://localhost:5000/api
```

### Authentication Endpoints

#### 1. **Register User**
- **Method:** `POST`
- **Endpoint:** `/register`
- **Content-Type:** `application/json`

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "password123",
  "confirm_password": "password123"
}
```

**Response (Success - 201):**
```json
{
  "message": "User registered successfully",
  "user_id": 1,
  "email": "user@example.com"
}
```

**Response (Error - 400):**
```json
{
  "error": "Email already exists",
  "message": "User with this email already registered"
}
```

---

#### 2. **Login User**
- **Method:** `POST`
- **Endpoint:** `/login`
- **Content-Type:** `application/json`

**Request Body:**
```json
{
  "email": "user@example.com",
  "password": "password123"
}
```

**Response (Success - 200):**
```json
{
  "message": "Login successful",
  "user_id": 1,
  "email": "user@example.com",
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
}
```

**Response (Error - 401):**
```json
{
  "error": "Invalid credentials",
  "message": "Email or password is incorrect"
}
```

---

#### 3. **Logout User**
- **Method:** `POST`
- **Endpoint:** `/logout`
- **Headers:** `Authorization: Bearer <token>`

**Response (Success - 200):**
```json
{
  "message": "Logged out successfully"
}
```

---

#### 4. **Get Current User (Protected Route)**
- **Method:** `GET`
- **Endpoint:** `/user`
- **Headers:** `Authorization: Bearer <token>`

**Response (Success - 200):**
```json
{
  "user_id": 1,
  "email": "user@example.com",
  "created_at": "2026-03-05T10:30:00"
}
```

**Response (Error - 401):**
```json
{
  "error": "Unauthorized",
  "message": "Invalid or expired token"
}
```

---

### Error Codes

| Code | Meaning | Description |
|------|---------|-------------|
| 200 | OK | Request successful |
| 201 | Created | Resource created successfully |
| 400 | Bad Request | Invalid input or missing fields |
| 401 | Unauthorized | Invalid credentials or missing token |
| 409 | Conflict | Email already exists |
| 500 | Server Error | Internal server error |

---



## Running the Full Application

### Terminal 1 - Backend
```bash
cd Backend
source venv/bin/activate  # or venv\Scripts\activate on Windows
python app.py
```

### Terminal 2 - Frontend
```bash
cd frontend
npm start
```

Both servers should run simultaneously:
- Frontend: `http://localhost:3000`
- Backend: `http://localhost:5000`

---

## Future Enhancements

- [ ] Email verification
- [ ] Password reset functionality
- [ ] OAuth integration (Google, GitHub)
- [ ] Two-factor authentication
- [ ] User profile management
- [ ] Session timeout handling

---


## Author

Created by **PrajwalShettyR**

---

## Support

For issues, questions, or suggestions, please open an issue in the repository.
