# 🎉 Smart Event Management System

A full-stack web application for managing events with a modern and responsive interface.

## 🌐 Live Demo

🚀 **[View Live Demo](https://smart-event-management-system-rho.vercel.app/)**

📂 **[View Source Code](https://github.com/SanthoshBathina/Smart-Event-Management-System)**

---

## 📌 Overview

The **Smart Event Management System** is a full-stack web application designed to simplify event management through a user-friendly interface. It provides authentication, event-related functionality, and a responsive frontend connected to a backend API.

## ✨ Features

* 🔐 User Authentication
* 👤 User Registration and Login
* 🎫 Event Management
* 📱 Responsive User Interface
* 🔒 JWT-based Authentication
* 🍪 Cookie-based Authentication
* 🔗 REST API Integration
* 🗄️ MongoDB Database
* ⚡ React-based Frontend
* 🚀 Deployed on Vercel

## 🛠️ Technologies Used

### Frontend

* React.js
* JavaScript
* HTML5
* CSS3

### Backend

* Node.js
* Express.js
* REST APIs
* JWT Authentication

### Database

* MongoDB

### Tools & Platforms

* Git
* GitHub
* VS Code
* npm
* Vercel

## 🏗️ System Architecture

```text
              ┌─────────────────────┐
              │       User          │
              └──────────┬──────────┘
                         │
                         ▼
              ┌─────────────────────┐
              │   React Frontend    │
              │      (Client)       │
              └──────────┬──────────┘
                         │
                    HTTP Requests
                         │
                         ▼
              ┌─────────────────────┐
              │  Express.js Server  │
              │      (Backend)      │
              └──────────┬──────────┘
                         │
                  Mongoose / API
                         │
                         ▼
              ┌─────────────────────┐
              │      MongoDB        │
              │      Database       │
              └─────────────────────┘
```

### Application Flow

```text
User
  ↓
React Frontend
  ↓
REST API
  ↓
Express.js Backend
  ↓
Authentication Middleware
  ↓
MongoDB
```

## 📂 Project Structure

```text
Smart-Event-Management-System/
│
├── smart-event-management/
│   │
│   ├── client/
│   │   └── React application
│   │
│   └── server/
│       ├── middleware/
│       ├── routes/
│       ├── models/
│       └── server files
│
└── README.md
```

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/SanthoshBathina/Smart-Event-Management-System.git
```

### 2. Navigate to the Project

```bash
cd Smart-Event-Management-System/smart-event-management
```

### 3. Install Frontend Dependencies

```bash
cd client
npm install
```

### 4. Install Backend Dependencies

```bash
cd ../server
npm install
```

## 🔐 Environment Variables

Create a `.env` file inside the `server` directory and add the required environment variables.

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
```

## ▶️ Running the Application

### Start Backend

```bash
cd server
npm start
```

### Start Frontend

Open another terminal:

```bash
cd client
npm start
```

The application will then be available locally through the frontend development server.

## 🔒 Authentication

The application uses JWT-based authentication.

```text
User Login
    ↓
Credentials Verification
    ↓
JWT Token Generated
    ↓
Token Stored in Cookie
    ↓
Authentication Middleware
    ↓
Protected Routes
```

## 🚀 Deployment

The application is deployed using **Vercel**.

🌐 **Live Application:**
https://smart-event-management-system-rho.vercel.app/

## 🔮 Future Improvements

* Advanced event search and filtering
* Event reminders and notifications
* Improved admin functionality
* Event analytics and reporting
* Enhanced UI/UX
* Additional security improvements

## 👨‍💻 Author

**Santhosh Bathina**

* GitHub: https://github.com/SanthoshBathina

## 📄 License

This project is intended for educational and portfolio purposes.
