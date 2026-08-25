# Smart Clinic Management System — Database Schema Design

## 1. Overview

The Smart Clinic Management System needs to manage structured data such as patients, doctors, appointments, and administrators. This structured data will be stored in a MySQL relational database.

The system also needs to manage flexible document-based data such as prescriptions. MongoDB will be used for this type of data because prescriptions can contain different numbers of medicines and nested information.

Therefore, the system uses a hybrid database approach:

- **MySQL** — for structured and relational data.
- **MongoDB** — for flexible, document-based data.

---

# 2. MySQL Database Design

The MySQL database will contain the following tables:

1. `patients`
2. `doctors`
3. `appointments`
4. `admin`

These tables contain structured data and use relationships through primary and foreign keys.

---

## 2.1 Patients Table

The `patients` table stores information about patients registered in the clinic.

| Column Name | Data Type | Key | Constraints | Description |
|---|---|---|---|---|
| patient_id | BIGINT | PK | NOT NULL, AUTO_INCREMENT | Unique patient identifier |
| first_name | VARCHAR(100) | | NOT NULL | Patient first name |
| last_name | VARCHAR(100) | | NOT NULL | Patient last name |
| email | VARCHAR(150) | | NOT NULL, UNIQUE | Patient email address |
| phone | VARCHAR(20) | | NOT NULL, UNIQUE | Patient phone number |
| date_of_birth | DATE | | NOT NULL | Patient date of birth |
| gender | VARCHAR(20) | | NOT NULL | Patient gender |
| address | VARCHAR(255) | | | Patient address |
| created_at | TIMESTAMP | | NOT NULL | Record creation timestamp |

### Primary Key

`patient_id` uniquely identifies each patient.

### Constraints

- `patient_id` is the primary key.
- `email` must be unique.
- `phone` must be unique.
- Required patient information cannot be NULL.

---

## 2.2 Doctors Table

The `doctors` table stores information about doctors working in the clinic.

| Column Name | Data Type | Key | Constraints | Description |
|---|---|---|---|---|
| doctor_id | BIGINT | PK | NOT NULL, AUTO_INCREMENT | Unique doctor identifier |
| first_name | VARCHAR(100) | | NOT NULL | Doctor first name |
| last_name | VARCHAR(100) | | NOT NULL | Doctor last name |
| email | VARCHAR(150) | | NOT NULL, UNIQUE | Doctor email address |
| phone | VARCHAR(20) | | NOT NULL, UNIQUE | Doctor phone number |
| specialization | VARCHAR(100) | | NOT NULL | Medical specialization |
| license_number | VARCHAR(100) | | NOT NULL, UNIQUE | Medical license number |
| availability | VARCHAR(255) | | | Doctor availability information |
| created_at | TIMESTAMP | | NOT NULL | Record creation timestamp |

### Primary Key

`doctor_id` uniquely identifies each doctor.

### Constraints

- `doctor_id` is the primary key.
- `email` must be unique.
- `phone` must be unique.
- `license_number` must be unique.
- Required doctor information cannot be NULL.

---

## 2.3 Appointments Table

The `appointments` table stores appointment information and establishes relationships between patients and doctors.

| Column Name | Data Type | Key | Constraints | Description |
|---|---|---|---|---|
| appointment_id | BIGINT | PK | NOT NULL, AUTO_INCREMENT | Unique appointment identifier |
| patient_id | BIGINT | FK | NOT NULL | Patient associated with appointment |
| doctor_id | BIGINT | FK | NOT NULL | Doctor associated with appointment |
| appointment_date | DATE | | NOT NULL | Date of appointment |
| appointment_time | TIME | | NOT NULL | Time of appointment |
| status | VARCHAR(30) | | NOT NULL | Appointment status |
| reason | VARCHAR(255) | | | Reason for appointment |
| created_at | TIMESTAMP | | NOT NULL | Record creation timestamp |

### Primary Key

`appointment_id` uniquely identifies each appointment.

### Foreign Keys

- `patient_id` references `patients(patient_id)`.
- `doctor_id` references `doctors(doctor_id)`.

### Constraints

- `appointment_id` is the primary key.
- `patient_id` cannot be NULL.
- `doctor_id` cannot be NULL.
- `appointment_date` cannot be NULL.
- `appointment_time` cannot be NULL.
- `status` cannot be NULL.

---

## 2.4 Admin Table

The `admin` table stores information about system administrators who manage system access and functionality.

| Column Name | Data Type | Key | Constraints | Description |
|---|---|---|---|---|
| admin_id | BIGINT | PK | NOT NULL, AUTO_INCREMENT | Unique admin identifier |
| first_name | VARCHAR(100) | | NOT NULL | Admin first name |
| last_name | VARCHAR(100) | | NOT NULL | Admin last name |
| email | VARCHAR(150) | | NOT NULL, UNIQUE | Admin email address |
| phone | VARCHAR(20) | | NOT NULL, UNIQUE | Admin phone number |
| username | VARCHAR(100) | | NOT NULL, UNIQUE | Admin username |
| password_hash | VARCHAR(255) | | NOT NULL | Hashed admin password |
| created_at | TIMESTAMP | | NOT NULL | Record creation timestamp |

### Primary Key

`admin_id` uniquely identifies each administrator.

### Constraints

- `admin_id` is the primary key.
- `email` must be unique.
- `phone` must be unique.
- `username` must be unique.
- `password_hash` cannot be NULL.

---

# 3. MySQL Relationships

The main relationships between the MySQL tables are:

```text
patients
   |
   | 1
   |
   | N
appointments
   |
   | N
   |
   | 1
doctors
