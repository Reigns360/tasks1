TASK TRACKER
Is a web app designed to help users track their tasks. It provides a simple and intuitive interface for managing tasks efficiently.

FEATURES
Create Tasks: Add new tasks with a title and description.
Update Tasks: Edit existing tasks to update their details.
Delete Tasks: Remove unwanted tasks from the list.

TECHNOLOGIES USED
Backend: Django, Django REST Framework
Frontend: Vue.js, Axios
Database: SQLite (default for Django)

INSTALLATION

Prerequisites
Python 3.x
Node.js and npm

BACKEND SETUP (Django)
Clone the repository:

bash
git clone https://github.com/yourusername/task-tracker.git
cd task-tracker
Create and activate a virtual environment:

bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
Install dependencies:

pip install django djangorestframework
Run migrations and start the Django server:

python manage.py migrate
python manage.py runserver

FRONTEND SETUP (Vue.js)
Navigate to the frontend directory:

bash
cd task-tracker-frontend
Install dependencies:

npm install
Run the Vue.js development server:

arduino
npm run serve

USAGE
Open your web browser and navigate to http://localhost:8080.
You'll see the Task Tracker interface.
Use the provided options to add, update, delete, and mark tasks as complete.
