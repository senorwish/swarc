# 

# Introduction and Goals {#section-introduction-and-goals}

CIS2 is a university management system. The goal of which will be to reduce work overhead for every participant in the university life. 

## Requirements Overview {#_requirements_overview}


The following functional requirements have been set by the stakeholders:

- Student Enrollment: This requirement is about enabling the students to register for courses. The system will also handel eligibility checks.
- Attendance Tracking: The faculty has to be able to record the students attendance for each class session.
- Grades Management: Faculty can input and manage grades which the students can then access in their academic records.
- Billing and Payments: The administration has to be able to issue invoices to the students which the students will then have to able to pay.
- Course Management: Faculity members have to be able to create, update and maintain courses and their details.
- Reporting and Analytics: Generating reports on enrollment, grades, attendance, and financials for the administration of the university.
- User Authentication: Ensuring that all users are authorized to access the system according to their roles.

Furthermore, the system is propelled by the following driving forces: 

- Efficiency: Automating processes to save time.
- Accessibility: Providing easy access to information and services for students and faculty on many different devices.
- Compliance: Adhering to security standards and privacy regulations. CIS2 will adhere to relevant security standards and privacy regulations such as the DSGVO. As a research institute CIS2 will also have to adhere to the upcoming NIS2 regulation.
- Scalability: As the university grows, the system has to be capable to handle an increased traffic and data load.
- User Engagement: Ensuring the interface is intuitive and meets the users needs.


