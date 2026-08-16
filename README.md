## Full-Stack Library Management System


**BookVault** is a full-stack Library Management System designed to manage books, users, borrowing, returns, penalties, subscriptions, waitlists, book requests, acquisitions, recommendations, and library analytics.


The application follows a modern client-server architecture with a **React + TypeScript frontend** and a **Spring Boot REST API backend**, backed by **MySQL**.


---


## Features


### User Authentication & Account Management


- User registration and login
- JWT-based authentication
- Role-based access control
- User profile management
- Forgot password functionality
- Password reset functionality
- Email account verification
- Secure authentication using Spring Security


### Book Management


- Add new books
- View all books
- Search books
- View book details
- Update book information
- Delete books
- Update book availability
- Manage book inventory
- ISBN-based book management


### Book Borrowing


- Borrow books
- Return books
- View borrowing history
- Track currently borrowed books
- View overdue books
- Calculate penalties for overdue books
- Pay penalties
- Waive penalties where permitted
- Reconcile borrowing records


### Book Requests


- Request books
- View personal book requests
- Admin/librarian request management
- Approve or reject requests
- Bulk approval of book requests
- Track request status
- Monthly request statistics


### Waitlist & Reservation Management


- Join a book waitlist
- Leave a waitlist
- View personal waitlist
- View waitlist position
- Manage active waitlists
- Update waitlist priority
Technologies Used
Frontend
React
TypeScript
Vite
React Router
Axios
Recharts
Framer Motion
HTML5
CSS3
Backend
Java 17
Spring Boot 3.5.7
Spring Web
Spring Data JPA
Hibernate
Spring Security
Spring Validation
Spring Mail
JWT Authentication
Maven
Lombok
Database
MySQL
Testing
JUnit
Mockito
Spring Security Test
H2 Database for integration testing
System Architecture

The application follows a client-server architecture.

                React Frontend
                       |
                       | REST API
                       v
              Spring Boot Backend
                       |
          +------------+------------+
          |            |            |
      Controllers   Services    Security
          |            |            |
          +------------+------------+
                       |
                 Spring Data JPA
                       |
                       v
                    MySQL
## Project Structure

LMS-master/
│
├── backend/
│   │
│   ├── src/
│   │   └── main/
│   │       ├── java/
│   │       │   └── com/
│   │       │       └── infy/
│   │       │           └── lms/
│   │       │               │
│   │       │               ├── config/
│   │       │               ├── controller/
│   │       │               ├── dto/
│   │       │               ├── enums/
│   │       │               ├── exception/
│   │       │               ├── model/
│   │       │               ├── repository/
│   │       │               ├── scheduler/
│   │       │               ├── security/
│   │       │               └── service/
│   │       │
│   │       └── resources/
│   │           └── application.properties
│   │
│   ├── pom.xml
│   ├── mvnw
│   └── mvnw.cmd
│
├── frontend/
│   │
│   ├── public/
│   │   └── assets/
│   │
│   ├── src/
│   │   ├── api/
│   │   ├── assets/
│   │   ├── components/
│   │   ├── context/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── types/
│   │   ├── App.tsx
│   │   ├── App.css
│   │   └── main.tsx
│   │
│   ├── package.json
│   ├── vite.config.ts
│   └── tsconfig.json
│
└── README.md
## Backend Setup
### Requirements

Make sure the following are installed:

Java JDK 17
Maven
MySQL
Node.js and npm
Git
## Database Setup

Create a MySQL database:

CREATE DATABASE librarydb;

The Spring Boot backend connects to MySQL using the configured database connection.

Update the database configuration in:

backend/src/main/resources/application.properties

Use your own MySQL username and password.

Example:

spring.datasource.url=jdbc:mysql://localhost:3306/librarydb
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD

Do not commit real database passwords or email credentials to GitHub.

## Backend Configuration

The backend runs on:

http://localhost:8081

The application uses:

Spring Data JPA
MySQL
Spring Security
JWT authentication
Spring Mail
File upload support

Maximum file upload size:

10 MB
Run the Backend

Navigate to the backend directory:

cd backend

Using Maven Wrapper:

Windows
mvnw.cmd spring-boot:run
Linux / macOS
./mvnw spring-boot:run

Or using Maven:

mvn spring-boot:run

The backend will start at:

http://localhost:8081
Frontend Setup

## Navigate to the frontend directory:

cd frontend

## Install dependencies:

npm install

Start the development server:

npm run dev

The Vite development server will display the local URL in the terminal.

The frontend uses the backend API configured through:

VITE_API_BASE

## Example:

VITE_API_BASE=http://localhost:8081
Frontend Commands
Start Development Server
npm run dev
Build the Project
npm run build
Run ESLint
npm run lint
Preview Production Build
npm run preview
## Authentication Flow

## The application uses JWT-based authentication.

User
 |
 v
Register / Login
 |
 v
Spring Boot Authentication API
 |
 v
JWT Token
 |
 v
Frontend Authentication Context
 |
 v
Protected Routes
 |
 v
Authorized Application Features

Protected routes are handled on the frontend using route guards, while backend APIs are secured using Spring Security.

## Main REST API Modules

### Authentication

