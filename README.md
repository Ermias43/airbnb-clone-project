# airbnb-clone-project
👥 Team Roles
Below are the key roles and responsibilities involved in this project:

## 🔧 Backend Developer
Builds the server-side logic and API endpoints using frameworks like Django or Node.js. Responsible for:

 - [x] Implementing RESTful APIs

 - [x] Managing authentication & authorization

 - [x] Ensuring secure, scalable backend logic

## 🗄️ Database Administrator (DBA)
Designs and manages the data layer of the application. Responsibilities include:

-  [x] Setting up and optimizing databases (e.g., PostgreSQL, MySQL)

-  [x] Ensuring data integrity, backup, and recovery

-  [x] Performance tuning of queries

## 🎨 Frontend Developer
Creates the user-facing part of the application. Responsible for:

-  [x] Building responsive UI with HTML, CSS, JS, or frameworks like React/Next.js

-  [x] Integrating with backend APIs

-  [x] Ensuring an optimal user experience

## 🧠 Project Manager
Oversees project planning and delivery. Duties include:

-  [x] Assigning tasks and tracking progress

-  [x] Facilitating team communication

-  [x] Ensuring timely delivery of milestones

## 🧪 QA Engineer (Quality Assurance)
Ensures the product meets quality standards through:

-  [x] Writing and executing manual/automated tests

-  [x] Detecting bugs and performance issues

-  [x] Validating feature requirements

## ☁️ DevOps Engineer
Handles deployment and infrastructure. Key responsibilities:

-  [x] Managing CI/CD pipelines

-  [x] Cloud configuration and resource scaling

-  [x] Monitoring and system troubleshooting

# 🛠️ Technology Stack
A breakdown of the core technologies used in this project and their specific purposes:

### 🐍 Django
A high-level Python web framework used to build fast, secure, and scalable web applications.
- [x]  Used for building the backend logic and creating RESTful APIs.

### 🐘 PostgreSQL
A powerful, open-source relational database system.
- [x] Used to store and manage structured application data securely and efficiently.

### 🔁 GraphQL
A query language for APIs that provides a more efficient, powerful, and flexible alternative to REST.
- [x] Used to enable precise data fetching for client applications.

### 🎨 Bootstrap
A responsive CSS framework.
- [x] Used for creating a mobile-friendly and visually consistent frontend design.

### 🌐 HTML, CSS & JavaScript
The foundational technologies of the web.
- [x] Used to structure (HTML), style (CSS), and add interactivity (JavaScript) to the frontend.

### 🌍 Git & GitHub
Version control tools used for tracking changes and collaborating on code.
- [x] GitHub hosts the project repository and supports team collaboration.


🧩 Database Design
Below is an overview of the main database entities and how they relate to each other in the project.

## 📘 Entities and Fields

### 👤 Users

| Field    | Description                      |
|----------|---------------------------------|
| id       | Unique identifier for the user  |
| name     | Full name of the user           |
| email    | Email address (unique)          |
| password | Encrypted password              |
| role     | Indicates if user is guest or host |


### 🏠 Properties

| Field         | Description                                |
|---------------|--------------------------------------------|
| `id`          | Unique identifier for the property         |
| `title`       | Name/title of the property                 |
| `description` | Detailed description                       |
| `location`    | Physical address or coordinates            |
| `owner_id`    | References the user who owns the property  |


### 📅 Bookings

| Field         | Description                          |
|---------------|--------------------------------------|
| `id`          | Unique identifier for the booking    |
| `user_id`     | The user who made the booking        |
| `property_id` | The property being booked            |
| `start_date`  | Booking start date                   |
| `end_date`    | Booking end date                     |


### ✍️ Reviews

| Field         | Description                          |
|---------------|--------------------------------------|
| `id`          | Unique identifier for the review     |
| `user_id`     | The user who wrote the review        |
| `property_id` | The property being reviewed          |
| `rating`      | Numeric rating (e.g., 1–5 stars)     |
| `comment`     | Optional text feedback               |


### 💳 Payments

| Field       | Description                                 |
|-------------|---------------------------------------------|
| `id`        | Unique identifier for the payment           |
| `booking_id`| References the related booking              |
| `amount`    | Total amount paid                           |
| `status`    | Status of the payment (e.g., paid, failed)  |
| `method`    | Payment method used                         |



### 🔗 Entity Relationships
- [x] A User can own multiple Properties.

- [x] A Property can have many Bookings and Reviews.

- [x] A Booking is linked to one User and one Property.

- [x] A Review is written by a User for a Property.

- [x] A Payment is made for one Booking.

## Feature Breakdown

### User Management
This feature allows users to register, log in, and manage their profiles securely. It supports different user roles such as guests and hosts, enabling personalized access and actions based on the role.

### Property Management
Hosts can list and manage their properties through this feature. It allows adding property details, updating availability, and maintaining property information, making it easy for guests to browse and select accommodations.

### Booking System
The booking system enables guests to book properties for specific dates. It handles availability checks, booking confirmation, and stores booking history, providing a seamless reservation experience for users.

## API Security

To ensure the backend APIs are secure and reliable, the project implements several key security measures:

- **Authentication:** Verifies the identity of users before allowing access to protected resources. This prevents unauthorized users from accessing sensitive data or actions.
  
- **Authorization:** Controls what authenticated users can do based on their roles (e.g., guest or host). This ensures users only access or modify data they have permission for, protecting both user data and system integrity.
  
- **Rate Limiting:** Limits the number of API requests a user or IP can make within a time frame. This protects the system from abuse, such as denial-of-service attacks, and maintains service availability for legitimate users.

Security is critical in this project because it protects sensitive user information such as personal details and payment data, preserves trust, and prevents malicious activities that could disrupt service or cause data breaches.


