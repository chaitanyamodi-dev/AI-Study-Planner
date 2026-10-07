
# 📚 AI Study Planner

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python" />
  <img src="https://img.shields.io/badge/FastAPI-REST%20API-009688?style=for-the-badge&logo=fastapi" />
  <img src="https://img.shields.io/badge/SQLAlchemy-ORM-red?style=for-the-badge" />
  <img src="https://img.shields.io/badge/SQLite-Database-003B57?style=for-the-badge&logo=sqlite" />
  <img src="https://img.shields.io/badge/Pydantic-Validation-E92063?style=for-the-badge" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/JWT-Authentication-black?style=for-the-badge&logo=jsonwebtokens" />
  <img src="https://img.shields.io/badge/HTML5-Frontend-E34F26?style=for-the-badge&logo=html5" />
  <img src="https://img.shields.io/badge/CSS3-Styling-1572B6?style=for-the-badge&logo=css3" />
  <img src="https://img.shields.io/badge/JavaScript-Frontend-F7DF1E?style=for-the-badge&logo=javascript" />
  <img src="https://img.shields.io/badge/Pytest-Testing-0A9EDC?style=for-the-badge&logo=pytest" />
</p>

---

## 🚀 About The Project

**AI Study Planner** is a personalized study planning and progress tracking application built with **FastAPI**.

The application helps students organize their learning goals, manage subjects, generate personalized study plans, track study progress, and receive AI-powered study recommendations.

The project combines a **RESTful backend API** with a modern **HTML/CSS/JavaScript frontend**.

### 🎯 Core Idea

Instead of manually deciding:

> "What should I study today?"

the application organizes the learning journey into:

```text
Goal
  ↓
Subjects
  ↓
Study Plan
  ↓
Study Tasks
  ↓
Progress
  ↓
AI Recommendation
  ↓
Plan Adjustment
````

---

# ✨ Features

## 🔐 Authentication

* User registration
* User login
* JWT authentication
* Password hashing
* Protected API endpoints
* Current user information

---

## 🎯 Goal Management

Users can create and manage learning goals.

Features include:

* Create goals
* View goals
* View individual goals
* Update goals
* Delete goals
* Target dates
* Daily study time
* Difficulty levels
* Goal status

---

## 📖 Subject Management

Each goal can contain multiple subjects.

Features:

* Add subjects
* View subjects
* Update subjects
* Delete subjects
* Subject priorities
* Estimated study hours

---

## 📝 Study Task Management

Study plans are converted into individual study tasks.

Features:

* Create study tasks
* View tasks
* View individual tasks
* Update tasks
* Delete tasks
* Scheduled dates
* Study duration
* Task priority
* Task completion status

---

## 📊 Progress Tracking

The application tracks learning progress.

Users can record:

* Minutes studied
* Completion percentage
* Progress notes
* Task progress
* Goal progress

---

## 🤖 AI Study Planner

The planner analyzes the user's goal, subjects, available study time, and target date to generate a structured study plan.

The current planner uses rule-based intelligence and is designed so that it can later be extended with a real LLM/AI service.

---

## 🧠 AI Recommendations

The system analyzes study progress and provides recommendations based on completion levels.

Example:

```text
80%+ Completion
       ↓
Excellent Progress

50%+ Completion
       ↓
Good Progress

1% - 49%
       ↓
Below Expected Pace

0%
       ↓
Start With Highest Priority Subject
```

---

## 🔄 Automatic Plan Adjustments

The system can adjust study duration based on progress.

Example:

```text
Low Progress
     ↓
Increase Pending Task Duration

High Progress
     ↓
Reduce Task Duration
```

This allows the study plan to adapt to the student's progress.

---

# 💡 Why I Built This

Students often create study plans manually but struggle to maintain them consistently.

I built this project to solve that problem by combining:

* Goal management
* Subject planning
* Task scheduling
* Progress tracking
* AI recommendations
* Automatic plan adjustments

The main goal was also to build a **real-world backend project** that demonstrates practical experience with:

```text
Python
FastAPI
REST APIs
SQLAlchemy
Database Design
Authentication
API Validation
Business Logic
Testing
Frontend Integration
```

---

# 🏗️ System Architecture

```text
┌──────────────────────────────────────────┐
│                FRONTEND                  │
│                                          │
│          HTML + CSS + JavaScript         │
└────────────────────┬─────────────────────┘
                     │
                     │ HTTP / REST
                     ▼
