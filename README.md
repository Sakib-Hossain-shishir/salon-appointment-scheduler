# Salon Appointment Scheduler

This is a simple Bash-based salon appointment scheduling system that interacts with a PostgreSQL database. Users can view available services, provide their contact information, and schedule appointments. The project is designed to meet freeCodeCamp’s Salon Appointment Scheduler project requirements.

---

## Features

- Lists all available salon services with a numbered menu.
- Prompts users for:
  - Service selection
  - Phone number
  - Customer name (if new)
  - Appointment time
- Automatically creates new customers if their phone number doesn’t exist in the database.
- Stores appointments in a PostgreSQL database with proper foreign key relationships.
- Displays a confirmation message after successfully booking an appointment.

---

## Database Schema

The project uses a PostgreSQL database named `salon` with the following tables:

### `services`
| Column      | Type        | Notes               |
|-------------|------------|-------------------|
| service_id  | SERIAL PK  | Primary key        |
| name        | VARCHAR    | Name of service    |

### `customers`
| Column       | Type       | Notes                           |
|--------------|-----------|--------------------------------|
| customer_id  | SERIAL PK | Primary key                     |
| name         | VARCHAR   | Customer name                   |
| phone        | VARCHAR   | Unique phone number             |

### `appointments`
| Column        | Type       | Notes                                           |
|---------------|-----------|------------------------------------------------|
| appointment_id| SERIAL PK | Primary key                                    |
| customer_id   | INT       | Foreign key referencing `customers(customer_id)` |
| service_id    | INT       | Foreign key referencing `services(service_id)`  |
| time          | VARCHAR   | Appointment time                                |

---


