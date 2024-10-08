# User-Management-Django-Backend

## Overview

This backend project provides a user management system built with Django and Django REST Framework. It supports user registration, login, and JWT authentication.

## Features

- **User Registration:** Allows users to sign up with an email, password, first name, last name, and phone number.
- **User Login:** Authenticates users using email and password, and returns JWT tokens for session management.
- **Custom User Model:** Utilizes a custom user model with email as the unique identifier.

## Requirements

- Python 3.x
- Django 4.x
- Django REST Framework
- djangorestframework-simplejwt
- psycopg2-binary (for PostgreSQL)

## Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Vishnu021198/User-Management-Django-Backend.git
   ```

2. **Create and activate a virtual environment:**

   ```bash
   python -m venv env
   source env/bin/activate  # On Windows use `env\Scripts\activate`
   ```

3. **Install the required packages:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Apply database migrations:**

   ```bash
   python manage.py migrate
   ```

5. **Create a superuser (for admin access):**

   ```bash
   python manage.py createsuperuser
   ```

6. **Run the development server:**

   ```bash
   python manage.py runserver
   ```

## API Endpoints

- **Register User:** `POST /api/register/`
- **Login User:** `POST /api/login/`

### Request Payloads

**Register User**

```json
{
    "email": "user@example.com",
    "password": "yourpassword",
    "first_name": "First",
    "last_name": "Last",
    "phone_number": "1234567890"
}
```

**Login User**

```json
{
    "email": "user@example.com",
    "password": "yourpassword"
}
```

### Response

**Register User**

```json
{
    "status": "User registered successfully"
}
```

**Login User**

```json
{
    "refresh": "your_refresh_token",
    "access": "your_access_token"
}
```

## Configuration

- Update the `DATABASES` settings in `settings.py` for PostgreSQL database configuration.
- Configure JWT settings in `settings.py` for token management.