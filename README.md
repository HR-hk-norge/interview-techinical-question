# interview-techinical-question
Requirements
============
Assume you are creating a Clinic Application. You need to create two JAVA modules.
### Patient Visit Module
The patient Visit module must be a runnable working web application. You need to provide end to end (RESTful API, service and DAO) implementation for CURD operations for business domain entities below:
* Patient
* Physician
* Visit

Assume identifier (ID) for these domain entities will be defined by users while filling the form.
When creating entities with user input, you need to implement two requirements below:
* You must check for data duplication before persisting to the storage medium. You must throw a duplication exception to the caller if there is any data with the same ID.
* While data created during the holiday, a holiday exception must be thrown back to the caller.

When the entity is updated or deleted
* While data modified during the holiday, holiday exception must be thrown back to the caller. 

You may have a static class to provide static login user-id value.

You may persist holiday data manually into your DB.

This module must be an independently runnable module without Billing Module
## Billing Module
After a visit entity is created, a billing entity related to that visit shall be created only if the billing module is part of the deployment. This mean, some clients may not want the billing module as a part of the whole application.
## Storage Medium Requirement
MySQL DB shall be used as a primary DB for this application. But based on the client’s needs, the application must support RDBMS and any NoSQL DB that Hibernate does not support. When introducing a new DB, your implemented project structure must be flexible enough and implemented codes in API and Service classes must have a minimum impact or no impact (better). The main point is that logic codes in Service and API classes should not be affected because of storage medium changes.
## Technical Requirement
* Backend: Spring Boot
* MySQL
## Business Domain Entity
### Patient
* ID
* Name
* Age
* Gender
* Created Datetime
* Modifed Datetime
* Created By
### Physician
* ID
* Name
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Visit
* ID
* Visit Datetime
* Physician ID
* Reason
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Holiday
* Name
* Holiday Date
* Created Datetime
* Modified Datetime
* Created By
* Modified By
### Billing
* ID
* Patient ID
* Physician ID
* Billed Datetime
