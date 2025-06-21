# Django User Authentication System

## Overview

A robust user authentication system built using Django 5.2.3. This system allows users to securely sign up, log in, log out, change passwords, reset forgotten passwords via email, verify their email before activation, manage their profile (edit details, upload avatar), and ensures session and security best practices.

## Features

### Core Features

1. **User Signup**
   New users can register using their username, email, and password. An email verification link is sent to activate the account.

2. **User Login**
   Only verified (activated) users can log in using their credentials.

3. **User Logout**
   Users can securely log out of their session.

4. **Password Reset via Email**
   Users can request a password reset link via email to reset their forgotten password.

5. **Password Change**
   Logged-in users can change their password from within the application.

6. **Email Verification**
   Activation email is sent on signup; accounts remain inactive until the user verifies the link.

7. **Session Management**

   * Session expiry is set to 20 minutes (1200 seconds).
   * Sessions expire upon browser close.

8. **Input Validation**

   * Strong password validation (minimum 8 characters, not too similar, not numeric-only, etc.).
   * Valid email format enforced.
   * Form validation feedback with user-friendly error messages.

### Bonus Features

1. **User Profile Management**
   Users can update their profile and upload an avatar (image).

## Tech Stack

* Python 3.12
* Django 5.2.3
* SQLite (default DB)
* Bootstrap 5.3 (for UI)
* Pillow (for image upload in profile)
* Git (version control)

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/django-auth-system.git
cd django-auth-system
```

### 2. Set Up a Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate  # Windows
# OR
source venv/bin/activate  # macOS/Linux
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Apply Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 5. Create Superuser (Admin)

```bash
python manage.py createsuperuser
```

### 6. Run the Development Server

```bash
python manage.py runserver
```

Visit: `http://127.0.0.1:8000/`

## Folder Structure

```
django-auth-system/
│
├── accounts/
│   ├── migrations/
│   ├── templates/
│   │   ├── accounts/
│   │   │   ├── activation_email.html
│   │   │   ├── activation_sent.html
│   │   │   ├── activation_success.html
│   │   │   ├── edit_profile.html
│   │   │   ├── home.html
│   │   │   ├── login.html
│   │   │   ├── logout.html
│   │   │   └── signup.html
│   │   └── registration/
│   │       ├── password_change_form.html
│   │       ├── password_reset_complete.html
│   │       ├── password_reset_confirm.html
│   │       ├── password_reset_done.html
│   │       └── password_reset_form.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── signals.py
│   ├── urls.py
│   └── views.py
│
├── auth_system/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── db.sqlite3
├── manage.py
├── requirements.txt
└── README.md
```

## Security Features

* CSRF protection enabled
* Password hashing (Django default)
* Email verification before login
* Session expiry (set in `settings.py`)
* Image upload validation via Pillow
* Secure password policies

## Notes

* Uses **Django's Console Email Backend** for demo purposes. In production, configure SMTP in `settings.py`.
* Static files can be served via `/static/` (configured in `settings.py`).

## Future Improvements

* Social authentication (Google, Facebook)
* Two-Factor Authentication (2FA)
* Account lockout after multiple failed attempts
* "Remember Me" functionality

## Author

* Name: Deshna Jain
* GitHub: (https://github.com/deshna0620)
