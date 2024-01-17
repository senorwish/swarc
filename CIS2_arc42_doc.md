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
| 1        | Usability            | When a student enters the university, he can log in, navigate and enroll in courses and check his grades and outstanding bills without the need to refer to a manual or seek help from other students.                                               |
| 2        | Reliability          | The system is up and running even during peak registration times. It also maintains its performance and availability during this increased load without crashing or significant slowdowns.                      |
| 3        | Security and Privacy | Attempts to breach the system will be detected and forwarded to be further analysed. the system also security encrypts sensitive data in accordance to relevant laws and standards.                       |
| 4        | Scalability          | CIS2 will not lack performance or user experience even as the university natually expands its courses and the number of students each year grows. |
| 5        | Performance          | Faculty   members access and input grades for a large class, and the changes are   reflected in real-time. The system handels these operations smoothly and fast.              |

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
| Technical      | Web-based              | The   system must be accessible online as a web-based platform in all common browsers such as Chrome, Firefox and Safari (yes, Microsoft Edge too).                       |
| Technical      | Modern Web   Technologies           | Must use technologies such as React, Node.js, and MongoDB for development to stay technically relevant.          |
| Technical      | Cloud Hosting   (AWS or Azure)      | The   application should be hosted on a scalable and secure cloud platform. This is to ensure that the application can be dynamically scaled as the university grows.           |
| Technical      | Data Security   and Encryption      | Must comply with data protection laws, security guidlines and other relevant regulations regarding the security of the system and its data.       |
| Technical      | Integration   with Existing Systems | The system must be able to integrate seamlessly with current university systems. See old.reddit as an example.|
| Organisational | Budget Limits                       | The project is constrained by the available budget for development and maintenance. |
| Organisational | Staffing and   Expertise            | Availability of skilled personnel to develop, deploy, and maintain the system.      |
| Organisational | Deadlines            | The system must be developed and deployed within a set timeframe. The prefered launchdate is during either summer or winter break.                   |
| Organisational | Compliance with Regulations       | Must adhere to  educational, privacy, and data protection regulations.               |
| Organisational | Stakeholder   Approval             | The system must meet the needs and gain approval from key stakeholders. An example of this could be the integration of a desired payment service by the Sarah Johnson, the finanical officer.             |
| Political      | Vendor Lock-in   Avoidance          | Preference for   solutions that don't overly depend on a single vendor. The system has to be able to adapt to different vendors.               |
| Convention     | Documentation   Standards           | Comprehensive  documentation must be maintained for all aspects of the system to ensure circulation of information regarding the system and its build.       |
| Convention     | Versioning   Guidelines             | Systematic approach to version control for software and documentation using git.             |
| Convention     | Naming   Conventions                | Consistent and  clear naming for variables, system components, files, and documentation.        |

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
| Students                      | Course selections, personal data, assignment submissions, maybe feedback | Course materials, schedules, grades, billing information and invoices           | Web portal                     | HTTPS, FTP |   |
| Faculty Members               | Course contents, grades, attendance records               | Schedules, administrative reports,  | Faculty portal, academic databases         | HTTPS, RESTful APIs, Database protocols            |   |
| Administrative Staff          | Student records, financial data                | Enrollment reports, financial reports         | Administrative dashboard                   | Database protocols, FTP           |   |
| IT Staff                      | System updates, security patches                    | System status reports, performance metrics                         | IT management tools                        | Network protocols, encryption standards            |   |
| External Educational Partners | Course data, enrollment information                                | Joint program details, transfer credit information                 | Partner portals, data interchange services |  APIs          |   |

## Technical Context {#_technical_context}

