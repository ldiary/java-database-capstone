# Schema Architecture

This application provides interactions with the outside world by presenting Admin and Doctor dashboards, served by Thymeleaf templates. It also provides REST API endpoints, enabling interactions with Appointments, Patient Records, and Patient Dashboard.

It leverages Spring Boot's MVC and REST controllers. This means, while the Admin and Doctor dashboards use Thymeleaf templates, all other modules will need to interact with the system using REST APIs. The system utilizes two different types of databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. JPA entities are used to interact with MySQL database while document models are used to interact with MongoDB.

## Data Flow

1. User accesses AdminDashboard, DoctorDashboard, PatientDashboard, PatientRecord or Appointment.
2. The AdminDashboard and DoctorDashboard actions will be routed to Thymeleaf Controllers, while PatientDashboard, PatientRecord and Appointment actions will be routed to REST Controllers.
3. Both Thymeleaf Controllers and REST Controllers will be served by Service Layer.[schema-architecture.md](schema-architecture.md)
4. For structured data (e.g. Doctor, Patient, Appointment, Admin) the Service Layer will connect to the MySQL repositories. For unstructured data (e.g. Prescription), the Service Layer will connect to the MongoDB repository.
5. MySQL repositories will access MySQL database engine, while MongoDB repository will access MongoDB database engine.
6. For Model Binding, MySQL data are converted into JPA entities which represent rows in the relational tables in the database. MongoDB data are loaded into document objects which map to BSON/JSON structures in the collections.
7. Bound models, both MySQL Models and MongDB Models are then accessed and passed to the user using either MVC or REST flows. In MVC flows, models are passed from the controller to Thymeleaf templates, while in REST flows, the same models (or transformed DTOs) are serialized into JSON.