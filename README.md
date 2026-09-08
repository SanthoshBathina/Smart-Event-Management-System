# 💰 BudgetX – Real-Time Currency Converter & Budgeting Tool

> A full-stack web application for **currency conversion, expense tracking, and smart budget management**.

BudgetX helps users manage their personal expenses while providing real-time currency conversion. Users can create an account, track their expenses, set category-wise budgets, monitor spending, and receive budget suggestions based on their spending patterns.

---

## 🚀 Features

### 🔐 User Authentication

* User registration and login
* Secure password hashing using **bcrypt**
* JWT-based authentication
* Forgot password and password reset functionality
* Protected API routes

### 💱 Currency Converter

* Convert between different currencies
* Real-time exchange-rate integration
* Currency swap functionality
* Smooth and responsive conversion interface
* Debounced API requests

### 💸 Expense Tracker

* Add new expenses
* View expense history
* Delete expenses
* Filter expenses by category/currency
* Track total spending

### 📊 Smart Budgeting

* Set category-wise spending limits
* Monitor budget utilization
* Warning indicators when spending increases
* Automated budget suggestions
* Visual spending representation using charts

### 📧 Email Services

* Automated email functionality using **NodeMailer**
* Welcome emails
* Password reset emails

### 🎨 Modern UI

* Responsive design
* Glassmorphism-based interface
* CSS animations
* Interactive dashboard
* Chart.js visualizations

---

## 🛠️ Technologies Used

### Frontend

* HTML5
* CSS3
* Vanilla JavaScript
* Chart.js

### Backend

* Node.js
* Express.js
* REST API
* JWT
* bcrypt
* NodeMailer

### Database

* MongoDB
* Mongoose

### Development Tools

* Git
* GitHub
* VS Code
* npm

---

## 🏗️ System Architecture

BudgetX follows a **three-tier client-server architecture**.

```text
                    ┌─────────────────────┐
                    │       USER          │
                    └──────────┬──────────┘
                               │
                               ▼
              ┌─────────────────────────────┐
              │       PRESENTATION          │
              │                             │
              │ HTML + CSS + JavaScript     │
              │                             │
              │ • Login / Signup            │
              │ • Dashboard                 │
              │ • Currency Converter        │
              │ • Expense Tracker           │
              └──────────────┬──────────────┘
                             │
                         REST API
                             │
                             ▼
              ┌─────────────────────────────┐
              │       APPLICATION           │
              │                             │
              │ Node.js + Express.js        │
              │                             │
              │ • Authentication            │
              │ • JWT Middleware            │
              │ • Business Logic            │
              │ • REST API Routes           │
              │ • Email Services            │
              └──────────────┬──────────────┘
                             │
                         Mongoose
                             │
                             ▼
              ┌─────────────────────────────┐
              │          DATA               │
              │                             │
              │        MongoDB              │
              │                             │
              │ • Users                     │
              │ • Expenses                  │
              │ • Budget Information        │
              └─────────────────────────────┘
```

---

## 📂 Project Structure

```text
budgetx-app/
│
├── backend/
│   ├── middleware/
│   │   └── auth.js
│   │
│   ├── models/
│   │   ├── User.js
│   │   └── Expense.js
│   │
│   ├── routes/
│   │   ├── auth.js
│   │   └── expenses.js
│   │
│   ├── utils/
│   │   └── emailer.js
│   │
│   ├── .env.example
│   ├── server.js
│   └── test-email.js
│
├── frontend/
│   ├── css/
│   ├── js/
│   │   ├── auth.js
│   │   ├── converter.js
│   │   ├── dashboard.js
│   │   └── tracker.js
│   │
│   ├── index.html
│   ├── signup.html
│   └── dashboard.html
│
├── .gitignore
├── package.json
├── package-lock.json
└── README.md
```

---

## 🔄 How BudgetX Works

### 1. User Authentication

```text
User
  ↓
Signup/Login
  ↓
Frontend
  ↓
POST /api/auth/signup
        OR
POST /api/auth/login
  ↓
Express Server
  ↓
MongoDB
  ↓
JWT Token
  ↓
Authenticated User
```

Passwords are hashed using **bcrypt**, while JWT tokens are used to authenticate protected requests.

---

### 2. Expense Tracking

