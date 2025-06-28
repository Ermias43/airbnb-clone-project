# Entity Relationship Diagram for ALX Airbnb Database

## í³Œ Entities & Attributes

### í·‘â€í²¼ User
- `user_id` (PK, UUID, Indexed)
- `first_name` (VARCHAR, NOT NULL)
- `last_name` (VARCHAR, NOT NULL)
- `email` (VARCHAR, UNIQUE, NOT NULL)
- `password_hash` (VARCHAR, NOT NULL)
- `phone_number` (VARCHAR, NULL)
- `role` (ENUM: guest, host, admin, NOT NULL)
- `created_at` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)

### í¿  Property
- `property_id` (PK, UUID, Indexed)
- `host_id` (FK â†’ User.user_id)
- `name` (VARCHAR, NOT NULL)
- `description` (TEXT, NOT NULL)
- `location` (VARCHAR, NOT NULL)
- `pricepernight` (DECIMAL, NOT NULL)
- `created_at` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)
- `updated_at` (TIMESTAMP, ON UPDATE CURRENT_TIMESTAMP)

### í³… Booking
- `booking_id` (PK, UUID, Indexed)
- `property_id` (FK â†’ Property.property_id)
- `user_id` (FK â†’ User.user_id)
- `start_date` (DATE, NOT NULL)
- `end_date` (DATE, NOT NULL)
- `total_price` (DECIMAL, NOT NULL)
- `status` (ENUM: pending, confirmed, canceled, NOT NULL)
- `created_at` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)

### í²³ Payment
- `payment_id` (PK, UUID, Indexed)
- `booking_id` (FK â†’ Booking.booking_id)
- `amount` (DECIMAL, NOT NULL)
- `payment_date` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)
- `payment_method` (ENUM: credit_card, paypal, stripe, NOT NULL)

### í²¬ Review
- `review_id` (PK, UUID, Indexed)
- `property_id` (FK â†’ Property.property_id)
- `user_id` (FK â†’ User.user_id)
- `rating` (INTEGER, CHECK rating BETWEEN 1 AND 5, NOT NULL)
- `comment` (TEXT, NOT NULL)
- `created_at` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)

### âœ‰ï¸ Message
- `message_id` (PK, UUID, Indexed)
- `sender_id` (FK â†’ User.user_id)
- `recipient_id` (FK â†’ User.user_id)
- `message_body` (TEXT, NOT NULL)
- `sent_at` (TIMESTAMP, DEFAULT CURRENT_TIMESTAMP)

---

## í´— Relationships

| Relationship | Type | Description |
|--------------|------|-------------|
| **User â†” Property** | 1:N | One user (host) can own many properties |
| **User â†” Booking** | 1:N | One user can make many bookings |
| **Property â†” Booking** | 1:N | One property can be booked many times |
| **Booking â†” Payment** | 1:1 | One booking has one payment |
| **User â†” Review** | 1:N | One user can write many reviews |
| **Property â†” Review** | 1:N | One property can have many reviews |
| **User â†” Message (sender/recipient)** | N:N | Users can send and receive messages to/from each other |

---

## í³Š ER Diagram Visual

Embed your ER diagram image or link it:

![ER Diagram](./airbnb-erd.png)

> If you havenâ€™t created the diagram yet, use tools like [Draw.io](https://app.diagrams.net/), Lucidchart, or dbdiagram.io to design it and export it as `airbnb-erd.png`.

---

## âœ… Notes

- Use `UUID` for all primary keys to ensure uniqueness.
- Ensure ENUMs and CHECK constraints enforce business logic.
- Add indexes to FK fields for performance optimization.
- Normalize the schema and avoid redundant data.


