# 

# Introduction and Goals {#section-introduction-and-goals}

CIS2 is a university management system. The goal of which will be to reduce work overhead for every participant in the university life. 

## Requirements Overview {#_requirements_overview}


The following functional requirements have been set by the stakeholders:

- Student Enrollment: Enabling students to register for courses, with the system handling eligibility checks and enrollment confirmations.
- Attendance Tracking: Allowing faculty to record student attendance for each class session.
- Grades Management: Faculty can input and manage grades, and students can access their academic records.
- Billing and Payments: Processing student payments for tuition and fees, and managing financial records.
- Course Management: Facilitating faculty in creating and updating course details.
- Reporting and Analytics: Generating reports on enrollment, grades, attendance, and financials for administrative use.
- User Authentication: Ensuring that all users are authorized to access the system according to their roles.

Furthermore, the system is propelled by the following driving forces: 

- Efficiency: Automating processes to save time.
- Accessibility: Providing easy access to information and services for students and faculty on different devices.
- Compliance: Adhering to security standards and privacy regulations.
- Scalability: Being capable of handling increased load as the university grows.
- User Engagement: Ensuring the interface is intuitive and meets the users needs.


A Use Case document has already been provided in the specification of this project. (see: https://github.com/marvkos/swarc-material/blob/main/materials/university%20managment/use%20case%20document.md)

## Quality Goals {#_quality_goals}

For CIS2 the following quality goals have been chosen: 

| Priority | Quality Goal         | Concrete   Scenario                                                                                                                                                                        |
|----------|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | Usability            | A   new student can log in, navigate, and enroll in courses within their first   visit, without needing to refer to a manual or seek help.                                                 |
| 2        | Reliability          | During   peak registration times, the system maintains its performance and   availability, handling the increased load without crashing or significant   slowdowns.                        |
| 3        | Security and Privacy | A   breach attempt is detected, and the system securely encrypts sensitive data   while alerting administrators to the attempt, preventing unauthorized access.                            |
| 4        | Scalability          | As   the university expands its courses and student numbers each year, the system   accommodates the increased data and user load without degradation in   performance or user experience. |
| 5        | Performance          | Faculty   members access and input grades for a large class, and the changes are   reflected in real-time, with the system handling the data-intensive operation   smoothly.               |

## Stakeholders {#_stakeholders}


-  **John Smith**, University Administrator: Responsible for the overall management and operational decisions within the university, including the use and implementation of the management application.


- **Jane Doe**, Senior Lecturer: As a faculty member, she is directly involved in academic aspects like course delivery, curriculum planning, and utilizing the system for academic management.


- **Michael Lee**, Chief Information Officer: Overseeing the technological infrastructure of the university, including the deployment, security, and maintenance of the University Management Application.


- **Emily Chen**, Student Representative: Representing the student body's interests and needs in regards to how the application affects student life, including enrollment, course management, and access to academic resources.


- **Sarah Johnson**, Financial Officer: Managing the financial aspects related to the application, including billing, payments, and budgeting for the system's implementation and upkeep.


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

::: formalpara-title
**Content**
:::

The building block view shows the static decomposition of the system
into building blocks (modules, components, subsystems, classes,
interfaces, packages, libraries, frameworks, layers, partitions, tiers,
functions, macros, operations, data structures, ...) as well as their
dependencies (relationships, associations, ...)

This view is mandatory for every architecture documentation. In analogy
to a house this is the *floor plan*.

::: formalpara-title
**Motivation**
:::

Maintain an overview of your source code by making its structure
understandable through abstraction.

This allows you to communicate with your stakeholder on an abstract
level without disclosing implementation details.

::: formalpara-title
**Form**
:::

The building block view is a hierarchical collection of black boxes and
white boxes (see figure below) and their descriptions.

![Hierarchy of building blocks](images/05_building_blocks-EN.png)

**Level 1** is the white box description of the overall system together
with black box descriptions of all contained building blocks.

**Level 2** zooms into some building blocks of level 1. Thus it contains
the white box description of selected building blocks of level 1,
together with black box descriptions of their internal building blocks.

**Level 3** zooms into selected building blocks of level 2, and so on.

See [Building Block View](https://docs.arc42.org/section-5/) in the
arc42 documentation.

## Whitebox Overall System {#_whitebox_overall_system}

Here you describe the decomposition of the overall system using the
following white box template. It contains

-   an overview diagram

-   a motivation for the decomposition

-   black box descriptions of the contained building blocks. For these
    we offer you alternatives:

    -   use *one* table for a short and pragmatic overview of all
        contained building blocks and their interfaces

    -   use a list of black box descriptions of the building blocks
        according to the black box template (see below). Depending on
        your choice of tool this list could be sub-chapters (in text
        files), sub-pages (in a Wiki) or nested elements (in a modeling
        tool).

-   (optional:) important interfaces, that are not explained in the
    black box templates of a building block, but are very important for
    understanding the white box. Since there are so many ways to specify
    interfaces why do not provide a specific template for them. In the
    worst case you have to specify and describe syntax, semantics,
    protocols, error handling, restrictions, versions, qualities,
    necessary compatibilities and many things more. In the best case you
    will get away with examples or simple signatures.

***\<Overview Diagram>***

Motivation

:   *\<text explanation>*

Contained Building Blocks

:   *\<Description of contained building block (black boxes)>*

Important Interfaces

:   *\<Description of important interfaces>*

Insert your explanations of black boxes from level 1:

If you use tabular form you will only describe your black boxes with
name and responsibility according to the following schema:

+-----------------------+-----------------------------------------------+
| **Name**              | **Responsibility**                            |
+=======================+===============================================+
| *\<black box 1>*      |  *\<Text>*                                    |
+-----------------------+-----------------------------------------------+
| *\<black box 2>*      |  *\<Text>*                                    |
+-----------------------+-----------------------------------------------+

If you use a list of black box descriptions then you fill in a separate
black box template for every important building block . Its headline is
the name of the black box.

### \<Name black box 1> {#__name_black_box_1}

Here you describe \<black box 1> according the the following black box
template:

-   Purpose/Responsibility

-   Interface(s), when they are not extracted as separate paragraphs.
    This interfaces may include qualities and performance
    characteristics.

-   (Optional) Quality-/Performance characteristics of the black box,
    e.g.availability, run time behavior, ....

-   (Optional) directory/file location

-   (Optional) Fulfilled requirements (if you need traceability to
    requirements).

-   (Optional) Open issues/problems/risks

*\<Purpose/Responsibility>*

*\<Interface(s)>*

*\<(Optional) Quality/Performance Characteristics>*

*\<(Optional) Directory/File Location>*

*\<(Optional) Fulfilled Requirements>*

*\<(optional) Open Issues/Problems/Risks>*

### \<Name black box 2> {#__name_black_box_2}

*\<black box template>*

### \<Name black box n> {#__name_black_box_n}

*\<black box template>*

### \<Name interface 1> {#__name_interface_1}

...

### \<Name interface m> {#__name_interface_m}

## Level 2 {#_level_2}

Here you can specify the inner structure of (some) building blocks from
level 1 as white boxes.

You have to decide which building blocks of your system are important
enough to justify such a detailed description. Please prefer relevance
over completeness. Specify important, surprising, risky, complex or
volatile building blocks. Leave out normal, simple, boring or
standardized parts of your system

### White Box *\<building block 1>* {#_white_box_emphasis_building_block_1_emphasis}

...describes the internal structure of *building block 1*.

*\<white box template>*

### White Box *\<building block 2>* {#_white_box_emphasis_building_block_2_emphasis}

*\<white box template>*

...

### White Box *\<building block m>* {#_white_box_emphasis_building_block_m_emphasis}

*\<white box template>*

## Level 3 {#_level_3}

Here you can specify the inner structure of (some) building blocks from
level 2 as white boxes.

When you need more detailed levels of your architecture please copy this
part of arc42 for additional levels.

### White Box \<\_building block x.1\_\> {#_white_box_building_block_x_1}

Specifies the internal structure of *building block x.1*.

*\<white box template>*

### White Box \<\_building block x.2\_\> {#_white_box_building_block_x_2}

*\<white box template>*

### White Box \<\_building block y.1\_\> {#_white_box_building_block_y_1}

*\<white box template>*

# Runtime View {#section-runtime-view}

::: formalpara-title
**Contents**
:::

The runtime view describes concrete behavior and interactions of the
system's building blocks in form of scenarios from the following areas:

-   important use cases or features: how do building blocks execute
    them?

-   interactions at critical external interfaces: how do building blocks
    cooperate with users and neighboring systems?

-   operation and administration: launch, start-up, stop

-   error and exception scenarios

Remark: The main criterion for the choice of possible scenarios
(sequences, workflows) is their **architectural relevance**. It is
**not** important to describe a large number of scenarios. You should
rather document a representative selection.

::: formalpara-title
**Motivation**
:::

You should understand how (instances of) building blocks of your system
perform their job and communicate at runtime. You will mainly capture
scenarios in your documentation to communicate your architecture to
stakeholders that are less willing or able to read and understand the
static models (building block view, deployment view).

::: formalpara-title
**Form**
:::

There are many notations for describing scenarios, e.g.

-   numbered list of steps (in natural language)

-   activity diagrams or flow charts

-   sequence diagrams

-   BPMN or EPCs (event process chains)

-   state machines

-   ...

See [Runtime View](https://docs.arc42.org/section-6/) in the arc42
documentation.

## \<Runtime Scenario 1> {#__runtime_scenario_1}

-   *\<insert runtime diagram or textual description of the scenario>*

-   *\<insert description of the notable aspects of the interactions
    between the building block instances depicted in this diagram.\>*

## \<Runtime Scenario 2> {#__runtime_scenario_2}

## ... {#_}

## \<Runtime Scenario n> {#__runtime_scenario_n}

# Deployment View {#section-deployment-view}

::: formalpara-title
**Content**
:::

The deployment view describes:

1.  technical infrastructure used to execute your system, with
    infrastructure elements like geographical locations, environments,
    computers, processors, channels and net topologies as well as other
    infrastructure elements and

2.  mapping of (software) building blocks to that infrastructure
    elements.

Often systems are executed in different environments, e.g. development
environment, test environment, production environment. In such cases you
should document all relevant environments.

Especially document a deployment view if your software is executed as
distributed system with more than one computer, processor, server or
container or when you design and construct your own hardware processors
and chips.

From a software perspective it is sufficient to capture only those
elements of an infrastructure that are needed to show a deployment of
your building blocks. Hardware architects can go beyond that and
describe an infrastructure to any level of detail they need to capture.

::: formalpara-title
**Motivation**
:::

Software does not run without hardware. This underlying infrastructure
can and will influence a system and/or some cross-cutting concepts.
Therefore, there is a need to know the infrastructure.

Maybe a highest level deployment diagram is already contained in section
3.2. as technical context with your own infrastructure as ONE black box.
In this section one can zoom into this black box using additional
deployment diagrams:

-   UML offers deployment diagrams to express that view. Use it,
    probably with nested diagrams, when your infrastructure is more
    complex.

-   When your (hardware) stakeholders prefer other kinds of diagrams
    rather than a deployment diagram, let them use any kind that is able
    to show nodes and channels of the infrastructure.

See [Deployment View](https://docs.arc42.org/section-7/) in the arc42
documentation.

## Infrastructure Level 1 {#_infrastructure_level_1}

Describe (usually in a combination of diagrams, tables, and text):

-   distribution of a system to multiple locations, environments,
    computers, processors, .., as well as physical connections between
    them

-   important justifications or motivations for this deployment
    structure

-   quality and/or performance features of this infrastructure

-   mapping of software artifacts to elements of this infrastructure

For multiple environments or alternative deployments please copy and
adapt this section of arc42 for all relevant environments.

***\<Overview Diagram>***

Motivation

:   *\<explanation in text form>*

Quality and/or Performance Features

:   *\<explanation in text form>*

Mapping of Building Blocks to Infrastructure

:   *\<description of the mapping>*

## Infrastructure Level 2 {#_infrastructure_level_2}

Here you can include the internal structure of (some) infrastructure
elements from level 1.

Please copy the structure from level 1 for each selected element.

### *\<Infrastructure Element 1>* {#__emphasis_infrastructure_element_1_emphasis}

*\<diagram + explanation>*

### *\<Infrastructure Element 2>* {#__emphasis_infrastructure_element_2_emphasis}

*\<diagram + explanation>*

...

### *\<Infrastructure Element n>* {#__emphasis_infrastructure_element_n_emphasis}

*\<diagram + explanation>*

# Cross-cutting Concepts {#section-concepts}

::: formalpara-title
**Content**
:::

This section describes overall, principal regulations and solution ideas
that are relevant in multiple parts (= cross-cutting) of your system.
Such concepts are often related to multiple building blocks. They can
include many different topics, such as

-   models, especially domain models

-   architecture or design patterns

-   rules for using specific technology

-   principal, often technical decisions of an overarching (=
    cross-cutting) nature

-   implementation rules

::: formalpara-title
**Motivation**
:::

Concepts form the basis for *conceptual integrity* (consistency,
homogeneity) of the architecture. Thus, they are an important
contribution to achieve inner qualities of your system.

Some of these concepts cannot be assigned to individual building blocks,
e.g. security or safety.

::: formalpara-title
**Form**
:::

The form can be varied:

-   concept papers with any kind of structure

-   cross-cutting model excerpts or scenarios using notations of the
    architecture views

-   sample implementations, especially for technical concepts

-   reference to typical usage of standard frameworks (e.g. using
    Hibernate for object/relational mapping)

::: formalpara-title
**Structure**
:::

A potential (but not mandatory) structure for this section could be:

-   Domain concepts

-   User Experience concepts (UX)

-   Safety and security concepts

-   Architecture and design patterns

-   \"Under-the-hood\"

-   development concepts

-   operational concepts

Note: it might be difficult to assign individual concepts to one
specific topic on this list.

![Possible topics for crosscutting
concepts](images/08-Crosscutting-Concepts-Structure-EN.png)

See [Concepts](https://docs.arc42.org/section-8/) in the arc42
documentation.

## *\<Concept 1>* {#__emphasis_concept_1_emphasis}

*\<explanation>*

## *\<Concept 2>* {#__emphasis_concept_2_emphasis}

*\<explanation>*

...

## *\<Concept n>* {#__emphasis_concept_n_emphasis}

*\<explanation>*

# Architecture Decisions {#section-design-decisions}

::: formalpara-title
**Contents**
:::

Important, expensive, large scale or risky architecture decisions
including rationales. With \"decisions\" we mean selecting one
alternative based on given criteria.

Please use your judgement to decide whether an architectural decision
should be documented here in this central section or whether you better
document it locally (e.g. within the white box template of one building
block).

Avoid redundancy. Refer to section 4, where you already captured the
most important decisions of your architecture.

::: formalpara-title
**Motivation**
:::

Stakeholders of your system should be able to comprehend and retrace
your decisions.

::: formalpara-title
**Form**
:::

Various options:

-   ADR ([Documenting Architecture
    Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions))
    for every important decision

-   List or table, ordered by importance and consequences or:

-   more detailed in form of separate sections per decision

See [Architecture Decisions](https://docs.arc42.org/section-9/) in the
arc42 documentation. There you will find links and examples about ADR.

# Quality Requirements {#section-quality-scenarios}

::: formalpara-title
**Content**
:::

This section contains all quality requirements as quality tree with
scenarios. The most important ones have already been described in
section 1.2. (quality goals)

Here you can also capture quality requirements with lesser priority,
which will not create high risks when they are not fully achieved.

::: formalpara-title
**Motivation**
:::

Since quality requirements will have a lot of influence on architectural
decisions you should know for every stakeholder what is really important
to them, concrete and measurable.

See [Quality Requirements](https://docs.arc42.org/section-10/) in the
arc42 documentation.

## Quality Tree {#_quality_tree}

::: formalpara-title
**Content**
:::

The quality tree (as defined in ATAM -- Architecture Tradeoff Analysis
Method) with quality/evaluation scenarios as leafs.

::: formalpara-title
**Motivation**
:::

The tree structure with priorities provides an overview for a sometimes
large number of quality requirements.

::: formalpara-title
**Form**
:::

The quality tree is a high-level overview of the quality goals and
requirements:

-   tree-like refinement of the term \"quality\". Use \"quality\" or
    \"usefulness\" as a root

-   a mind map with quality categories as main branches

In any case the tree should include links to the scenarios of the
following section.

## Quality Scenarios {#_quality_scenarios}

::: formalpara-title
**Contents**
:::

Concretization of (sometimes vague or implicit) quality requirements
using (quality) scenarios.

These scenarios describe what should happen when a stimulus arrives at
the system.

For architects, two kinds of scenarios are important:

-   Usage scenarios (also called application scenarios or use case
    scenarios) describe the system's runtime reaction to a certain
    stimulus. This also includes scenarios that describe the system's
    efficiency or performance. Example: The system reacts to a user's
    request within one second.

-   Change scenarios describe a modification of the system or of its
    immediate environment. Example: Additional functionality is
    implemented or requirements for a quality attribute change.

::: formalpara-title
**Motivation**
:::

Scenarios make quality requirements concrete and allow to more easily
measure or decide whether they are fulfilled.

Especially when you want to assess your architecture using methods like
ATAM you need to describe your quality goals (from section 1.2) more
precisely down to a level of scenarios that can be discussed and
evaluated.

::: formalpara-title
**Form**
:::

Tabular or free form text.

# Risks and Technical Debts {#section-technical-risks}

::: formalpara-title
**Contents**
:::

A list of identified technical risks or technical debts, ordered by
priority

::: formalpara-title
**Motivation**
:::

"Risk management is project management for grown-ups" (Tim Lister,
Atlantic Systems Guild.)

This should be your motto for systematic detection and evaluation of
risks and technical debts in the architecture, which will be needed by
management stakeholders (e.g. project managers, product owners) as part
of the overall risk analysis and measurement planning.

::: formalpara-title
**Form**
:::

List of risks and/or technical debts, probably including suggested
measures to minimize, mitigate or avoid risks or reduce technical debts.

See [Risks and Technical Debt](https://docs.arc42.org/section-11/) in
the arc42 documentation.

# Glossary {#section-glossary}

::: formalpara-title
**Contents**
:::

The most important domain and technical terms that your stakeholders use
when discussing the system.

You can also see the glossary as source for translations if you work in
multi-language teams.

::: formalpara-title
**Motivation**
:::

You should clearly define your terms, so that all stakeholders

-   have an identical understanding of these terms

-   do not use synonyms and homonyms

A table with columns \<Term> and \<Definition>.

Potentially more columns in case you need translations.

See [Glossary](https://docs.arc42.org/section-12/) in the arc42
documentation.

+-----------------------+-----------------------------------------------+
| Term                  | Definition                                    |
+=======================+===============================================+
| *\<Term-1>*           | *\<definition-1>*                             |
+-----------------------+-----------------------------------------------+
| *\<Term-2>*           | *\<definition-2>*                             |
+-----------------------+-----------------------------------------------+
