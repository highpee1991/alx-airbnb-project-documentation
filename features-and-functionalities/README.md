# alx-airbnb-project-documentation
# Airbnb Clone – Roles & Responsibilities

This backend system supports three main user roles: **Guest**, **Host**, and **Admin**. Each role has different permissions and responsibilities within the platform.

## 👤 Guest
Guests are users who sign up to explore and book properties.

### Guest Capabilities:
- Register/Login
- Browse property listings
- Search/filter properties by location, price, and amenities
- Book available properties
- Cancel bookings (within policy)
- Make secure payments
- Leave reviews and ratings for properties
- Chat with hosts

---

## 🏠 Host
Hosts are users who list and manage properties to be rented out to guests.

### Host Capabilities:
- Register as a host or upgrade role
- Create, update, or delete property listings
- Upload images and add amenities
- View bookings made on their properties
- Communicate with guests through messaging
- Respond to guest reviews
- Track booking status and availability

---

## 🛡️ Admin
Admins are system-level users responsible for maintaining and moderating the platform.

### Admin Capabilities:
- View all users (guests and hosts)
- Suspend or delete users violating policies
- Monitor and remove inappropriate property listings
- View and manage bookings system-wide
- Handle payment disputes or refunds
- Moderate or remove inappropriate reviews
- Access the admin dashboard with platform metrics

---

## 🧠 Role Management
Roles are defined in the `users` table and can be one of:
- `guest`
- `host`
- `admin`

Role-based access control (RBAC) is enforced to ensure each user only accesses features permitted by their role.

---
