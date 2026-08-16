## Full-Stack Library Management System

A full-stack **Library Management System** developed using React, TypeScript, Spring Boot, Hibernate/JPA, MySQL, and REST APIs. The system provides role-based functionality for managing users, books, borrowing, returns, book requests, subscriptions, waitlists, penalties, acquisitions, recommendations, and library reports.

## Features

- User registration and login
- JWT-based authentication
- Role-based access control
- User profile management
- Book management and inventory
- Search and browse books
- Book borrowing and returning
- Borrowing history
- Book request management
- Book waitlist and reservations
- Subscription and membership management
- Overdue penalty calculation and payment
- Book acquisition requests
- Personalized book recommendations
- Popular books and category analytics
- Library reports
- Email verification and notifications
- Admin and librarian management features

## Technologies Used

### Frontend

- React
- TypeScript
- Vite
- React Router
- Axios
- Recharts
- Framer Motion
- HTML
- CSS

### Backend

- Java 17
- Spring Boot
- Spring Data JPA
- Hibernate
- Spring Security
- JWT
- REST APIs
- Maven
- Lombok
- JavaMail

### Database

- MySQL

### Testing

- JUnit
- Mockito
- H2 Database
- Spring Security Test

## Project Structure

```

LMS-master/
│
├── backend/
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/infy/lms/
│   │       │       ├── config/
│   │       │       ├── controller/
│   │       │       ├── dto/
│   │       │       ├── enums/
│   │       │       ├── exception/
│   │       │       ├── model/
│   │       │       ├── repository/
│   │       │       ├── scheduler/
│   │       │       ├── security/
│   │       │       └── service/
│   │       │
│   │       └── resources/
│   │           └── application.properties
│   │
│   ├── pom.xml
│   ├── mvnw
│   └── mvnw.cmd
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── api/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── context/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   └── types/
│   │
│   ├── package.json
│   ├── vite.config.ts
│   └── tsconfig.json
│
└── README.md

```

## How It Works

```

User
↓
React Frontend
↓
REST API
↓
Spring Boot Controllers
↓
Service Layer
↓
Repository Layer
↓
Hibernate / JPA
↓
MySQL Database

```

The application uses **JWT-based authentication and Spring Security** to provide secure, role-based access to different library operations.

## Main Modules

### User Management

- User registration
- Login and authentication
- Email verification
- Password reset
- Profile management
- Role-based access

### Book Management

- Add books
- View books
- Search books
- Update books
- Delete books
- Manage book availability
- Manage book inventory

### Borrowing & Returns

- Borrow books
- Return books
- Track borrowed books
- View borrowing history
- Manage overdue books
- Calculate penalties

### Book Requests

- Request books
- Approve or reject requests
- View request history
- Bulk request approval

### Waitlist

- Join book waitlist
- Leave waitlist
- View waitlist position
- Manage reservations
- Manage waitlist priority

### Membership / Subscription

- View membership packages
- Activate membership
- Extend membership
- Check membership status

### Penalties

- Calculate overdue penalties
- View pending penalties
- Pay penalties
- Waive penalties
- View penalty history

### Acquisition

- Submit book acquisition requests
- View requests
- Approve requests
- Reject requests

### Recommendations & Analytics

- Personalized book recommendations
- Popular books
- Category trends
- Popular book analytics
- Time-series analysis
- Export analytics

### Reports

- Generate library reports
- Download reports
- View library statistics

## Database

The application uses **MySQL** as the relational database.

Database configuration:

```

Database: librarydb
Host: localhost
Port: 3306

```

The database schema is managed using **Hibernate/JPA** with Spring Boot.

## Installation

### Backend

Navigate to the backend directory:

```

cd backend

```

Run the Spring Boot application:

### Windows

```

mvnw.cmd spring-boot:run

```

### Linux / macOS

```

./mvnw spring-boot:run

```

The backend runs on:

```

[http://localhost:8081](http://localhost:8081)

```

### Frontend

Navigate to the frontend directory:

```

cd frontend

```

Install the required dependencies:

```

npm install

```

Start the development server:

```

npm run dev

```

## Usage

1. Start the MySQL database.
2. Configure the database credentials in the backend configuration.
3. Start the Spring Boot backend.
4. Start the React frontend.
5. Register or log in to the application.
6. Access features according to the assigned user role.
7. Manage books, borrowing, returns, requests, memberships, penalties, and other library operations.

## Authentication Flow

```

Registration
↓
Email Verification
↓
Login
↓
JWT Token
↓
Role-Based Access
↓
Library Management Features

```

## API Testing

The REST APIs can be tested using **Postman**.

Major API modules include:

```

Authentication
Books
Borrowing
Returns
Book Requests
Acquisition Requests
Waitlist
Subscriptions
Penalties
Recommendations
Reports

```

## Author

This project is developed for **internship purposes** to demonstrate full-stack application development using **Java, Spring Boot, React, REST APIs, Hibernate/JPA, Spring Security, JWT, and MySQL**.

**Author:** Abhijna R S
