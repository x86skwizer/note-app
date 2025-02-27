Collecting workspace information# Note App

Note App is a full-stack web application for creating, viewing, and deleting notes. The backend is built with Django and Django REST framework, while the frontend is built with React and Vite.

## Features

- User registration and authentication
- JWT-based authentication
- Create, view, and delete notes
- Protected routes for authenticated users

## Project Structure

```
.gitignore
.vscode/
backend/
    api/
        __init__.py
        admin.py
        apps.py
        migrations/
        models.py
        serializers.py
        tests.py
        urls.py
        views.py
    backend/
        __init__.py
        asgi.py
        settings.py
        urls.py
        wsgi.py
    db.sqlite3
    manage.py
    requirements.txt
frontend/
    .env
    .gitignore
    eslint.config.js
    index.html
    package.json
    public/
    src/
        api.js
        App.jsx
        assets/
        components/
        constants.js
        main.jsx
        pages/
        styles/
    vite.config.js
README.md
```

## Backend

The backend is a Django project with a single app called `api`. It provides RESTful endpoints for user registration, authentication, and note management.

### Installation

1. Navigate to the backend directory:
    ```sh
    cd backend
    ```

2. Create a virtual environment and activate it:
    ```sh
    python -m venv .venv
    source .venv/bin/activate  # On Windows use `.venv\Scripts\activate`
    ```

3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

4. Apply the migrations:
    ```sh
    python manage.py migrate
    ```

5. Run the development server:
    ```sh
    python manage.py runserver
    ```

### API Endpoints

- `POST /api/user/register/` - Register a new user
- `POST /api/token/` - Obtain JWT token
- `POST /api/token/refresh/` - Refresh JWT token
- `GET /api/notes/` - List all notes for the authenticated user
- `POST /api/notes/` - Create a new note
- `DELETE /api/notes/delete/<int:pk>/` - Delete a note by ID

## Frontend

The frontend is a React application bootstrapped with Vite. It interacts with the backend API to provide a seamless user experience.

### Installation

1. Navigate to the frontend directory:
    ```sh
    cd frontend
    ```

2. Install the required packages:
    ```sh
    npm install
    ```

3. Start the development server:
    ```sh
    npm run dev
    ```

### Environment Variables

Create a .env file in the frontend directory with the following content:
```
VITE_API_URL="http://127.0.0.1:8000"
```

## Running the Application

1. Start the backend server:
    ```sh
    cd backend
    source .venv/bin/activate
    python manage.py runserver
    ```

2. Start the frontend development server:
    ```sh
    cd frontend
    npm run dev
    ```

3. Open your browser and navigate to `http://localhost:5173/`.