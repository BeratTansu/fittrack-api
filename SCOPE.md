# FitTrack — Project Scope

## 1. Overview

FitTrack is a personal workout tracking app, allowing users to log sessions, review history, and see clear progress week by week.

## 2. Problem & Motivation

Many lifters, including myself, often struggle to remember how much weight they lifted in their last workout, which makes consistent progress difficult. FitTrack allows them to easily log their workouts, sets and weights and shows how much progress they have made with stats, charts and comparisons.

## 3. User Stories

- As a user, I want to create an account, so that I can record and track my progress.
- As a user, I want to log in, so that I can access my existing account.
- As a user, I want to add a workout for a specific day, so that I can keep a record of my training sessions.
- As a user, I want to add exercises (sets, reps, weight) to a workout, so that I can see exactly what I did and how much I lifted.
- As a user, I want to view my progress statistics, so that I can understand my overall improvement and stay motivated.

## 4. MVP Features

The first version of FitTrack will include the following features:

### Authentication
- User registration with email and password
- User login that returns a JWT token
- Password hashing with bcrypt for security
- Protected endpoints accessible only with a valid token

### Workout Management
- Create, view, update, and delete workouts
- Each workout has a name, date, optional duration, and optional notes
- Users can only see and modify their own workouts

### Exercise Management
- Add exercises to a specific workout
- Each exercise stores sets, reps, weight, and optional notes
- Update or delete individual exercises

### Body Measurements
- Record body measurements (weight, body fat, chest, waist, arm)
- View measurement history over time

### Statistics
- View basic stats: weekly workout count, total weight lifted, most frequent exercise

## 5. Out of Scope

The following features are intentionally excluded from the MVP to keep the project focused and achievable within the 10-week timeline:

- **Social features (friends, sharing, feed):** Adds significant complexity (relationships, permissions, real-time updates) without serving the core goal of personal progress tracking.
- **Pre-built workout programs:** Requires content curation and a separate data model. The MVP focuses on user-generated workouts only.
- **AI coaching or recommendations:** Would require ML infrastructure, training data, and ongoing model maintenance — far beyond the scope of a learning project.
- **Nutrition tracking:** A full feature on its own (food database, macro calculations). Combining it with workout tracking dilutes the focus.
- **Mobile application:** Web-only for the MVP. A mobile app would require a separate codebase (React Native or native development) and double the workload.
- **Push notifications:** Requires third-party services (Firebase, OneSignal) and significantly complicates deployment for marginal value at this stage.
- **Video integration (exercise tutorials):** Requires content licensing or hosting infrastructure. Users can find tutorials elsewhere; FitTrack's job is tracking, not teaching.

## 6. Tech Stack

FitTrack is built as a full-stack web application. The backend is a **FastAPI** (Python) service that exposes a RESTful API and handles authentication via **JWT**. Data is stored in a **PostgreSQL** database, accessed through the **SQLAlchemy** ORM, with schema migrations managed by **Alembic**. Passwords are hashed with **bcrypt**. The frontend is a single-page application built with **React** (Vite) and styled with **Tailwind CSS**. The entire backend stack runs locally via **Docker Compose**, with the production backend deployed to **Render** and the frontend to **Vercel**.