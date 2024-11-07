# Celvora Task Manager

Celvora Task Manager is a task management web application built with Django for the backend and Vue.js for the frontend. This application allows users to create, read, update, and delete tasks.

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Getting Started](#getting-started)
  - [Backend Setup (Django)](#backend-setup-django)
  - [Frontend Setup (Vue.js)](#frontend-setup-vuejs)
- [Configuration](#configuration)
  - [CORS](#cors-configuration)
- [Usage](#usage)

---

## Project Overview

Celvora Task Manager is a web-based application where users can manage tasks with features like adding, viewing, editing, and deleting tasks. This project demonstrates the integration between a Django REST API backend and a Vue.js frontend.

## Technologies Used

- **Backend**: Django, Django REST Framework
- **Frontend**: Vue.js
- **Database**: SQLite (or any other Django-supported database)
- **Other**: Axios (for handling HTTP requests in Vue)

---

## Getting Started

These instructions will help you set up and run the project on your local machine.

### Prerequisites
- Python 3.x
- Node.js and npm
- Git

### Clone the Repository
```bash
git clone https://github.com/manasapuellela/celvora-task-manager.git
cd celvora-task-manager '''

### **Backend Setup (Django)**

### **Create a virtual environment:**
python -m venv myenv
source myenv/bin/activate  # On Windows, use `myenv\Scripts\activate`

### **Install the dependencies:**
pip install -r requirements.txt

### **Run migrations:**
python manage.py migrate

### **Start the Django server:**
python manage.py runserver

### **Frontend Setup (Vue.js)**

### **Navigate to the frontend directory:**
cd frontend

### **Install dependencies:**
npm install

### **Run the Vue development server:**
npm run serve

# **Configuration**

# **CORS Configuration**

# In settings.py, add the frontend URL (http://localhost:8080) to the CORS ALLOWED_ORIGINS to allow the frontend to communicate with the backend API.
CORS_ALLOWED_ORIGINS = [
    "http://localhost:8080",
]

# **Usage**

# Once both the Django and Vue servers are running:
# Visit http://localhost:8080 in your browser to access the frontend.
# The application should now be able to interact with the backend API for task management.

