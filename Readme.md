# 📚 Litty - Your Modern Reading Companion

Litty helps you build consistent reading habits through progress tracking, challenges, and insightful analytics. Transform your reading journey with motivation and structure.

## 🎯 Live Demo

- **Web App**: [https://litty-front-end.onrender.com](https://litty-front-end.onrender.com)
- **API Documentation**: [https://litty-backend.onrender.com/docs](https://litty-backend.onrender.com/docs)

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| **📖 Reading Tracker** | Log reading sessions and visualize your progress |
| **🎯 Reading Challenges** | Participate in timed challenges to stay motivated |
| **📊 Reading Analytics** | View streaks, reading time, and completion statistics |
| **📚 Personal Library** | Organize and manage your book collection |
| **🏆 Achievement System** | Earn rewards for reading milestones and consistency |

## 🛠️ Technology Stack

### Frontend
- **React.js** - Modern UI framework
- **React Router** - Client-side navigation
- **Vite** - Fast build tool and dev server
- **CSS3** - Modern styling with flexbox/grid

### Backend
- **FastAPI** - High-performance Python web framework
- **SQLAlchemy** - Python SQL toolkit and ORM
- **JWT** - Secure authentication
- **PostgreSQL** - Relational database
- **Pydantic** - Data validation

### Deployment & Infrastructure
- **Render.com** - Cloud platform for both frontend and backend
- **PostgreSQL** - Managed database service

## 🚀 Quick Start

### Prerequisites
- **Node.js** (v16 or higher)
- **Python** (v3.9 or higher)
- **PostgreSQL** (v12 or higher)

### Local Development Setup

#### 1. Clone & Setup
```bash
# Clone both repositories
git clone https://github.com/Inema-Leslie/Litty-backend 
git clone https://github.com/Inema-Leslie/Litty-front-end

# Create project directory structure
mkdir litty-app && cd litty-app
mv ../litty-frontend .
mv ../litty-backend .
2. Backend Setup
bash
cd litty-backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Environment setup
cp .env.example .env
# Edit .env with your database credentials
3. Database Setup
Option A: Local PostgreSQL

Install PostgreSQL from postgresql.org

Start PostgreSQL service

Create database:

sql
CREATE DATABASE litty;
Option B: Docker (Easier)

bash
# Run PostgreSQL in Docker
docker run --name litty-postgres -e POSTGRES_PASSWORD=password -e POSTGRES_DB=litty -p 5432:5432 -d postgres
Update your .env file:

env
DATABASE_URL=postgresql://postgres:password@localhost:5432/litty
JWT_SECRET_KEY=your-super-secret-key-here
JWT_ALGORITHM=HS256
4. Frontend Setup
bash
cd ../litty-frontend

# Install dependencies
npm install

# Environment setup
cp .env.example .env
Update frontend .env:

env
VITE_API_URL=http://localhost:8000
5. Run the Application
bash
# Terminal 1 - Backend (runs on http://localhost:8000)
cd litty-backend
python main.py

# Terminal 2 - Frontend (runs on http://localhost:5173)
cd litty-frontend
npm run dev
Visit http://localhost:5173 to start using Litty!

 API Reference
Authentication
Method	Endpoint	        Description
POST	/api/auth/register	Create new user account
POST	/api/auth/login	    User authentication
GET	/api/auth/me	        Get current user profile
Reading Management
Method	Endpoint	            Description
GET	/api/books/popular-books    Discover popular books
POST	/api/reader/log-reading	Log reading session
Challenges
Method	Endpoint	                Description
GET	/api/challenges/	            Browse available challenges
GET	/api/user/challenges	        Get user's active challenges
POST	/api/challenges/{id}/start	Start a new challenge
User Analytics
Method	Endpoint	    Description
GET	/api/user/streak	Get current reading streak


 Deployment
Backend Deployment (Render)
Connect GitHub repository to Render

Create Web Service

Build Command: pip install -r requirements.txt

Start Command: python main.py

Add environment variables in Render dashboard

Frontend Deployment (Render)
Create Static Site

Build Command: npm run build

Publish Directory: dist

Environment Variable: VITE_API_URL=https://litty-backend.onrender.com

Environment Variables
Backend (.env)

env
DATABASE_URL=postgresql://user:pass@host:port/database
JWT_SECRET_KEY=your-256-bit-secret
JWT_ALGORITHM=HS256
Frontend (.env)

env
VITE_API_URL=https://litty-backend.onrender.com/


Troubleshooting
Common Issues
Database Connection Errors

Verify PostgreSQL is running: sudo service postgresql status

Check connection string format

Ensure database exists: \l in psql

CORS Issues

Confirm frontend URL is in backend CORS origins

Check environment variables match between frontend and backend

Build Failures

Verify Node.js version: node --version

Check Python version: python --version

Clear dependencies and reinstall






