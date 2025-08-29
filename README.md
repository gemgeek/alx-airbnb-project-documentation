# Features and Functionalities – Airbnb Clone Backend

This document outlines the key features and functionalities of the Airbnb Clone backend project.  
The system is designed to support users, property management, bookings, payments, reviews, and admin operations.

## Core Features
1. **User Management**
   - Registration & Login (with JWT & OAuth options)
   - Profile management (photo, contact, preferences)

2. **Property Listings**
   - Add/Edit/Delete listings
   - Manage availability, price, and amenities

3. **Search & Filtering**
   - By location, price, guest count, and amenities
   - Pagination for large datasets

4. **Booking System**
   - Create, cancel, and track bookings
   - Prevent double booking with date validation

5. **Payments**
   - Secure payments (Stripe, PayPal)
   - Multi-currency support
   - Automatic payouts to hosts

6. **Reviews & Ratings**
   - Guests leave reviews, hosts respond
   - Linked to valid bookings

7. **Notifications**
   - Email and in-app alerts for confirmations, cancellations, payments

8. **Admin Dashboard**
   - Manage users, listings, bookings, and payments

## Technical & Non-Functional Requirements
- Database: PostgreSQL/MySQL
- RESTful APIs with proper HTTP methods
- Authentication & Authorization (JWT, RBAC)
- File storage for images
- Scalability, Security, Caching, and Testing

## Diagram
![Features Diagram](./features.png.png)
