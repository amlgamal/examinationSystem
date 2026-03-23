# 📝 Examination System — Full-Stack Quiz Platform

A full-stack web-based examination system built as a college team project. The platform supports two roles: **admins** who create and manage quizzes, and **students** who take timed exams and track their scores.

---

## 🚀 Features

### 👨‍💼 Admin
- Create quizzes with multiple-choice questions
- View and manage all available quizzes
- View all registered users

### 🎓 Student
- Register and log in securely
- Browse available exams
- Take timed exams with randomized question order
- Flag questions to review during the exam
- Track progress with a live progress bar
- View previous exam scores and history

---

## 🛠️ Tech Stack

### Frontend
- HTML, CSS, JavaScript (Vanilla — no frameworks)
- Fetch API for communicating with the backend
- localStorage for token and session management

### Backend
- **Node.js** + **Express.js** — REST API
- **MongoDB** + **Mongoose** — database and schema modeling
- **JWT (jsonwebtoken)** — authentication with access & refresh tokens
- **bcrypt** — password hashing
- **Joi** — request validation
- **dotenv** — environment variable management
- **CORS** — cross-origin request handling

---

## 🔐 Security Features

- JWT-based authentication (access token: 1 day, refresh token: 7 days)
- Role-based access control (admin / user)
- Passwords hashed with bcrypt (12 salt rounds) before storing
- Protected API routes using authentication & authorization middleware
- Input validation on registration using Joi schemas

---

## 📁 Project Structure

```
├── index.js                  # Entry point
├── src/
│   ├── app.controller.js     # Bootstrap (middleware + routes setup)
│   ├── DB/
│   │   ├── connectDB.js      # MongoDB connection
│   │   ├── dbServices.js     # Reusable DB operations
│   │   └── models/
│   │       ├── user.model.js
│   │       └── Quiz.model.js
│   ├── Modules/
│   │   ├── auth/
│   │   │   ├── auth.controller.js   # Register & Login
│   │   │   ├── auth.validation.js   # Joi schemas
│   │   │   └── auth.route.js
│   │   └── Admin/
│   │       ├── question.controller.js  # Quiz CRUD + grades
│   │       └── question.route.js
│   ├── Middlewares/
│   │   ├── auth.middlewares.js      # Authentication & Authorization
│   │   └── validation.middlewares.js
│   └── Utils/
│       ├── token.utils.js           # signToken & verifyToken
│       ├── successResponse.utils.js
│       └── errorHandler.utils.js
└── client/                   # Frontend
    ├── login/
    ├── register/
    ├── userHome/
    ├── getQuiz/
    ├── createQuiz/
    ├── getAllQuizs/
    ├── quizDetails/
    └── homeAdmin/
```

---

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/examination-system.git

# Navigate to the project
cd examination-system

# Install dependencies
npm install

# Create a .env file
cp .env.example .env
```

### Run the server
```bash
npm start
# or with nodemon
npm run dev
```
Then open the frontend HTML files directly in your browser or use a live server.

---

## 📡 API Endpoints

### Auth
| Method | Endpoint | Description | Protected |
|--------|----------|-------------|-----------|
| POST | `/api/auth/register` | Register new user | No |
| POST | `/api/auth/login` | Login | No |

### Quiz
| Method | Endpoint | Description | Protected |
|--------|----------|-------------|-----------|
| POST | `/api/quiz/createQuiz` | Create a new quiz | Admin |
| GET | `/api/quiz/getAllQuiz` | Get all quizzes | Yes |
| GET | `/api/quiz/getQuiz/:quizName` | Get quiz by name | Yes |
| POST | `/api/quiz/save-result` | Save exam result | Yes |
| GET | `/api/quiz/getMyGrades` | Get my grades | Yes |
| GET | `/api/quiz/getAllUsers` | Get all users | Admin |

---

## 👥 Team

| Name | Role |
|------|------|
| Aml Gamal | Full-Stack Developer |
| Marwan Abd Elhakem | Full-Stack Developer |


---
