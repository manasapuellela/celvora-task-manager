Celvora Task Manager
A task management web application built with Django for the backend and Vue.js for the frontend. This application allows users to create, read, update, and delete tasks.

Table of Contents
Project Overview
Technologies Used
Getting Started
Installation
Usage
Folder Structure
API Endpoints
Screenshots
Contributing
License
Project Overview
Celvora Task Manager is a web-based application where users can manage tasks with features like adding, viewing, editing, and deleting tasks. The application demonstrates the integration between a Django REST API backend and a Vue.js frontend.

Technologies Used
Backend: Django, Django REST Framework
Frontend: Vue.js
Database: SQLite (or any other Django-supported database)
Other: Axios (for handling HTTP requests in Vue)
Getting Started
These instructions will help you set up and run the project on your local machine.

Prerequisites
Python 3.x
Node.js and npm
Git
Installation
Clone the repository:

bash
Copy code
git clone https://github.com/manasapuellela/celvora-task-manager.git
cd celvora-task-manager
Backend Setup (Django):

Create a virtual environment:

bash
Copy code
python -m venv myenv
source myenv/bin/activate  # On Windows use `myenv\Scripts\activate`
Install the dependencies:

bash
Copy code
pip install -r requirements.txt
Run migrations:

bash
Copy code
python manage.py migrate
Start the Django server:

bash
Copy code
python manage.py runserver
Frontend Setup (Vue.js):

Navigate to the frontend directory:

bash
Copy code
cd frontend
Install dependencies:

bash
Copy code
npm install
Run the Vue development server:

bash
Copy code
npm run serve
Configuration for CORS (Cross-Origin Resource Sharing):

In settings.py, add the frontend URL (http://localhost:8080) to the CORS_ALLOWED_ORIGINS to allow the frontend to communicate with the backend.

Usage
Once the servers are running:

Open the Vue.js frontend at http://localhost:8080
The Django API will be accessible at http://127.0.0.1:8000/api/
Main Features
Add Task: Input task details and add to the list.
View Task: See the list of all tasks.
Edit Task: Modify task details.
Delete Task: Remove a task from the list.
Folder Structure
css
Copy code
celvora-task-manager/
├── backend/
│   ├── manage.py
│   ├── celvora_store/
│   │   ├── settings.py
│   │   └── ...
│   ├── tasks/
│       ├── models.py
│       ├── views.py
│       └── ...
└── frontend/
    ├── src/
    │   ├── components/
    │       └── TaskList.vue
    │   ├── App.vue
    │   └── main.js
    └── public/
API Endpoints
Endpoint	Method	Description
/api/tasks/	GET	List all tasks
/api/tasks/	POST	Create a new task
/api/tasks/<id>/	PUT	Update a specific task
/api/tasks/<id>/	DELETE	Delete a specific task
Screenshots
Include a few screenshots of your project in action. You can add these as links or embed them directly in the README using Markdown:

markdown
Copy code
![Home Page](screenshots/home.png)
![Add Task](screenshots/add-task.png)
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature-name).
Make your changes.
Commit and push your changes (git commit -m "Description").
Open a pull request.
License