┌──────────────────────────────────────────┐
│                 FASTAPI                  │
│                                          │
│              API Routers                 │
│                                          │
│  Auth │ Goals │ Subjects │ Tasks         │
│       │ Progress │ Plans │ AI            │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│                SERVICES                  │
│                                          │
│  Planner Service                         │
│  Progress Service                        │
│  AI Recommendation Service               │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│              SQLALCHEMY ORM              │
└────────────────────┬─────────────────────┘
                     │
                     ▼
┌──────────────────────────────────────────┐
│                  SQLITE                  │
│                                          │
│ Users                                    │
│ Goals                                    │
│ Subjects                                 │
│ Study Tasks                              │
│ Progress                                 │
└──────────────────────────────────────────┘
```

---

# 🔄 Study Planner Workflow

```text
                 👤 USER
                    │
                    ▼
             🔐 Authentication
                    │
                    ▼
              🎯 Create Goal
                    │
                    ▼
             📖 Add Subjects
                    │
                    ▼
          🤖 Generate Study Plan
                    │
                    ▼
             📝 Study Tasks
                    │
                    ▼
              📚 Study
                    │
                    ▼
             📊 Record Progress
                    │
                    ▼
          🧠 Analyze Progress
                    │
                    ▼
          💡 AI Recommendation
                    │
                    ▼
          🔄 Adjust Study Plan
                    │
                    └───────────────┐
                                    │
                                    ▼
                              Continue Learning
```

---

# 🗄️ Database Design

The project uses **SQLite** with **SQLAlchemy ORM**.

## Entity Relationship Diagram

```text
┌─────────────────┐
│      USER       │
├─────────────────┤
│ id              │
│ name            │
│ email           │
│ password_hash   │
│ created_at      │
└────────┬────────┘
         │
         │ 1:N
         ▼
┌─────────────────┐
│      GOAL       │
├─────────────────┤
│ id              │
│ user_id         │
│ title           │
│ description     │
│ target_date     │
│ daily_minutes   │
│ difficulty      │
│ status          │
│ created_at      │
└───────┬─────────┘
        │
        ├──────────────────────┐
        │                      │
        │ 1:N                  │ 1:N
        ▼                      ▼
┌─────────────────┐    ┌─────────────────┐
│     SUBJECT     │    │   STUDY TASK    │
├─────────────────┤    ├─────────────────┤
│ id              │    │ id              │
│ goal_id         │    │ goal_id         │
│ name            │    │ subject_id      │
│ priority        │    │ title           │
│ estimated_hours │    │ description     │
└────────┬────────┘    │ scheduled_date  │
         │             │ duration_minutes│
         │ 1:N         │ status          │
         └────────────►│ priority        │
                       │ completed_at    │
                       └────────┬────────┘
                                │
                                │ 1:N
                                ▼
                       ┌─────────────────┐
                       │    PROGRESS     │
                       ├─────────────────┤
                       │ id              │
                       │ goal_id         │
                       │ task_id         │
                       │ minutes_spent   │
                       │ completion_%    │
                       │ notes           │
                       │ created_at      │
                       └─────────────────┘
