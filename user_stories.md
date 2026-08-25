# Smart Clinic Management System — User Stories

Admin User Stories
User Story 1

Title:
As an Admin, I want to manage user access, so that only authorized users can access the appropriate system functionality.

Acceptance Criteria:

The Admin can manage access for system users.
Users can access only the functionality permitted for their role.
Unauthorized users cannot access restricted functionality.

Priority: High
Story Points: 5
Notes:

Access control should apply to Admin, Doctor, and Patient functionality.
The exact authentication mechanism is not specified in the architecture document.
User Story 2

Title:
As an Admin, I want to manage doctor information, so that doctor information is maintained correctly in the system.

Acceptance Criteria:

The Admin can view doctor information.
The Admin can add or update doctor information.
The system stores doctor information correctly.

Priority: High
Story Points: 5
Notes:

Doctor information is part of the structured data managed by the system.
User Story 3

Title:
As an Admin, I want to manage patient information, so that patient information is maintained correctly in the system.

Acceptance Criteria:

The Admin can view patient information.
The Admin can add or update patient information.
The system stores patient information correctly.

Priority: High
Story Points: 5
Notes:

Patient information is stored as structured data.
User Story 4

Title:
As an Admin, I want to view and manage appointments, so that the clinic can maintain an organized appointment schedule.

Acceptance Criteria:

The Admin can view appointments.
The Admin can manage appointment information.
Appointment information is stored and retrieved correctly.

Priority: High
Story Points: 5
Notes:

Appointments are part of the structured data managed by the system.
Patient User Stories
User Story 5

Title:
As a Patient, I want to book an appointment with a doctor, so that I can receive a medical consultation.

Acceptance Criteria:

The Patient can select a doctor for an appointment.
The Patient can book an available appointment.
The appointment is stored successfully in the system.

Priority: High
Story Points: 5
Notes:

Appointment functionality is explicitly included in the system architecture.
User Story 6

Title:
As a Patient, I want to view my appointments, so that I can keep track of my scheduled consultations.

Acceptance Criteria:

The Patient can access their appointments.
The Patient can view appointment details.
The system displays the patient's appointment information correctly.

Priority: High
Story Points: 3
Notes:

Appointment information is maintained as structured data.
User Story 7

Title:
As a Patient, I want to access my patient dashboard, so that I can view information relevant to my clinic activities.

Acceptance Criteria:

The Patient can access the Patient Dashboard.
The dashboard displays relevant patient information.
The dashboard retrieves the required information from the system.

Priority: Medium
Story Points: 5
Notes:

The architecture specifically identifies a Patient Dashboard.
User Story 8

Title:
As a Patient, I want to view my patient records, so that I can access my medical information.

Acceptance Criteria:

The Patient can access the Patient Records functionality.
The system retrieves the patient's records.
The patient records are displayed correctly.

Priority: High
Story Points: 5
Notes:

Patient Records are explicitly identified as a system module in the architecture.
Doctor User Stories
User Story 9

Title:
As a Doctor, I want to manage my availability, so that patients can book appointments during my available time slots.

Acceptance Criteria:

The Doctor can specify their availability.
The system stores the Doctor's availability.
Patients can use the available information when booking appointments.

Priority: High
Story Points: 5
Notes:

Managing doctor availability is explicitly part of the Doctor functionality required by the assignment.
User Story 10

Title:
As a Doctor, I want to view my appointments, so that I can keep track of my scheduled consultations.

Acceptance Criteria:

The Doctor can access their appointments.
The Doctor can view appointment details.
The system displays the Doctor's appointment information correctly.

Priority: High
Story Points: 3
Notes:

Appointment management is one of the core Doctor responsibilities.
User Story 11

Title:
As a Doctor, I want to manage patient appointments, so that I can effectively organize my consultation schedule.

Acceptance Criteria:

The Doctor can view patient appointments.
The Doctor can manage appointment information.
Changes to appointment information are stored correctly.

Priority: High
Story Points: 5
Notes:

The architecture includes an Appointment module and Doctor appointment management.
User Story 12

Title:
As a Doctor, I want to view patient information, so that I can access the information required for patient consultations.

Acceptance Criteria:

The Doctor can access relevant patient information.
The system retrieves the patient's information correctly.
The patient information is displayed to the Doctor.

Priority: High
Story Points: 5
Notes:

Patient information is stored as structured data in MySQL.
User Story 13

Title:
As a Doctor, I want to manage patient prescriptions, so that prescription information can be maintained as part of the patient's medical information.

Acceptance Criteria:

The Doctor can create prescription information.
The Doctor can view prescription information.
Prescription information is stored and retrieved correctly.

Priority: High
Story Points: 5
Notes:

Prescriptions are identified in the architecture as document-oriented data stored in MongoDB.