![technical_context](https://github.com/senorwish/swarc/blob/main/images/technical_scope.drawio.png?raw=true)

|      Channel/Interface      |        Transmission Media       |                                                                 Domain Specific I/O                                                                 |                                                                 Explanation                                                                |                  Protocols/Formats                 |
|:---------------------------:|:-------------------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------------------------------:|
| Web Portal                  | HTTPS                | - Student course selections, personal data, assignment submissions<br>- Faculty course content, grades<br>- Administrative reports, student records | The web portal is the primary interface for students, faculty, and staff. It uses HTTPS for secure transmission of data over the internet. | HTTPS, educational data standards (e.g., PESC XML) |
| Email System                | SMTP, IMAP/POP       | - Notifications to students, faculty, and staff<br>- Administrative communication                                                                   | Used for sending out notifications and communications related to enrollment, grades, assignments, and administrative matters.              | HTTPS, RESTful APIs, Database protocols            |
| API Integration             | HTTPS                | - Data exchange with external service partners such KLARNA for payment processes                                        | APIs allow for secure data exchange between the system and external/internal systems for course data, enrollment, and more.                | Database protocols, secure file transfer           |
| Database Access             | TCP/IP               | - Storage and retrieval of all system data                                                                                                          | The database is accessed through the intranet using TCP/IP for all operations related to storing and retrieving data.                      | Network protocols, encryption standards            |
| File Transfer (for updates) | FTP/SFTP | - System updates, patches<br>- Upload of bulk data like course materials, student records                                                           | Secure file transfer is used by IT staff for system updates or by administrative staff for uploading large sets of data into the system.   | Educational data exchange standards, APIs          |

# Solution Strategy {#section-solution-strategy}

**Technology Decisions:**

- Web-based Application: CIS2 will be composed as a Web-Based Application with React as the frontend technology and Node.js for the backend. These have been chosen for their performance, scalability and community support. For the databse, MongoDB has been chosen for its good usability with large data.
- Cloud Hosting (AWS or Azure): The development team has chosen to host the Webapplication with cloud services (either AWS or Azure) This ensures scalability, reliability, and security. Cloud services are selected for their robust infrastructure and wide range of services.
- Secure Communication Protocols (HTTPS, SFTP, etc.): To ensure data security during transmission.

**Top-level Decomposition:**

- Microservices: The system and its components will be decomposed into loosely coupled and independently deployable microservices. This helps manage updates und maintanance and will also help scalability of the system.
- SSO for Authentication: A centralized authentication mechanism that improves user experience and security.
- Modular User Interface: Separating the user interface into modules corresponding to user roles (for example students, faculty, administative personell will have a different overview) for better usability and maintainability.

**Achieving Key Quality Goals:**

- Usability: Adoption of user-centered design principles in the UI/UX, ensuring the system is intuitive and meets the needs of all users.
- Reliability and Availability: Implementation of failover strategies, regular backups, and robust error handling in the cloud environment.
- Security: Integration of comprehensive security measures, including data encryption, regular security audits, and adherence to privacy regulations.
- Performance: The use of caching, loadbalancing and well written database queries will ensure a good performance and speed even under load.

**Organizational Decisions:**

- Agile Development: Adopting an agile methodology for iterative development, allowing for flexibility and continuous improvement.
- Third-Party Integrations: For the payment service Klarna will be used. For email services Microsoft Outlook will be used.
- CI/CD: Implementing CI/CD pipelines for regular, automated testing and deployment to reduce errors and streamline updates.


# Building Block View {#section-building-block-view}

![get_grades_runtime](https://github.com/senorwish/swarc/blob/main/images/Building%20Block%20View.drawio.png?raw=true)

# Runtime View {#section-runtime-view}

## \<View Grades as a student> {#__runtime_scenario_1}

![get_grades_runtime](https://github.com/senorwish/swarc/blob/main/images/get_grades.drawio.png?raw=true)

## \<Grade a student as a teacher> {#__runtime_scenario_2}

![get_grades_runtime](https://github.com/senorwish/swarc/blob/main/images/give_grade.png?raw=true)


# Deployment View {#section-deployment-view}

![deployment](https://github.com/senorwish/swarc/blob/main/images/deployment_view.png?raw=true)

# Cross-cutting Concepts {#section-concepts}

In this chapter, we will document concepts and technologies which can be used in in different components and layers of the system. This helps establish a set of overarching principles and ensures consitency and homogeneity across the entire architecture.

**User Experience Concepts (UX):**

- Design System: A standardized UI design system with reusable components, and interaction patterns ensuring a cohesive user experience. 
- A overarching color scheme. 

**Safety and Security Concepts:**

- Authentication and Authorization: A robust security framework ensuring secure access controls and data protection.
- Data Encryption: All sensitive data is encrypted while at rest and while beeing sent. The access to this data is handled under the "need-to-know" principle.
- Audit Trails: Implementing a logging mechanisms which tracks the system usage and changes made. This is important for security audits and troubleshooting.

**Architecture and Design Patterns:**

- Microservices Architecture: Decoupling the system into microservices to help with scalability, maintainability, and deployment flexibility.
- API Gateway Pattern: A single entry point for all client requests, which provides an additional layer of abstraction and thightens security.

**Under-the-hood:**

- Database Abstraction: Utilizing ORM (Object-Relational Mapping) tools like Hibernate for database interactions. This decouples the application logic from the database engine. 
- Error Handling: A global error handling strategy for gracefully managing exceptions and providing clear, actionable feedback to users. This will be achived using feedback-loops and ticket systems. 

**Development Concepts:**

- Code Standards: Enforcing coding standards and reviews to maintain code quality.
- Continuous Integration/Continuous Deployment (CI/CD): Implementing CI/CD pipelines for automated testing and deployment.

**Operational Concepts:**

- Disaster Recovery: Strategies like regular backups and failover mechanisms to ensure business continuity.

# Architecture Decisions {#section-design-decisions}

**ADR 1: Use of Microservices Architecture**

- Status: Accepted
- Decision: Implement the system using a microservices architecture.
- Context: The need for scalability and flexibility in managing diverse university functions. CIS2 needs to be scaleable und flexible in      managing the diverse university functions.
- Consequences: Higher complexity in deployment and orchestration but better scalability and independent service management. 

**ADR 2: Cloud Hosting with AWS/Azure**

- Status: Accepted
- Decision: Host the system on AWS/Azure cloud services.
- Context: Requirement for high availability and scalability.
- Consequences: Potential vendor lock-in and variable costs, but gains in reliability and scalability.

**ADR 3: Use of React for Frontend Development**

- Status: Accepted
- Decision: Use React framework for frontend development.
- Context: The need for a robust, scalable, and maintainable frontend solution.
- Consequences: Requirement for developers with React skills in the development team.

**ADR 4: Centralized Authentication Service**

- Status: Accepted
- Decision: Implement a centralized authentication service using auth0. 
- Context: The necessity for a consistent and secure authentication mechanism across all services.
- Consequences: Centralized management of security but requires good implementation to prevent security vulnerabilities.

**ADR 5: NoSQL Database**

- Status: Accepted
- Decision: Use a NoSQL database (MongoDB) for data storage.
- Context: Need for flexibility in handling diverse and evolving data schemas.
- Consequences: Limited ability for complex transactions and queries but increased scalability and flexibility in data management.


# Quality Requirements {#section-quality-scenarios}

**High-Priority Quality Goals**

Usability
- Scenario: A student should be able to register for courses with no more than three clicks from the dashboard (Course-Overview -> Course Details -> Enroll). 

Reliability
- Scenario: The system must have an uptime of 99.9% during the semester. Downtime can only occure during summer or winter break. 

Performance
- Scenario: The system should load any grades of the students within two seconds under normal load conditions.

Security
- Scenario: Sensitive student data must be encrypted. Furthermore the system should withstand commong cybersecurity attacks like SQL Injections.

Scalability
- Scenario: The system should support a x10 increase in simulated user connections without loss of performance.

**Lower-Priority Quality Goals**

Maintainability
- Scenario: Developers should be able to implement a new feature or address a bug within a standardized time frame.

Compatibility
- Scenario: The system should be compatible with the latest versions of commong web browsers like Chrome, Firefox, and Safari.

Testability
- Scenario: The system should have automated tests covering at least 80% of the codebase, ensuring key functionalities work as expected after changes.

Disaster Recovery
- Scenario: In the event of a critical system failure, the system should be able to fully recover within four hours.


# Risks and Technical Debts {#section-technical-risks}

System Downtime During Critical Operations:
- Risk of system downtime during peak times such as registration periods.

Data Breach and Security Vulnerabilities:
- Potential leackage of sensitive student and faculty data due to security vulnerabilities.

Integration with previous Systems:
- Challenges and potential failures in integrating the new system with the outdated university systems.

Scalability Concerns:
- Risk that the system may not handle a rapid increase in user base or data volume.

Technical Debt from Rapid Development:
- Quick fixes and sloppy workarounds during stressing development times leading to bad and unstable code.

Vendor Lock-in with Cloud Providers:
- Dependence on specific cloud services may limit future infrastructure choices.

Performance Bottlenecks:
- Unefficient database queries could slow down the system.

