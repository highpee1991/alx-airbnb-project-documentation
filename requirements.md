# Airbnb Clone – Backend Feature Requirements

## 1. User Authentication

### 🔗 Endpoints
- `POST /api/register` – Register a new user
- `POST /api/login` – Login user and return JWT token

### 📥 Input
- `first_name`: string, required
- `last_name`: string, required
- `email`: string, required, must be unique
- `password`: string, required, min 8 characters

### 📤 Output
- Success: `{ message: "User registered successfully", user_id: UUID }`
- Error: `{ error: "Email already exists" }`

### ✅ Validation Rules
- Password must be at least 8 characters
- Email must be valid format
- Unique email

### ⚙️ Performance Criteria
- Response time < 1 second for registration
- Password must be hashed using bcrypt before saving

---

## 2. Property Management

### 🔗 Endpoints
- `POST /api/properties` – Add new listing
- `GET /api/properties/{id}` – Get property by ID
- `PUT /api/properties/{id}` – Update property
- `DELETE /api/properties/{id}` – Delete property

### 📥 Input
- `host_id`: UUID, required
- `description`: string, required
- `location`: string, required
- `price_per_night`: decimal, required

### 📤 Output
- Success: `{ message: "Property created", property_id: UUID }`
- Error: `{ error: "Missing required fields" }`

### ✅ Validation Rules
- Price must be greater than zero
- Host must be a valid user (foreign key exists)
- Location must not be empty

### ⚙️ Performance Criteria
- Query results paginated for large data
- Indexing on `host_id` and `location` for faster filtering

---

## 3. Booking System

### 🔗 Endpoints
- `POST /api/bookings` – Create booking
- `GET /api/bookings/{id}` – Get booking details

### 📥 Input
- `user_id`: UUID, required
- `property_id`: UUID, required
- `start_date`: datetime, required
- `end_date`: datetime, required

### 📤 Output
- Success: `{ message: "Booking successful", booking_id: UUID }`
- Error: `{ error: "Double booking detected" }`

### ✅ Validation Rules
- `end_date` must be after `start_date`
- No overlapping bookings for same property
- Property and user must exist

### ⚙️ Performance Criteria
- Ensure date check logic is optimized to prevent slow queries
- DB index on `property_id` and `start_date`

---

