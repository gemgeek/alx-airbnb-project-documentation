# Backend Requirement Specifications

This document outlines the **technical and functional requirements** for key backend features of the Airbnb Clone project.

---

## 1. User Authentication

### Description
Provides secure login and registration for guests and hosts.

### Functional Requirements
- Users can register with email and password.
- OAuth login via Google and Facebook.
- JWT-based authentication for secure sessions.
- Role-based access (Guest, Host, Admin).

### API Endpoints
- `POST /api/v1/auth/register` → Register new user  
- `POST /api/v1/auth/login` → Login user and return token  
- `GET /api/v1/auth/profile` → Retrieve user profile (authenticated)  

### Input/Output
- **Input:** JSON `{ "email": "user@example.com", "password": "123456" }`  
- **Output:** JSON `{ "token": "jwt-token", "userId": 1 }`  

### Validation Rules
- Email must be unique and valid format.  
- Password must be at least 8 characters.  

### Performance Criteria
- Response time < 300ms for login.  
- Must handle 1000 concurrent logins without failure.  

---

## 2. Property Management

### Description
Allows hosts to add, update, and manage property listings.

### Functional Requirements
- Hosts can create property listings with details.  
- Hosts can edit or delete their own listings.  
- Guests can view and search listings.  

### API Endpoints
- `POST /api/v1/properties` → Create new property  
- `GET /api/v1/properties` → Retrieve all properties (with filters)  
- `GET /api/v1/properties/:id` → Retrieve property details  
- `PUT /api/v1/properties/:id` → Update property  
- `DELETE /api/v1/properties/:id` → Delete property  

### Input/Output
- **Input:** JSON `{ "title": "Cozy Apartment", "price": 100, "location": "Accra" }`  
- **Output:** JSON `{ "id": 101, "title": "Cozy Apartment", "status": "active" }`  

### Validation Rules
- Title and location are required.  
- Price must be > 0.  

### Performance Criteria
- Listing retrieval must support pagination.  
- Search query results in < 500ms.  

---

## 3. Booking System

### Description
Enables guests to book available properties and hosts to manage bookings.

### Functional Requirements
- Guests can book properties for specific dates.  
- Prevent double-bookings with date validation.  
- Guests and hosts can cancel bookings.  
- Track booking statuses (pending, confirmed, canceled).  

### API Endpoints
- `POST /api/v1/bookings` → Create booking  
- `GET /api/v1/bookings/:id` → Retrieve booking details  
- `DELETE /api/v1/bookings/:id` → Cancel booking  

### Input/Output
- **Input:** JSON `{ "propertyId": 101, "guestId": 1, "startDate": "2025-09-01", "endDate": "2025-09-05" }`  
- **Output:** JSON `{ "id": 202, "status": "confirmed" }`  

### Validation Rules
- Dates must not overlap with existing bookings.  
- Start date must be before end date.  

### Performance Criteria
- System should confirm booking in < 400ms.  
- Must handle at least 500 concurrent bookings.  

---