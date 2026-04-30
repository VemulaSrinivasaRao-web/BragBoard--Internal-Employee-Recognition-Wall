# BragBoard--Internal-Employee-Recognition-Wall
BragBoard is a web-based employee recognition platform built with React, FastAPI, and PostgreSQL. It enables users to post shout-outs, tag colleagues, and interact via reactions and comments. With JWT authentication and an admin dashboard, it ensures secure access, moderation, analytics, and promotes workplace appreciation.


Here’s a clear, step-by-step guide to set up and run your BragBoard project in VS Code 👇

1. Install Required Tools

Install these first:

Visual Studio Code
Node.js (includes npm)
Python (3.9+)
PostgreSQL
Git

Check installation:

node -v
npm -v
python --version
git --version
2. Open Project in VS Code
cd BragBoard
code .
3. Setup Backend (FastAPI)
Step 1: Create virtual environment (venv)
python -m venv venv
Step 2: Activate venv
Windows:
venv\Scripts\activate
Mac/Linux:
source venv/bin/activate
Step 3: Install FastAPI & tools
pip install fastapi uvicorn psycopg2-binary python-jose passlib[bcrypt]
Step 4: Create main file

Create main.py:

from fastapi import FastAPI

app = FastAPI()

@app.get("/")
def home():
    return {"message": "BragBoard Backend Running"}
Step 5: Run backend server
uvicorn main:app --reload

👉 Open: http://127.0.0.1:8000

4. Setup Frontend (React)
Step 1: Create React app
npx create-react-app frontend
cd frontend
Step 2: Install dependencies
npm install axios react-router-dom tailwindcss
Step 3: Run frontend
npm start

👉 Open: http://localhost:3000

5. Setup Tailwind CSS
npx tailwindcss init

Add in tailwind.config.js:

content: ["./src/**/*.{js,jsx}"]

In index.css:

@tailwind base;
@tailwind components;
@tailwind utilities;
6. Setup PostgreSQL Database
Open pgAdmin / terminal
Create database:
CREATE DATABASE bragboard;
Connect in FastAPI using:
DATABASE_URL = "postgresql://user:password@localhost/bragboard"
7. Run Full Project

Open 2 terminals in VS Code:

Terminal 1 (Backend)
cd backend
venv\Scripts\activate
uvicorn main:app --reload
Terminal 2 (Frontend)
cd frontend
npm start
8. Folder Structure (Recommended)
BragBoard/
 ├── backend/
 │    ├── venv/
 │    ├── main.py
 │
 ├── frontend/
 │    ├── src/
 │
 └── README.md