POST /api/auth/register
POST /api/auth/login
POST /api/auth/forgot-password
POST /api/auth/reset-password
GET  /api/auth/profile
PUT  /api/auth/profile
GET  /api/auth/verify

### Books
POST   /api/books
GET    /api/books
GET    /api/books/search
GET    /api/books/{id}
PUT    /api/books/{id}
POST   /api/books/{id}/availability
DELETE /api/books/{id}

### Borrowing
POST /api/borrow
POST /api/return
GET  /api/members/{memberId}/history
GET  /api/borrow
GET  /api/borrow/overdue

### Penalties
POST /api/borrow/{borrowId}/penalty/compute
POST /api/borrow/{borrowId}/penalty/pay
GET  /api/members/{memberId}/penalties
GET  /api/members/{memberId}/penalties/pending
GET  /api/penalties/pending
GET  /api/penalties

### Book Requests
POST /api/issue-requests
GET  /api/issue-requests/my
GET  /api/issue-requests
PATCH /api/issue-requests/{id}/approve
PATCH /api/issue-requests/{id}/reject
POST /api/issue-requests/bulk-approve

### Acquisition Requests
POST  /api/acquisition-requests
GET   /api/acquisition-requests/mine
GET   /api/acquisition-requests
PATCH /api/acquisition-requests/{id}/approve
PATCH /api/acquisition-requests/{id}/reject

### Waitlist
POST   /api/waitlist/join/{bookId}
DELETE /api/waitlist/leave/{bookId}
GET    /api/waitlist/my-waitlist
GET    /api/waitlist/position/{bookId}
GET    /api/waitlist/book/{bookId}
GET    /api/waitlist/all
PUT    /api/waitlist/priority/{waitlistId}
GET    /api/waitlist/reservations

### Subscriptions
GET  /api/subscriptions/status
POST /api/subscriptions/activate
POST /api/subscriptions/extend
GET  /api/subscriptions/packages

### Recommendations
GET /api/recommendations/{userId}
GET /api/recommendations/analytics/popular-books
GET /api/recommendations/analytics/category-trends
GET /api/recommendations/analytics/popular-books/timeseries
GET /api/recommendations/analytics/popular-books/export

### Reports
GET /api/reports/download

## Main Frontend Pages

The React frontend contains pages for:

General
Landing Page
About
Contact
Login
Registration
Forgot Password
Reset Password
Student / User
Student Dashboard
Student Home
Student Profile
Book Catalog
Borrowed Books
Returns
Book Requests
Fines
Membership Requests
Pro Membership
Waitlist
Librarian
Library Dashboard
Manage Books
Add Books
Issue Books
Returns
Members
Membership Requests
Penalties
Reports
Admin
Admin Dashboard
User Management
Books Management
Books Catalog
Acquisition Requests
Requests Management
Returns
Penalties
Waitlist Management
Reports
AI Analytics
System Settings
Automated Background Tasks

The backend includes scheduled services for library operations such as:

Overdue processing
Subscription expiry handling
Waitlist management
Reservation cleanup

These schedulers help automate recurring library management operations.

Email Services

The application includes email functionality for account-related and library-related workflows.

Email functionality includes:

Account verification
Password reset
Library notifications
Request-related communication
Subscription-related communication

Email configuration should be provided through environment variables or secure configuration rather than committing credentials to the repository.

## Security

The application includes:

Spring Security
JWT authentication
Token authentication filter
Role-based authorization
Protected frontend routes
Password reset flow
Email verification
Global exception handling

Sensitive configuration such as:

Database passwords
Email passwords
JWT secrets
API credentials

should never be committed to GitHub.

Error Handling

The backend includes centralized exception handling with custom exceptions for situations such as:

Bad requests
Unauthorized access
Resource not found
Book not found
Duplicate ISBN
Out-of-stock books
Borrowing errors
Conflicts
Internal server errors

## Development Workflow

User
 ↓
React Frontend
 ↓
Axios API Client
 ↓
Spring Boot REST Controller
 ↓
Service Layer
 ↓
Repository Layer
 ↓
Hibernate / JPA
 ↓
MySQL Database

## Running the Complete Project

Start MySQL first.

Then start the backend:

cd backend
mvnw.cmd spring-boot:run

Open another terminal and start the frontend:

cd frontend
npm install
npm run dev

Then open the Vite URL displayed in the terminal.

## Important Notes
The project is configured for local development.
MySQL must be running before starting the backend.
The frontend must be configured with the correct backend API URL.
Email functionality requires valid SMTP configuration.
Do not commit .env files or passwords containing sensitive credentials.
Do not commit the node_modules directory to GitHub.
Do not commit generated build files such as dist or Maven target directories.

## Future Enhancements

Possible future improvements include:

Cloud deployment
Advanced recommendation algorithms
More detailed analytics
Mobile application
Online payment gateway integration
Enhanced notification system
Advanced search and filtering
Automated database backups
Containerized deployment using Docker

## Author

Abhijna R S

Library Management System developed as an internship full-stack project demonstrating:

Java
Spring Boot
Spring Security
REST APIs
JWT Authentication
React
TypeScript
MySQL
Full-Stack Web Development