```

---

# 🛠️ Tech Stack

| Technology         | Purpose                     |
| ------------------ | --------------------------- |
| 🐍 Python          | Backend development         |
| ⚡ FastAPI          | REST API framework          |
| 🗄️ SQLAlchemy     | ORM                         |
| 💾 SQLite          | Database                    |
| 📦 Pydantic        | Request/response validation |
| 🔐 JWT             | Authentication              |
| 🔑 Passlib         | Password hashing            |
| 🌐 HTML5           | Frontend                    |
| 🎨 CSS3            | Styling                     |
| ⚙️ JavaScript      | API integration             |
| 🧪 Pytest          | Testing                     |
| 📘 Swagger/OpenAPI | API documentation           |

---

# 📂 Project Structure

```text
AI-Study-Planner/
│
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── database.py
│   ├── models.py
│   ├── schemas.py
│   │
│   ├── routers/
│   │   ├── __init__.py
│   │   ├── auth.py
│   │   ├── goals.py
│   │   ├── subjects.py
│   │   ├── plans.py
│   │   ├── tasks.py
│   │   ├── progress.py
│   │   ├── ai_planner.py
│   │   └── adjustments.py
│   │
│   ├── services/
│   │   ├── __init__.py
│   │   ├── planner.py
│   │   ├── progress.py
│   │   └── ai_planner.py
│   │
│   └── utils/
│       ├── __init__.py
│       └── security.py
│
├── frontend/
│   ├── index.html
│   │
│   ├── css/
│   │   └── style.css
│   │
│   └── js/
│       └── main.js
│
├── tests/
│   ├── __init__.py
│   └── test_api.py
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md
```

---

# 📡 REST API

## 🔐 Authentication

| Method | Endpoint         | Description      |
| ------ | ---------------- | ---------------- |
| `POST` | `/auth/register` | Register user    |
| `POST` | `/auth/login`    | Login            |
| `GET`  | `/auth/me`       | Get current user |

---

## 🎯 Goals

| Method   | Endpoint           | Description |
| -------- | ------------------ | ----------- |
| `GET`    | `/goals`           | Get goals   |
| `POST`   | `/goals`           | Create goal |
| `GET`    | `/goals/{goal_id}` | Get goal    |
| `PUT`    | `/goals/{goal_id}` | Update goal |
| `DELETE` | `/goals/{goal_id}` | Delete goal |

---

## 📖 Subjects

| Method   | Endpoint                           | Description    |
| -------- | ---------------------------------- | -------------- |
| `POST`   | `/subjects/{goal_id}`              | Create subject |
| `GET`    | `/subjects/{goal_id}`              | Get subjects   |
| `GET`    | `/subjects/{goal_id}/{subject_id}` | Get subject    |
| `PUT`    | `/subjects/{goal_id}/{subject_id}` | Update subject |
| `DELETE` | `/subjects/{goal_id}/{subject_id}` | Delete subject |

---

## 📝 Study Tasks

| Method   | Endpoint                     | Description |
| -------- | ---------------------------- | ----------- |
| `POST`   | `/tasks/{goal_id}`           | Create task |
| `GET`    | `/tasks/{goal_id}`           | Get tasks   |
| `GET`    | `/tasks/{goal_id}/{task_id}` | Get task    |
| `PUT`    | `/tasks/{goal_id}/{task_id}` | Update task |
| `DELETE` | `/tasks/{goal_id}/{task_id}` | Delete task |

---

## 📊 Progress

| Method | Endpoint                   | Description       |
| ------ | -------------------------- | ----------------- |
| `POST` | `/progress`                | Create progress   |
| `GET`  | `/progress/task/{task_id}` | Get task progress |
| `GET`  | `/progress/goal/{goal_id}` | Get goal progress |

---

## 🤖 Study Plans

| Method | Endpoint                    | Description         |
| ------ | --------------------------- | ------------------- |
| `POST` | `/plans/generate/{goal_id}` | Generate study plan |

Example:

```http
POST /plans/generate/1
```

Response:

```json
{
  "message": "Study plan generated successfully",
  "goal_id": 1,
  "tasks_created": 5
}
```

---

## 🧠 AI Planner

| Method | Endpoint                       | Description           |
| ------ | ------------------------------ | --------------------- |
| `GET`  | `/ai/recommendation/{goal_id}` | Get AI recommendation |

---

## 🔄 Plan Adjustments

| Method | Endpoint                 | Description       |
| ------ | ------------------------ | ----------------- |
| `POST` | `/adjustments/{goal_id}` | Adjust study plan |

---

# 📘 API Documentation

FastAPI automatically provides interactive API documentation.

### Swagger UI

```text
http://127.0.0.1:8000/docs
```

### ReDoc

```text
http://127.0.0.1:8000/redoc
```

Swagger allows you to:

* Explore endpoints
* Send API requests
* Test request bodies
* Test authentication
* Inspect API responses
* Debug backend functionality

---

# 🖥️ Frontend

The project includes a lightweight frontend built with:

```text
HTML5
CSS3
JavaScript
```

The frontend communicates with the FastAPI backend using REST APIs.

### Frontend Entry Point

```text
frontend/index.html
```

### Styles

```text
frontend/css/style.css
```

### JavaScript

```text
frontend/js/main.js
```

---

# 📸 Screenshots

> Add your project screenshots here after capturing them from the running application.

### 🏠 Application

```text
screenshots/home.png
```

![AI Study Planner](screenshots/home.png)

---

### 📘 Swagger API Documentation

```text
screenshots/swagger.png
```

![Swagger API](screenshots/swagger.png)

---

### 📊 Study Dashboard

```text
screenshots/dashboard.png
```

![Study Dashboard](screenshots/dashboard.png)

---

### 🤖 Generated Study Plan

```text
screenshots/study-plan.png
```

![Generated Study Plan](screenshots/study-plan.png)

---

# 🚀 Installation

## 1. Clone Repository

```bash
git clone https://github.com/your-username/AI-Study-Planner.git
```

```bash
cd AI-Study-Planner
```

---

## 2. Create Virtual Environment

### Windows

```bash
python -m venv venv
```

Activate:

```bash
venv\Scripts\activate
```

### Linux/macOS

```bash
python3 -m venv venv
```

```bash
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Configure Environment

