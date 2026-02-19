# Full Stack Product Dashboard – Assignment Submission

## Overview

This project is a full-stack web application built using **Next.js (Frontend)** and **FastAPI (Backend)**. It implements authentication, dashboard interface, and advanced product listing with **cursor-based pagination, searching, sorting, filtering, and secure API integration**.

The application follows a **scalable production-ready architecture** with proper separation of concerns between frontend and backend layers.

---







## Tech Stack

### Frontend

* Next.js (App Router)
* React
* TypeScript
* TailwindCSS
* Axios
* Cursor-based pagination
* Feature-based architecture

### Backend

* FastAPI
* Python
* SQLAlchemy ORM
* PostgreSQL / SQLite
* JWT Authentication
* Cursor-based pagination
* REST API architecture

---

## Features

### Authentication

* User Registration
* User Login
* JWT Token authentication
* Secure protected endpoints

---

### Dashboard

* Responsive layout
* Sidebar navigation
* Navbar with theme toggle
* Logout functionality
* Summary metrics

---

### Product Listing (Core Feature)

Fully implemented advanced functionality:

* Cursor-based pagination
* Next and Previous page navigation
* Searching by product name
* Filtering by category and price
* Sorting by:

  * created_at
  * price
  * rating
* Combined filtering + pagination support
* Backend integration
* Efficient large dataset handling

---

## Cursor-Based Pagination Implementation

Instead of traditional page numbers, cursor pagination is used.

Backend returns:

```
{
  data: [...],
  next_cursor: "...",
  has_more: true
}
```

Frontend stores cursor history:

```
Page 1 → cursor undefined
Page 2 → cursor A
Page 3 → cursor B
```

This allows efficient navigation without performance degradation.

Benefits:

* High performance
* Scalable
* No offset inefficiency
* Production standard approach

---

## Project Structure

```
project-root/
│
├── frontend_app/
│   ├── src/
│   │   ├── app/
│   │   ├── features/
│   │   ├── components/
│   │   ├── services/
│   │   ├── hooks/
│   │   ├── utils/
│   │   ├── types/
│   │   └── styles/
│   ├── .env.local
│   └── package.json
│
├── backend_app/
│   ├── src/
│   │   ├── modules/
│   │   │   ├── auth/
│   │   │   ├── product/
│   │   │   └── dashboard/
│   │   ├── core/
│   │   ├── utils/
│   │   └── app.py
│   ├── scripts/
│   └── requirements.txt
│
└── README.md
```

---

## Architecture Overview

### Frontend Architecture

Feature-based structure:

```
features/
  products/
    components/
    services.ts
    types.ts
```

API layer abstraction:

```
services/api.ts
```

Handles:

* Base URL
* Token injection
* API communication

---

### Backend Architecture

Modular FastAPI structure:

```
modules/
  auth/
  product/
  dashboard/
```

Each module contains:

```
router.py
service.py
crud.py
schema.py
model.py
```

Separation of:

* API layer
* Business logic
* Database layer

---

## API Endpoints

Authentication:

```
POST /auth/register
POST /auth/login
GET /auth/me
```

Products:

```
GET /products
POST /products
PUT /products/{id}
DELETE /products/{id}
```

---

## Setup Instructions

### Backend Setup

Navigate to backend folder:

```
cd backend_app
```

Create virtual environment:

```
python -m venv venv
```

Activate:

Windows:

```
venv\Scripts\activate
```

Install dependencies:

```
pip install -r requirements.txt
```

Run server:

```
uvicorn src.app:app --reload
```

Backend runs at:

```
http://127.0.0.1:8000
```

---

### Frontend Setup

Navigate to frontend folder:

```
cd frontend_app
```

Install dependencies:

```
npm install
```

Create environment file:

```
.env.local
```

Add:

```
NEXT_PUBLIC_API_URL=http://127.0.0.1:8000
```

Run frontend:

```
npm run dev
```

Frontend runs at:

```
http://localhost:3000
```

---

## Deployment

Frontend deployed using:

```
Vercel
```

Backend deployed using:

```
Render
```

Environment variable used:

```
NEXT_PUBLIC_API_URL=https://backend-url.com
```

---

## Database

Uses SQLAlchemy ORM with:

* SQLite (development)
* PostgreSQL (production)

---

## Best Practices Followed

* Clean architecture
* Feature-based structure
* Separation of concerns
* Cursor-based pagination
* Secure authentication
* Environment variable configuration
* Production-ready structure
* Modular backend design

---

## Assumptions

* Backend provides cursor pagination
* JWT authentication used
* API endpoints available

---

## Time Taken

Estimated development time:

```
12–18 hours
```

Includes:

* Backend development
* Frontend development
* Pagination logic
* Authentication
* Debugging
* Testing
* Deployment preparation

---

## Future Improvements

* Unit testing
* Global state management
* Performance optimization
* Caching layer
* Role-based access control
* CI/CD pipeline

---

## Conclusion

This project demonstrates:

* Full-stack application development
* Cursor-based pagination implementation
* Production-ready architecture
* Clean, scalable code structure
* Proper frontend-backend integration

The system is designed for scalability, maintainability, and performance.

🌐 Live Demo

🔗 Frontend:
https://clabs-joitleb3a-abhis-projects-db8c8177.vercel.app

🔗 Backend API:
https://deploytest-vlmn.onrender.com



---
