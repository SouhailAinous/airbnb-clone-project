# Airbnb Clone Project

## Overview
This is a full-stack Airbnb clone built as part of a backend engineering program. The goal is to simulate a real-world scalable booking platform and learn backend development through hands-on experience.

## Project Goals
- Design a scalable backend architecture
- Develop secure and RESTful APIs
- Build and connect a relational database (MySQL)
- Implement CI/CD pipelines for deployment
- Learn team collaboration and documentation practices

## Tech Stack
- Python
- Django
- MySQL
- Django REST Framework
- Docker
- GitHub Actions
- GraphQL 
## Team Roles

Below are the typical roles involved in a backend development project like the Airbnb Clone. These roles help ensure collaboration, structure, and clear responsibilities.

### 🔧 Backend Developer
Responsible for writing the server-side logic of the application. Builds and maintains the APIs, handles data processing, and ensures proper communication with the database.

### 🗄️ Database Administrator (DBA)
Designs and manages the database structure. Ensures data is stored securely, efficiently, and is always accessible. Works with the backend developer to create the data models.

### 🔐 Security Engineer
Implements security protocols like authentication, authorization, and protection against common threats (e.g., SQL injection, XSS). Ensures data privacy and secure API transactions.

### 🚀 DevOps Engineer
Handles deployment and CI/CD pipelines. Uses tools like Docker and GitHub Actions to automate testing, building, and deploying the app to production.

### 📚 Technical Writer / Documentation Lead
Writes clean documentation for other developers and users. Maintains the README, API docs, and onboarding instructions.

### 🧑‍💻 Team Lead / Project Manager
Coordinates the team, sets deadlines, assigns tasks, and ensures that the team follows best practices. Also communicates between the team and external stakeholders (if any).
## Technology Stack

Here are the main technologies used in this project and their purposes:

### 🐍 Django
A high-level Python web framework used to build backend services quickly. It handles routing, database models, authentication, and more.

### 🛢️ MySQL
A relational database system used to store structured data like users, listings, and bookings. Django connects to this to fetch or save data.

### 🔌 Django REST Framework (DRF)
An extension of Django that makes it easier to build RESTful APIs. It helps serialize data and create CRUD operations efficiently.

### 📦 Docker
A containerization tool that packages your app and its environment into isolated units, making it easier to develop and deploy.

### 🧪 GitHub Actions
A CI/CD tool that automates testing, building, and deploying your code whenever you push updates.

### 🔐 JWT (or other auth method)
Used for user authentication and session management. Ensures only authorized users can access certain resources.

### 🧬 GraphQL *(if included)*
An alternative to REST APIs that lets clients request only the data they need. It improves flexibility and reduces over-fetching.

### 📝 Markdown
Used to write documentation like this README. It’s a lightweight syntax for formatting plain text.

### 🧠 Git & GitHub
Version control tools used to track changes, collaborate with a team, and store code safely online.
## 🗄️ Database Design

Here are the main entities (tables) used in the Airbnb Clone project, along with their key fields and relationships:

### 👤 Users
Stores information about people using the platform.
- `id`: Unique identifier
- `name`: Full name
- `email`: Email address
- `password_hash`: Encrypted password
- `is_host`: Boolean to check if user is a host

### 🏠 Properties
Represents the listings available for booking.
- `id`: Unique identifier
- `owner_id`: Foreign key to Users (who owns this property)
- `title`: Name of the listing
- `location`: City and address
- `price_per_night`: Cost of booking per night

### 📅 Bookings
Tracks who booked which property and when.
- `id`: Unique identifier
- `user_id`: Foreign key to Users
- `property_id`: Foreign key to Properties
- `start_date`: When the booking starts
- `end_date`: When the booking ends
- `total_price`: Calculated cost

### 💬 Reviews
Allows users to leave feedback on properties.
- `id`: Unique identifier
- `user_id`: Foreign key to Users
- `property_id`: Foreign key to Properties
- `rating`: Numerical score (e.g., 1 to 5)
- `comment`: Text feedback

### 💳 Payments
Stores transaction data for bookings.
- `id`: Unique identifier
- `booking_id`: Foreign key to Bookings
- `amount`: Total amount paid
- `status`: Paid / Failed / Refunded
- `payment_method`: e.g., credit card, PayPal

---

### 🔗 Entity Relationships

- A **User** can create multiple **Properties** (1-to-many)
- A **Property** can have multiple **Bookings** (1-to-many)
- A **Booking** belongs to one **User** and one **Property**
- A **User** can leave multiple **Reviews** for different **Properties**
- A **Payment** is linked to one **Booking**
