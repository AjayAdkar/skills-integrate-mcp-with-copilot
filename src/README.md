# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.

## Features

- View all available extracurricular activities
- Sign up for activities

## Getting Started

1. Install the dependencies:

   ```
   pip install fastapi uvicorn
   ```

2. Run the application:

   ```
   python app.py
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/auth/register`                                                  | Register a new user                                                  |
| POST   | `/auth/login`                                                     | Log in and receive a bearer token                                    |
| GET    | `/users/me`                                                       | Get currently authenticated user                                     |
| GET    | `/users`                                                          | List all users (admin only)                                          |
| POST   | `/activities/{activity_name}/signup`                              | Sign up for an activity (students sign self up; admins can sign up other students) |
| DELETE | `/activities/{activity_name}/unregister`                          | Unregister from an activity (students unregister self; admins can remove others) |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level

All data is stored in memory, which means data will be reset when the server restarts.
