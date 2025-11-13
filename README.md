# final-project-e-learning-platform
Full-stack E-learning Platform for Underprivileged Children – SDG 4
## 1. Project Scope

### Title:
E-learning Platform for Underprivileged Children

### Scope:
This project aims to build a full-stack web application that provides accessible educational resources for underprivileged children. The platform will allow users to:

Access a catalog of courses and lessons

Take interactive quizzes with instant feedback

Track learning progress through dashboards

Optionally, engage in gamified learning experiences (badges, points)

The platform is designed to be responsive and user-friendly, accessible from both desktops and mobile devices.

### 2. Objectives

Increase access to quality education for underprivileged children through an online platform.

Provide interactive learning materials (text, images, quizzes) to enhance understanding.

Track student progress and provide feedback to support continuous learning.

Enable scalable and maintainable software architecture using a full-stack MERN approach.

Demonstrate practical full-stack development skills including front-end, back-end, database, and API integration.

### 3. SDG 4 Alignment (Quality Education)

Goal 4 – Quality Education: Ensure inclusive and equitable quality education and promote lifelong learning opportunities for all.

The platform aligns with SDG 4 by:

Providing free or low-cost educational resources

Supporting interactive and self-paced learning

Reaching children in areas with limited access to traditional schools or learning materials

### 4. Problem Statement

Many underprivileged children lack access to quality educational resources. Traditional schools may be under-resourced or too far away, and online platforms are often expensive or not localized. This project addresses this problem by creating a full-stack e-learning platform that is free, accessible, and interactive, helping children learn at their own pace and develop essential skills.

### 5. Market Analysis

Existing Platforms:

Khan Academy, Coursera, Udemy: Provide high-quality content but are often general, or partially paid.

### Gap:

Underprivileged children often cannot afford paid courses.

Limited localized or context-specific content is available.

Lack of interactive and gamified learning to increase engagement.

### Opportunity:

Create an accessible platform tailored to underserved communities.

Include quizzes, progress tracking, and gamification to encourage learning.

Potential partnerships with NGOs, schools, or local organizations.

## 6. Setup & Configuration

- **Environment variables**
  - `server/.env`
    - `MONGO_URI=<your Mongo connection string>`
    - `CLERK_SECRET_KEY=<Clerk secret key>`
    - Any other backend-specific settings (e.g. `PORT`)
  - `client/.env`
    - `VITE_CLERK_PUBLISHABLE_KEY=<Clerk publishable key>`
    - `VITE_API_URL=http://localhost:5000/api` (or your deployed API origin)

- **Authentication**
  - Clerk handles sign-in/sign-up UI (`/login`, `/register` routes) and session tokens.
  - Backend routes expect a valid Clerk session token via the `Authorization: Bearer <token>` header.
  - Local user records are synchronised automatically from Clerk on first authenticated request.

- **Running locally**
  - Install dependencies:
    - `npm install` inside both `client/` and `server/`
  - Start services:
    - Backend: `npm run dev` (or the configured start script) from `server/`
    - Frontend: `npm run dev` from `client/`
  - Ensure Clerk allowed origins include your local frontend URL (default `http://localhost:5173`).

- **Testing & QA recommendations**
  - Add integration tests covering Clerk-protected routes once credentials are configured.
  - Exercise enrolment/progress flows to confirm state updates without full page reloads.  

## 7. Live Demo  

You can access the deployed application here:   
[Final Project E-learning Platform](https://final-project-e-learning-platform.vercel.app)
