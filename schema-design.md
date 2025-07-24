# Schema Design

## MySQL Database Design
### Table: admin
- id: INT, Primary Key, Auto Increment
- name: VARCHAR, Not Null
- username: VARCHAR, Not Null, UNIQUE
- password: VARCHAR, Not Null

### Table: doctors
- id: INT, Primary Key, Auto Increment
- name: VARCHAR, Not Null
- specialty: VARCHAR, Not Null
- email: VARCHAR, Not Null, UNIQUE
- password: VARCHAR, Not Null
- phone: VARCHAR, Not Null

### Table: patients
- id: INT, Primary Key, Auto Increment
- name: VARCHAR, Not Null
- date_of_birth: DATE, Not Null
- email: VARCHAR, Not Null, UNIQUE
- password: VARCHAR, Not Null
- phone: VARCHAR, Not Null
- address: VARCHAR, Not Null

### Table: appointments
- id: INT, Primary Key, Auto Increment
- doctor_id: INT, Foreign Key → doctors(id)
- patient_id: INT, Foreign Key → patients(id)
- appointment_time: DATETIME, Not Null
- status: INT (0 = Scheduled, 1 = Completed, 2 = Cancelled)


## MongoDB Collection Design

### Collection: prescriptions

```json
{
  "_id": "ObjectId('1234567')",
  "patientName": "Elmer Roberts",
  "appointmentId": 21,
  "medication": "Amlodhipine",
  "dosage": "30mg",
  "doctorNotes": "Take 1 30mg table once a day",
  "repeatMedication": "no"
  "pharmacy": {
    "name": "Boots Pharmacy",
    "location": "East Market, London"
  }
}