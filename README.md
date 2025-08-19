# Airbnb Clone

## Overview
The Airbnb Clone Project is a full-stack application that simulates a real booking platform. It emphasizes backend systems, database design, API development, and security, giving learners hands-on experience with scalable architectures and team collaboration.

## Team Roles
- **Backend Developer**: Responsible for the server-side logic, database design, and API development.
- **Frontend Developer**: Handles the user interface and user experience.
- **Database Administrator**: Manages the database and ensures data integrity.
- **DevOps Engineer**: Sets up and manages deployment pipelines, CI/CD processes, and cloud infrastructure.
- **QA Engineer (Tester)**: Ensures software quality by writing and executing test cases, identifying bugs, and validating that features work as intended
- **Project Manager**: Oversees the project timeline, coordinates collaboration between roles, and ensures goals are met
- **UI/UX Designer**:Crafts intuitive and appealing user experiences, designs wireframes, and ensures accessibility and consistency across the application.
## Technology Stack
- **Django**: A high-level Python web framework used to build RESTful APIs.
- **Django REST Framework (DRF)**: An extension of Django for building powerful RESTful APIs
- **PostgreSQL**: A relational database system for structured data storage and queries.
- **Redis**: An in-memory data store used for caching and managing background task queues.
- **GraphQL**: A query language for APIs that allows clients to request exactly the data they
- **Celery**: A distributed task queue for handling asynchronous and scheduled jobs.

- **Docker**: A containerization platform that simplifies deployment and ensures consistency across environments.

- **CI/CD Pipelines**: Automated workflows for testing, building, and deploying code, ensuring reliable and efficient delivery.

## Database Design
The project database is structured to support a booking platform similar to Airbnb. Below are the key entities, their important fields, and relationships:

1.**Users**

- Fields:
    - id (Primary Key)
    - name (Full name)
    - email (Unique, used for login)
    - password_hash (Encrypted password)
    - role (guest, host, or admin)

- Relationships:
    - A user can list multiple properties.
    - A user can make multiple bookings.
    - A user can write multiple reviews.
  
2. **Properties**

- Fields:

    - id (Primary Key)
    - title (Property name/short description)
    - description (Detailed info)
    - location (City, Country, Coordinates)
    - price_per_night

- Relationships:
    - A property belongs to one user (host).
    - A property can have many bookings.
    - A property can receive many reviews.
  
3. **Bookings**
- Fields:
    - id (Primary Key)
    - user_id (Guest who made the booking)
    - property_id (Property being booked)
    - check_in_date
    - check_out_date
    -status (pending, confirmed, cancelled)
- Relationships:
    - A booking belongs to one user (guest).
    - A booking belongs to one property.
    - A booking may have one payment.
  

4. **Reviews**

- Fields:

    - id (Primary Key)
    - user_id (Author of the review)
    - property_id (Reviewed property)
    - rating (1–5 scale)
    - comment
- Relationships:

    - A review belongs to one user (guest).
    - A review belongs to one property.

5. **Payments**
- Fields:
    - id (Primary Key)
    - booking_id (Linked booking)
    - amount
    - payment_method (credit card, PayPal, etc.)
    - status (pending, completed, failed)
- Relationships:

    - A payment is tied to exactly one booking.