Create:

```text
.env
```

Add:

```env
APP_NAME=AI Study Planner
DATABASE_URL=sqlite:///./study_planner.db
SECRET_KEY=change-this-later
```

> ⚠️ Never commit real production secrets to GitHub.

---

## 5. Run the Application

```bash
uvicorn app.main:app --reload
```

Application:

```text
http://127.0.0.1:8000
```

---

# 🧪 Testing

Run:

```bash
pytest
```

The test suite covers important API functionality including:

* Root/health endpoint
* User registration
* User login
* Current user
* Goal creation
* Goal retrieval

---

# 🔒 Security

The backend implements:

* JWT authentication
* Password hashing
* Protected endpoints
* User ownership validation
* Pydantic request validation
* Environment configuration

### Production Improvements

Before production deployment:

* Use a strong secret key
* Store secrets securely
* Use PostgreSQL
* Enable HTTPS
* Configure CORS properly
* Add rate limiting
* Add refresh tokens
* Improve authentication/session handling

---

# 📈 Future Roadmap

* [ ] 🎨 Complete dashboard UI
* [ ] 📅 Study calendar
* [ ] 📊 Progress charts
* [ ] 📈 Analytics dashboard
* [ ] 🤖 Real LLM integration
* [ ] 🧠 Smarter plan optimization
* [ ] 🔔 Study reminders
* [ ] 📧 Email notifications
* [ ] 📱 Mobile-friendly improvements
* [ ] 🐘 PostgreSQL support
* [ ] 🐳 Docker support
* [ ] ☁️ Cloud deployment
* [ ] 🔄 Advanced adaptive learning system

---

# 🧠 What I Learned

Building this project helped me practice:

### Backend Development

* FastAPI application architecture
* REST API design
* Dependency injection
* Request/response validation
* CRUD operations
* Exception handling

### Database

* SQLAlchemy ORM
* Relational database design
* Foreign keys
* One-to-many relationships
* Cascading relationships

### Authentication

* JWT authentication
* Password hashing
* OAuth2 password flow
* Protected routes
* User ownership validation

### Business Logic

* Study plan generation
* Progress calculation
* Task scheduling
* Adaptive plan adjustments
* Recommendation logic

### Testing

* API testing
* Pytest
* Authentication testing
* CRUD testing

### Frontend

* HTML
* CSS
* JavaScript
* Fetch API
* REST API integration

---

# ⭐ Project Highlights

```text
⚡ FastAPI REST API
🔐 JWT Authentication
🗄️ SQLAlchemy ORM
💾 SQLite Database
📦 Pydantic Validation
🎯 Goal Management
📖 Subject Management
📝 Study Task Management
📊 Progress Tracking
🤖 AI Recommendations
🔄 Adaptive Plan Adjustments
🎨 Modern Frontend
🧪 Pytest
📘 Swagger Documentation
```

---

# 👨‍💻 Author

## Chaitanya Modi

**Python Backend Developer**

### Skills

```text
Python
FastAPI
Django
Django REST Framework
REST APIs
SQLAlchemy
SQLite
PostgreSQL
JWT
HTML
CSS
JavaScript
Git
GitHub
```

---

# ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is created for learning, development, and portfolio purposes.

````

