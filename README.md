
# Job-Application-Web-App

## Job Application Management System

A PHP-based web application that provides a platform for applicants to browse and apply for jobs and recruiters to post and manage job opportunities. The system uses MySQL for storing user, job, and application data and provides role-based access for recruiters and applicants.

## Features

- User registration and login
- Role-based access for Recruiters and Applicants
- Session-based authentication
- Applicant dashboard
- Recruiter dashboard
- Job posting
- Job editing and deletion
- Browse available jobs
- Apply for jobs
- CV upload functionality
- View submitted CVs
- Track application status
- Shortlist applicants
- Select applicants
- Reject applications
- Job status management
- MySQL database integration
- Logout functionality

## Technologies Used

- PHP
- MySQL
- HTML
- CSS
- XAMPP
- phpMyAdmin

## Project Structure
```
Job-Application-Web-App/
│
├── home.html
├── login.html
├── login.php
├── register.html
├── register.php
│
├── applicant_dashboard.php
├── apply_job.php
├── apply_job_form.php
│
├── recruiter_dashboard.php
├── create_job.php
├── edit_job.php
├── delete_job.php
├── update_status.php
│
├── logout.php
├── db_connection.php
├── styles.css
│
├── our_DB.txt
├── CV.txt
│
├── uploads/
│   └── CV files
│
└── README.md
```
## How It Works
```
User Registration
       ↓
     Login
       ↓
   Role Check
       ↓
 ┌─────┴─────┐
 ↓           ↓
Applicant   Recruiter
 ↓           ↓
Browse      Post Jobs
Jobs        ↓
 ↓          Manage Jobs
Apply       ↓
 ↓          View Applicants
Upload CV   ↓
 ↓          Update Status
Track Status
```
The application uses session-based authentication to identify the logged-in user and provide access according to the user's role.

## User Roles

### Applicant

Applicants can:

- Register and login
- View available jobs
- View job descriptions
- Check required skills
- View location and salary
- Apply for jobs
- Upload CV
- View submitted applications
- Track application status
- Logout

### Recruiter

Recruiters can:

- Register and login
- Create job posts
- Specify job description
- Add required skills
- Add job location
- Add salary
- Set application deadline
- View their job posts
- Edit job posts
- Delete job posts
- View applicants
- View applicant CVs
- Shortlist applicants
- Select applicants
- Reject applicants
- Logout

## Database

The application uses MySQL as the database.

Database name:

jp

Main tables:

users
jobs
applications

### Users Table

Stores user information including:

- Username
- Name
- Email
- Password
- Role
- Account creation date

Supported roles:

recruiter
applicant

### Jobs Table

Stores job information including:

- Job title
- Job description
- Required skills
- Location
- Salary
- Application deadline
- Job status
- Recruiter ID
- Creation date

Job status:

active
closed

### Applications Table

Stores application information including:

- Job ID
- Applicant ID
- CV path
- Application status
- Applicant name
- Email
- Phone
- Application date

Application status:

pending
shortlisted
rejected
selected

## Database Relationship
```
Users
  │
  ├───────────────┐
  ↓               ↓
Jobs          Applications
  │               ↑
  └───────────────┘
```
A recruiter can create multiple jobs, and applicants can submit applications for available jobs.

## Installation

### Requirements

Install the following:

- XAMPP
- PHP
- MySQL
- phpMyAdmin
- Web Browser

## Database Setup

1. Start Apache and MySQL from XAMPP.
2. Open phpMyAdmin.
3. Create a database named:

jp

4. Open the our_DB.txt file.
5. Execute the SQL commands in phpMyAdmin.
6. Verify that the required tables are created.

## Database Configuration

Open:

db_connection.php

Configure the MySQL connection according to your local XAMPP setup.

Example:

$servername = "localhost";
$username = "root";
$password = "";
$dbname = "jp";

## Run the Project

Place the project folder inside the XAMPP htdocs directory:

C:\xampp\htdocs\Job-Application-Web-App

Start:

Apache
MySQL

Then open the application in a browser:

http://localhost/Job-Application-Web-App/home.html

## Usage

### Applicant Workflow

1. Register as an Applicant.
2. Login using your credentials.
3. View available jobs.
4. Select a job and click Apply.
5. Upload your CV.
6. Submit the application.
7. View your applications from the Applicant Dashboard.
8. Track the application status.

### Recruiter Workflow

1. Register as a Recruiter.
2. Login using your credentials.
3. Open the Recruiter Dashboard.
4. Create a new job.
5. Enter job title, description, skills, location, salary, and deadline.
6. View posted jobs.
7. Edit or delete job posts when required.
8. View applicants for each job.
9. View applicant CVs.
10. Update application status to:

Shortlisted
Selected
Rejected

## Application Workflow
```
Recruiter Creates Job
        ↓
Job Appears in Applicant Dashboard
        ↓
Applicant Selects Job
        ↓
Applicant Uploads CV
        ↓
Application Stored in MySQL
        ↓
Recruiter Views Application
        ↓
Recruiter Reviews CV
        ↓
Application Status Updated
        ↓
Pending / Shortlisted / Selected / Rejected
```
## CV Upload

Applicants can upload their CV while applying for a job.

Uploaded CV files are stored inside:

uploads/

Each uploaded CV is given a unique file name to avoid conflicts.

## Authentication

The application uses PHP sessions for authentication and role management.
```
Login
  ↓
Session Created
  ↓
Role Identified
  ↓
Applicant → Applicant Dashboard
Recruiter → Recruiter Dashboard
```
Unauthorized users are redirected to the login page.

## Author

This project is developed for internship purposes to demonstrate the implementation of a database-driven Job Application Web Application using PHP, MySQL, HTML, and CSS.

Author: Abhijna R S
```