A Use Case document has already been provided in the specification of this project. (see: https://github.com/marvkos/swarc-material/blob/main/materials/university%20managment/use%20case%20document.md)

## Quality Goals {#_quality_goals}

For CIS2 the following quality goals have been chosen and ranked by priority: 

| Priority | Quality Goal         | Concrete   Scenario                                                                                                                                                                        |
|----------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | Usability            | A   new student can log in, navigate, and enroll in courses within their first   visit, without needing to refer to a manual or seek help.                                                 |
| 2        | Reliability          | During   peak registration times, the system maintains its performance and   availability, handling the increased load without crashing or significant   slowdowns.                        |
| 3        | Security and Privacy | A   breach attempt is detected, and the system securely encrypts sensitive data   while alerting administrators to the attempt, preventing unauthorized access.                            |
| 4        | Scalability          | As   the university expands its courses and student numbers each year, the system   accommodates the increased data and user load without degradation in   performance or user experience. |
| 5        | Performance          | Faculty   members access and input grades for a large class, and the changes are   reflected in real-time, with the system handling the data-intensive operation   smoothly.               |

## Stakeholders {#_stakeholders}

As specified in the specification, the following persons represent the stakeholders in CIS2: 

-  **John Smith**, University Administrator: He is responsible for the management and operational decisions within the university. He is also responsible for the use and implementation of the management application. 


- **Jane Doe**, Senior Lecturer: Jane represents the faculty members and is therefore directly involved in the academic aspects of CIS2 including the course delivery, the curriculum planning and utilizing the system for academic use.


- **Michael Lee**, Chief Information Officer: As the CIO, Michael is overseeing the whole technological infrastructure of the university. This also includes the security, deployment and maintanance of CIS2. He is an important stakeholder when deciding on the technological aspects of CIS2


- **Emily Chen**, Student Representative: Emily Chen is a student and will therefore represent the students interests and needs. As a stakeholder she will be the contact person for anything regarting the student life, enrollment process and resource management.


- **Sarah Johnson**, Financial Officer: He is making the financial decisions in the university and is therefore the stakeholder responsible for the billing and payment processes. 


# Architecture Constraints {#section-architecture-constraints}

| Subdivision    | Constraint                          | Explanation                                                                           |
|----------------|-------------------------------------|---------------------------------------------------------------------------------------|
| Technical      | Web-based   Application             | The   system must be accessible online as a web-based platform.                       |
| Technical      | Modern Web   Technologies           | Must use   technologies such as React, Node.js, and MongoDB for development.          |
| Technical      | Cloud Hosting   (AWS or Azure)      | The   application should be hosted on a scalable and secure cloud platform.           |
| Technical      | Data Security   and Encryption      | Must comply   with data protection laws and ensure user data is secure.               |
| Technical      | Integration   with Existing Systems | The system   must be able to integrate seamlessly with current university systems.    |
| Organisational | Budget Limits                       | The project is   constrained by the available budget for development and maintenance. |
| Organisational | Staffing and   Expertise            | Availability   of skilled personnel to develop, deploy, and maintain the system.      |
| Organisational | Timeline and   Deadlines            | The system   must be developed and deployed within a set timeframe.                   |
| Organisational | Compliance   with Regulations       | Must adhere to   educational, privacy, and data protection regulations.               |
| Organisational | Stakeholder   Buy-In                | The system   must meet the needs and gain approval from key stakeholders.             |
| Political      | University   Policies               | Must align   with the broader policies and strategic objectives of the university.    |
| Political      | Vendor Lock-in   Avoidance          | Preference for   solutions that don't overly depend on a single vendor.               |
| Political      | Interdepartmental   Coordination    | Must   facilitate and not hinder interdepartmental communication and processes.       |
| Convention     | Programming   Guidelines            | Adherence to   specific coding standards and practices for development.               |
| Convention     | Documentation   Standards           | Comprehensive   documentation must be maintained for all aspects of the system.       |
| Convention     | Versioning   Guidelines             | Systematic   approach to version control for software and documentation.              |
| Convention     | Naming   Conventions                | Consistent and   clear naming for system components, files, and documentation.        |

# System Scope and Context {#section-system-scope-and-context}


- Student Management: Enrollment, personal data management, academic history.
- Course Management: Scheduling, curriculum updates, materials distribution.
- Faculty Management: Staff records, schedules, workload management.
- Attendance Management: Daily attendance recording, statistics, reports.
- Grades Management: Grade recording, transcript management, assessments.
- Billing and Payment Management: Fee calculations, payment processing, financial aid.
- Reporting and Analytics: Generation of reports for academic and administrative use.

## Business Context {#_business_context}

|     Communication Partner     |                               Inputs                               |                               Outputs                              |                 Interfaces                 |                  Protocols/Formats                 |   |
|:-----------------------------:|:------------------------------------------------------------------:|:------------------------------------------------------------------:|:------------------------------------------:|:--------------------------------------------------:|---|
| Students                      | Course selections, personal data, assignment submissions, feedback | Course materials, schedules, grades, billing information           | Web portal, mobile app                     | HTTPS, educational data standards (e.g., PESC XML) |   |
| Faculty Members               | Course content, grades, attendance records, feedback               | Schedule updates, administrative reports, student performance data | Faculty portal, academic databases         | HTTPS, RESTful APIs, Database protocols            |   |
| Administrative Staff          | Student records, course information, financial data                | Enrollment reports, financial reports, compliance reports          | Administrative dashboard                   | Database protocols, secure file transfer           |   |
| IT Staff                      | System updates, security patches, user feedback                    | System status reports, performance metrics                         | IT management tools                        | Network protocols, encryption standards            |   |
| Regulatory Bodies             | Compliance requests                                                | Compliance data, reports                                           | Secure data exchange portal                | Specific regulatory data exchange formats          |   |
| External Educational Partners | Course data, enrollment information                                | Joint program details, transfer credit information                 | Partner portals, data interchange services | Educational data exchange standards, APIs          |   |

## Technical Context {#_technical_context}

|      Channel/Interface      |        Transmission Media       |                                                                 Domain Specific I/O                                                                 |                                                                 Explanation                                                                |                  Protocols/Formats                 |
|:---------------------------:|:-------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------:|
| Web Portal                  | HTTPS                | - Student course selections, personal data, assignment submissions<br>- Faculty course content, grades<br>- Administrative reports, student records | The web portal is the primary interface for students, faculty, and staff. It uses HTTPS for secure transmission of data over the internet. | HTTPS, educational data standards (e.g., PESC XML) |
| Email System                | SMTP, IMAP/POP       | - Notifications to students, faculty, and staff<br>- Administrative communication                                                                   | Used for sending out notifications and communications related to enrollment, grades, assignments, and administrative matters.              | HTTPS, RESTful APIs, Database protocols            |
| API Integration             | HTTPS                | - Data exchange with external educational partners<br>- System integration with other university IT systems                                         | APIs allow for secure data exchange between the system and external/internal systems for course data, enrollment, and more.                | Database protocols, secure file transfer           |
| Database Access             | TCP/IP               | - Storage and retrieval of all system data                                                                                                          | The database is accessed through the intranet using TCP/IP for all operations related to storing and retrieving data.                      | Network protocols, encryption standards            |
| Mobile Application          | HTTPS                | - Mobile access to schedules, grades, course materials                                                                                              | The mobile app allows students and faculty to access system features on-the-go. It uses HTTPS to secure data transmission.                 | Specific regulatory data exchange formats          |
| File Transfer (for updates) | FTP/SFTP | - System updates, patches<br>- Upload of bulk data like course materials, student records                                                           | Secure file transfer is used by IT staff for system updates or by administrative staff for uploading large sets of data into the system.   | Educational data exchange standards, APIs          |

# Solution Strategy {#section-solution-strategy}

**Technology Decisions:**

- Web-based Application: Chosen for its accessibility and ease of maintenance. Technologies like React for the frontend, Node.js for the backend, and MongoDB for the database are selected for their performance, scalability, and community support.
- Cloud Hosting (AWS or Azure): Ensures scalability, reliability, and security. Cloud services are selected for their robust infrastructure and wide range of services.
- Secure Communication Protocols (HTTPS, SFTP, etc.): To ensure data security during transmission.

**Top-level Decomposition:**

- Microservices: The system is decomposed into loosely coupled, independently deployable microservices. This approach enhances scalability and allows for more manageable updates and maintenance.
- SSO for Authentication: A centralized authentication mechanism that improves user experience and security.
- Modular User Interface: Separating the user interface into modules corresponding to user roles (students, faculty, admin) for better usability and maintainability.

**Achieving Key Quality Goals:**

- Usability: Adoption of user-centered design principles in the UI/UX, ensuring the system is intuitive and meets the needs of all users.
- Reliability and Availability: Implementation of failover strategies, regular backups, and robust error handling in the cloud environment.
- Security: Integration of comprehensive security measures, including data encryption, regular security audits, and adherence to privacy regulations.
- Performance: Use of caching, load balancing, and efficient database queries to ensure the system performs well under load.

**Organizational Decisions:**

- Agile Development: Adopting an agile methodology for iterative development, allowing for flexibility and continuous improvement.
- Third-Party Integrations: Deciding on strategic partnerships for features like payment gateways, email services, or library databases to enhance functionality without developing every component in-house.
- CI/CD: Implementing CI/CD pipelines for regular, automated testing and deployment to reduce errors and streamline updates.


# Building Block View {#section-building-block-view}


## Whitebox Overall System {#_whitebox_overall_system}

## Level 2 {#_level_2}

## Level 3 {#_level_3}



# Runtime View {#section-runtime-view}

## \<View Grades as a student> {#__runtime_scenario_1}

![get_grades_runtime](https://github.com/senorwish/swarc/blob/main/images/get_grades.drawio.png?raw=true)

## \<Grade a student as a teacher> {#__runtime_scenario_2}

![get_grades_runtime](https://github.com/senorwish/swarc/blob/main/images/give_grade.png?raw=true)


# Deployment View {#section-deployment-view}

![deployment](https://github.com/senorwish/swarc/blob/main/images/deployment_view.png?raw=true)

# Cross-cutting Concepts {#section-concepts}

In documenting cross-cutting concepts for the University Management System, we aim to establish a set of overarching principles and guidelines that ensure consistency and homogeneity across the entire architecture. These concepts form the backbone of the system's design and implementation, impacting multiple components and layers. Here's an outline structured around the suggested categories:
Domain Concepts:

- Domain Model: A unified and consistent domain model that defines the core entities such as students, faculty, courses, and grades, as well as their relationships, which is shared across all components.
- Business Rules: Clear definitions of business logic, such as enrollment prerequisites, grading policies, and billing cycles, that are centrally managed and applied consistently across the system.

**User Experience Concepts (UX):**

- Design System: A standardized UI design system with reusable components, color schemes, and interaction patterns ensuring a cohesive user experience.
- Accessibility Standards: Adherence to WCAG guidelines to ensure the system is usable by all users, including those with disabilities.

**Safety and Security Concepts:**

- Authentication and Authorization: A robust security framework ensuring secure access controls and data protection.
- Data Encryption: All sensitive data, both at rest and in transit, is encrypted using industry-standard protocols.
- Audit Trails: Implementing logging mechanisms to track system usage and changes, important for security audits and troubleshooting.

**Architecture and Design Patterns:**

- Microservices Architecture: Decoupling the system into microservices to enhance scalability, maintainability, and deployment flexibility.
- API Gateway Pattern: A single entry point for all client requests, providing an additional layer of abstraction and security.

**Under-the-hood:**

- Database Abstraction: Utilizing ORM (Object-Relational Mapping) tools like Hibernate for database interactions to decouple the application logic from the database engine.
- Error Handling: A global error handling strategy for gracefully managing exceptions and providing clear, actionable feedback to users.

**Development Concepts:**

- Code Standards: Enforcing coding standards and reviews to maintain code quality.
- Continuous Integration/Continuous Deployment (CI/CD): Implementing CI/CD pipelines for automated testing and deployment.

**Operational Concepts:**

- Monitoring and Logging: System-wide monitoring and logging to ensure operational health and quick resolution of issues.
- Disaster Recovery: Strategies like regular backups and failover mechanisms to ensure business continuity.

# Architecture Decisions {#section-design-decisions}

**Adopting Microservices Architecture**

- Rationale: The decision to adopt a microservices architecture was driven by the need for scalability and flexibility. It allows individual teams to develop, deploy, and scale their services independently, improving the system's responsiveness to changing requirements.
- Consequences: This decision introduces complexity in deployment and orchestration, necessitating a robust infrastructure and DevOps expertise.

**Cloud Hosting with AWS/Azure**

- Rationale: Using cloud services like AWS or Azure provides scalability, high availability, and a range of services that can be leveraged for different needs. It also transfers some of the infrastructure security responsibilities to the cloud provider.
- Consequences: This decision leads to potential vendor lock-in and requires careful management of costs associated with cloud services.

# Quality Requirements {#section-quality-scenarios}

**High-Priority Quality Goals**

Usability
- Scenario: A student should be able to register for courses with no more than three clicks from the dashboard.

Reliability
- Scenario: The system must have an uptime of 99.9% during registration periods.

Performance
- Scenario: The system should load any student's grade book within two seconds under normal load conditions.

Security
- Scenario: Personal student data must be encrypted in transit and at rest, and the system should withstand common security attacks like SQL injection and XSS.

Scalability
- Scenario: The system should support a tenfold increase in simultaneous user connections without degradation of performance.

**Lower-Priority Quality Goals**

Maintainability
- Scenario: Developers should be able to implement a new feature or address a bug within a standardized time frame.

Compatibility
- Scenario: The system should be compatible with the two latest versions of major web browsers like Chrome, Firefox, and Safari.

Interoperability
- Scenario: The system should be able to exchange data with existing university systems using standardized data formats such as CSV or JSON.

Testability
- Scenario: The system should have automated tests covering at least 80% of the codebase, ensuring key functionalities work as expected after changes.

Disaster Recovery
- Scenario: In the event of a critical system failure, the system should be able to fully recover within four hours.


# Risks and Technical Debts {#section-technical-risks}

System Downtime During Critical Operations:
- Risk of system outages during peak times such as registration or grading periods.

Data Breach and Security Vulnerabilities:
- Potential exposure of sensitive student and faculty data due to security weaknesses.

Integration with Legacy Systems:
- Challenges and potential failures in integrating with outdated university systems.

Scalability Concerns:
- Risk that the system may not handle a rapid increase in user base or data volume.

Compliance with Data Protection Regulations:
- The possibility of incurring legal penalties due to non-compliance with regulations like GDPR or FERPA.

Technical Debt from Rapid Development:
- Accumulation of quick fixes and workarounds during aggressive development timelines leading to unstable code.

Vendor Lock-in with Cloud Providers:
- Dependence on specific cloud services that may limit future infrastructure choices.

Performance Bottlenecks:
- Unoptimized queries or inefficient code that could slow down the system.

User Interface Inconsistency:
- Disparate user interface elements leading to a confusing user experience.

# Glossary {#section-glossary}

::: formalpara-title
**Contents**
:::