```text
User enters expense
        ↓
Frontend JavaScript
        ↓
POST /api/expenses
        ↓
JWT Authentication
        ↓
Express Route
        ↓
Expense Model
        ↓
MongoDB
        ↓
Expense stored
        ↓
Dashboard updated
```

---

### 3. Currency Conversion

```text
User selects currencies
        ↓
Enters amount
        ↓
Currency Converter
        ↓
Exchange Rate API
        ↓
Conversion Calculation
        ↓
Converted Amount
        ↓
Displayed on Dashboard
```

---

## 🔌 API Endpoints

### Authentication

| Method | Endpoint                 | Description            |
| ------ | ------------------------ | ---------------------- |
| POST   | `/api/auth/signup`       | Register a new user    |
| POST   | `/api/auth/login`        | Login user             |
| POST   | `/api/auth/forgot`       | Request password reset |
| PUT    | `/api/auth/reset/:token` | Reset password         |

### Expenses & Budget

| Method | Endpoint               | Description            |
| ------ | ---------------------- | ---------------------- |
| GET    | `/api/expenses`        | Get user expenses      |
| POST   | `/api/expenses`        | Add a new expense      |
| DELETE | `/api/expenses/:id`    | Delete an expense      |
| GET    | `/api/expenses/budget` | Get budget information |
| PUT    | `/api/expenses/budget` | Update budget          |
| GET    | `/api/expenses/rates`  | Get exchange rates     |

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/SanthoshBathina/budgetx-app.git
```

### 2. Navigate into the project

```bash
cd budgetx-app
```

### 3. Install dependencies

```bash
npm install
```

### 4. Configure environment variables

Create a `.env` file inside the `backend` directory.

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
EMAIL_USER=your_email
EMAIL_PASS=your_email_password
```

> ⚠️ Never commit your `.env` file to GitHub.

### 5. Start the backend

```bash
node backend/server.js
```

For development:

```bash
nodemon backend/server.js
```

The backend runs on:

```text
http://localhost:5000
```

### 6. Run the frontend

Open:

```text
frontend/index.html
```

in your browser.

---

## 🔑 Environment Variables

| Variable     | Purpose                                |
| ------------ | -------------------------------------- |
| `MONGO_URI`  | MongoDB database connection            |
| `JWT_SECRET` | Secret key used for JWT authentication |
| `EMAIL_USER` | Email account used by NodeMailer       |
| `EMAIL_PASS` | Email authentication credential        |

---

## 📊 Dashboard

The dashboard provides users with:

* Total expenses
* Expense categories
* Budget utilization
* Currency conversion
* Spending charts
* Budget recommendations

### 📸 Screenshots

Add screenshots of your application here:

```text
screenshots/
├── login.png
├── signup.png
├── dashboard.png
├── converter.png
└── expense-tracker.png
```

Example:

```markdown
![Dashboard](screenshots/dashboard.png)
```

---

## 🔒 Security

BudgetX implements several security mechanisms:

* JWT authentication
* Password hashing with bcrypt
* Protected backend routes
* Environment variables for sensitive configuration
* Authentication middleware
* Server-side API handling

---

## 🧪 Testing

The application can be tested by checking:

* User registration
* User login
* Invalid login credentials
* Expense creation
* Expense deletion
* Budget updates
* Currency conversion
* Password reset
* Protected API requests

---

## 🔮 Future Improvements

Potential future enhancements include:

* 📱 Mobile-responsive improvements
* 📈 Advanced expense analytics
* 📊 Monthly and yearly financial reports
* 🔔 Budget notifications
* 🤖 AI-powered spending recommendations
* 🌐 Support for more currencies
* 📤 Export expenses to CSV/PDF
* 🔐 Two-factor authentication
* ☁️ Cloud deployment
* 📱 Progressive Web App support

---

## 🎯 Project Goals

The main goal of BudgetX is to combine **financial tracking and currency conversion into a single application**.

It demonstrates practical implementation of:

* Full-stack web development
* REST API development
* Authentication and authorization
* Database management
* API integration
* CRUD operations
* Data visualization
* Responsive UI development

---

## 👨‍💻 Author

**Santhosh Bathina**

B.Tech Student | Full-Stack Developer | DSA Enthusiast

GitHub: [SanthoshBathina](https://github.com/SanthoshBathina)

---

## ⭐ Support

If you find this project useful, consider giving it a ⭐ on GitHub!

---

## 📄 License

This project is developed for educational and portfolio purposes.
