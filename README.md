# Django User Authentication and CRUD

This project is a Django application that provides user authentication (Sign Up, Sign In, Sign Out) and CRUD (Create, Read, Update, Delete) operations for users.

## Features

- User Registration (Sign Up)
- User Login (Sign In)
- User Logout (Sign Out)
- List all users
- View user details
- Update user information
- Delete users

## Technologies Used

- Django
- PostgreSQL
- Python

## Setup Instructions

### 1. Clone the repository

```bash
git clone <repository_url>
cd django_user_auth
```

### 2. Create and activate a virtual environment

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

(Note: You will need to create a `requirements.txt` file with `pip freeze > requirements.txt` after installing all dependencies.)

### 4. PostgreSQL Setup

Ensure you have PostgreSQL installed and running. Create a database and a user for this project. Replace `mydatabase`, `myuser`, and `mypassword` with your desired values.

```sql
CREATE USER myuser WITH PASSWORD 'mypassword';
CREATE DATABASE mydatabase;
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
```

### 5. Environment Variables

Create a `.env` file in the `django_user_auth` directory with your PostgreSQL credentials:

```
DB_NAME=mydatabase
DB_USER=myuser
DB_PASSWORD=mypassword
DB_HOST=localhost
DB_PORT=5432
```

### 6. Run Migrations

Navigate to the `django_user_auth` directory and run the migrations:

```bash
cd django_user_auth
PYTHONPATH=$(pwd) DJANGO_SETTINGS_MODULE=django_user_management.settings python3 manage.py migrate
```

### 7. Create a Superuser (Optional)

To access the Django admin panel, create a superuser:

```bash
PYTHONPATH=$(pwd) DJANGO_SETTINGS_MODULE=django_user_management.settings python3 manage.py createsuperuser
```

### 8. Run the Development Server

```bash
PYTHONPATH=$(pwd) DJANGO_SETTINGS_MODULE=django_user_management.settings python3 manage.py runserver
```

Access the application at `http://127.0.0.1:8000/`

## Usage

- **Sign Up:** Navigate to `/signup/` to create a new user account.
- **Sign In:** Navigate to `/signin/` to log in.
- **User List:** After logging in, you can view the list of users at `/users/`.
- **User Details, Update, Delete:** From the user list, click on a username to view details, and then you'll see options to update or delete the user.

