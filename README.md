#Parking sytem
This project presents a parking lot system developed in Java, incorporating basic dummy database functionality. The system is designed to showcase various software design principles, patterns, and industry standards. It provides a practical example of how to implement object-oriented programming techniques to create a maintainable and scalable application. The project serves as a hands-on educational tool for understanding the intricacies of software design and architecture in a real-world context.

##Overview
This parking lot system is designed to handle multiple parking lots, each with its own floors and parking spaces. It’s set up so that each space can accommodate various types and sizes of vehicles, making sure there’s a spot that fits everything from small cars to larger trucks.


![Parking drawio (1)-1](https://github.com/user-attachments/assets/7a399232-7942-4789-b774-b154deac2fc8)



## Features

* **Multiple Parking Lots:** The system can manage multiple parking lots, each with its own set of parking floors.
* **Parking Floors:** Each parking lot consists of multiple parking floors, accommodating different numbers of vehicles.
* **Parking Slots:** The system supports various vehicles, including cars, motorcycles, trucks, buses, and bicycles.
* **Dummy Database:** Although the system does not use a real database, it simulates database functionality using a map-based data structure.

##1 Requirements for Designing the Parking Lot System

1.1 Functional Requirements
User Authentication: The system must support user registration and login. This ensures that users can create and access their accounts safely, much like logging into a secure online banking system.
Parking Space Management: Real-time tracking of parking space availability is essential. This feature will keep users informed about which spaces are free or occupied, similar to how inventory systems track product availability.
Reservation System: Users should be able to reserve parking spots in advance through an online platform. This functionality is akin to booking a hotel room, providing users with the assurance of a secured spot before arriving.
Payment Processing: A reliable payment system is crucial for handling parking fees. The payment process should be straightforward and secure, much like making a purchase on a well-established e-commerce site.
Navigation Assistance: The system should offer guidance to help users find their reserved parking spaces. This is comparable to GPS navigation, assisting users in reaching their destinations efficiently.
1.2 Non-Functional Requirements
Latency: The system must provide quick responses to user requests, ensuring minimal wait times. Efficient response times are essential for a smooth user experience, especially during peak hours.
Data Integrity: Maintaining accurate and consistent data is vital. The system should ensure that information about parking spaces and user transactions remains reliable and up-to-date.
Scalability: The system should be designed to handle increasing numbers of users and transactions without performance degradation. This involves preparing for higher traffic volumes and expanding resources as needed.
2. Capacity Estimation for Parking Lot System
To estimate system capacity, consider the following:

Traffic Volume: Average number of vehicles and reservation patterns.
User Reservations: The proportion of users making reservations in advance.
Unreserved Payments: The percentage of users paying for parking without prior reservation.
For example:

Monthly Traffic: 50,000 vehicles
Traffic Per Second: 50,000 / (30 * 24 * 60 * 60) ≈ 0.019
Reservation Assumptions: 30% reserve in advance, 10% pay without reservation
Storage Requirements:

Transactions Per Second (TPS): 30 + 10 = 40
Storage Per Transaction: Approx. 200 KB
Total Storage Needed: 40 * 200 KB = 8 MB per second
Annual Storage: 8 MB * 60 * 60 * 24 * 365 ≈ 250 TB

##3. Use Case Diagram for Parking Lot System
A use case diagram helps visualize how users interact with the system:

Registered User: Users who have an account can log in, reserve parking spaces, and view their reservation history.
Unregistered User: Users without an account can check parking availability, access general information, and view rates.
System: The system processes user requests, manages reservations, and handles payments.

##4. Architecture of Parking Lot System
The architecture involves:

Hardware and Software Components:

Backend Services: Manage requests, process reservations, and handle payments.
Database: Stores user data, parking information, and transaction records.
System Process:

User Registration: Users create accounts via the mobile app.
Space Reservation: Users search for and book parking spaces based on their destination.
Backend Processing: The system verifies space availability and provides instructions to the user.


##5. Low-Level Design (LLD) for Parking Lot System
Data Schema
Database Structure: Define tables and relationships for users, reservations, parking spaces, payments, and feedback.
Schema Details: Include tables for user details, reservation records, parking space availability, payment transactions, and user feedback.
Algorithms
Core Functionalities: Implement algorithms for handling requests, processing payments, and managing reservations.
Key Functions: Focus on payment processing, reservation management, and authentication.
Data Flow Diagrams
Information Flow: Illustrate how data moves between system components, showing interactions between users, the application, and the database.

##6. High-Level Design (HLD) for Parking Lot System
System Architecture
Layers: Define the presentation layer (user interface), business logic layer (request processing), and data layer (storage and retrieval).
Interactions: Describe how components interact, including user interface communication with the server and data handling.
Module Interaction
Component Flow: Outline how different modules interact, ensuring smooth coordination between functionalities.
User Interface Design
Design Focus: Emphasize ease of use and intuitive design, aligning with user needs and project goals.
External Interfaces
Integration: Specify how the system interfaces with external services or APIs, including protocols and data formats.

##7. Database Design for Parking Lot System
User Table
Fields: User_id, Username, Email_address, Password, License_plate, Created_date
Reservation Table
Fields: Reservation_id, User_id, Parking_space_id, Reservation_time, Duration
Parking Space Table
Fields: Parking_space_id, Availability_status, Location, Type, Rate
Payment Table
Fields: Payment_id, User_id, Reservation_id, Amount, Payment_date
Feedback Table
Fields: Feedback_id, User_id, Reservation_id, Rating, Comments



##9. Microservices Used for Parking Lot System
9.1 User Management
Functions: Manages user registration, authentication, and profile management.
9.2 Reservation Management
Functions: Handles reservations, checks availability, and manages reservation history.
9.3 Payment Processing
Functions: Manages payment transactions and refund handling.


##10. Scalability and Performance
10.1 Horizontal Scaling
Description: Add more servers to handle increased user load and transactions.
10.2 Load Balancing
Description: Distribute requests across multiple servers to prevent overload.
10.3 Containerization
Description: Use containers to ensure consistency and ease of deployment.
10.4 Database Sharding
Description: Partition data across multiple databases to improve performance and scalability.


##11. Principles Applied
11.1 CRUD Operations
Create: Users can create accounts and reservations.
Read: Users can view their reservations and parking space availability.
Update: Users can modify their reservations and account details.
Delete: Users can cancel their reservations if needed.
11.2 SOLID Principles
Single Responsibility Principle: Each class or module should have one reason to change, such as separating user management from reservation management.
Open/Closed Principle: The system should be open for extension but closed for modification, allowing new features to be added with minimal changes to existing code.
Liskov Substitution Principle: Subtypes should be replaceable for their base types without altering the correctness of the program.
Interface Segregation Principle: Provide specific interfaces for different functionalities to ensure that clients only depend on what they use.
Dependency Inversion Principle: High-level modules should not depend on low-level modules. Both should depend on abstractions, which allows for easier changes and testing.
11.3 Concurrency
Synchronization: Ensure that critical sections of code, such as payment processing, are thread-safe to prevent race conditions.
Database Transactions: Use transactions to maintain data integrity, especially for operations involving multiple steps like booking and payment.
Scalable Design: Design the system to handle multiple requests simultaneously, ensuring that performance remains optimal even under heavy load.


##12. Security
Encryption: Protect sensitive data with encryption.
Authentication: Implement robust user verification.
Secure Transactions: Use secure payment methods and transaction validation.


##13. Conclusion
This document outlines a understable design for a parking lot management system. By adhering to these design principles and incorporating essential features, the project aims to deliver a reliable, scalable, and user-friendly solution for parking management.
