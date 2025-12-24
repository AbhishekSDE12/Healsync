# Healsync
Walk us through something you've built and shipped end-to-end

What was it? What did it do, and who was it for?
I worked on HealSync, a unified multi-hospital appointment management platform built to digitize and streamline appointment booking across hospitals. The system replaces manual, phone-based coordination with a secure, role-based workflow.

The platform was designed for:
- Patients to search doctors by specialization and book appointments
- Doctors to manage availability and appointment requests
- Hospital/Admin teams to onboard hospitals, manage doctors, and handle operational cases

The core goal was to build a reliable and scalable system that works across multiple hospitals.

--------------------------------------------------

What was your role?
This was a group project, and I worked as a core backend and integration developer.

I owned and contributed to:
- Designing and developing REST APIs using Spring Boot
- Implementing JWT-based authentication and role-based access control
- Designing key parts of the database schema (users, roles, appointments)
- Handling business logic and edge cases around doctor availability
- Integrating backend APIs with the React frontend
- Testing and validating APIs using Postman

While the project was collaborative, I took ownership of backend logic, security, and edge-case handling.

--------------------------------------------------

Key decisions I made (and why)

1. Enforcing role-based access control at the backend
Options:
- Handle role logic mostly on the frontend
- Enforce access control strictly at the backend

Decision:
Enforced role-based access control at the backend using Spring Security and JWT.

Why:
Admin, Doctor, and Patient had very different permissions. Backend enforcement ensured security, correctness, and simpler frontend logic.

Trade-off:
More backend configuration and logic, but significantly safer and more scalable.

--------------------------------------------------

2. Introducing a hospital-level admin for emergency and availability edge cases
Problem:
Doctors may become unavailable due to emergencies or may forget to update their availability, which could block appointments or cause incorrect bookings.

Options:
- Allow only doctors to manage availability
- Introduce a hospital-level admin who can manage doctor availability

Decision:
Added a hospital-level admin role with permission to update doctor availability and manage appointments.

Why:
This handled real-world scenarios like emergency leave, sudden unavailability, and appointment reassignment without system downtime.

Trade-off:
Additional role and permission logic, but much higher operational reliability.

--------------------------------------------------

3. Choosing a modular monolith architecture
Options:
- Microservices architecture
- Modular monolith architecture

Decision:
Used a modular monolith with clear controller, service, and repository layers.

Why:
Given time constraints and team size, this allowed faster development, easier debugging, and clearer ownership.

Trade-off:
Less independent scaling, but faster delivery and simpler maintenance.

--------------------------------------------------

What constraints did you face?
- Fixed academic timelines
- Coordination challenges in a group project
- Evolving requirements as domain understanding improved
- Limited real-world user feedback

These constraints pushed us to prioritize clarity, correctness, and shipping over over-engineering.

--------------------------------------------------

What happened? Did it ship? What worked and what didn’t?
Yes, the project was completed and fully functional.

What worked well:
- Secure authentication and role separation
- Clean API contracts
- Handling of real-world edge cases like doctor unavailability

What didn’t work perfectly:
- Frontend user experience could be improved
- Limited logging and observability
- No background jobs for notifications or reminders

--------------------------------------------------

What would you do differently now?
If I were building this again, I would:
- Add structured logging and monitoring early
- Introduce background jobs for reminders and cancellations
- Design appointment data to support analytics use cases
- Explore AI-assisted features like smart scheduling or demand prediction

--------------------------------------------------

Final reflection
HealSync taught me how real systems behave under ambiguity. I learned to think beyond features and design for failure cases, human error, and operational control, which strongly shaped how I approach backend and system design.
