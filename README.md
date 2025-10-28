 Airbnb-Like Property Rental System

Overview

AirbnbLite is a desktop-based Java application that simulates a simplified version of Airbnb.
The system allows users to register, log in, list properties, make bookings, leave reviews, message hosts**, and provides an admin dashboard to manage data.

This project is built using Java with a Swing GUI, following good coding practices such as modular design, file-based data storage, and password hashing for security.

 Project Objectives

* Build a desktop-based rental system similar to Airbnb.
* Support user registration, login, and property listings.
* Enable property booking, reviews, and messaging.
* Provide admin access to view and manage system data.
* Demonstrate advanced Java features like Streams and Lambdas.
* Store data using a file-based persistence layer (no database needed).

Technologies Used

Component            / Technology                                   
Language               / Java SE 17 (or later)                        
GUI                    / Swing                                        
Data Storage           / File-based (Java Serialization / JSON files) 
Security               / SHA-256 Password Hashing + Salt              
IDE                    / NetBeans (recommended)                       
Advanced Java Features / Streams & Lambda Expressions                 

Project Structure

AirbnbLite/
├─ data/                           # Persistent data files (e.g., users.dat, listings.dat)
├─ src/
│  └─ com/airbnblite/
│     ├─ App.java                  # Main entry point
│     ├─ model/                    # Data models
│     │   ├─ User.java
│     │   ├─ Property.java
│     │   ├─ Booking.java
│     │   └─ Review.java
│     ├─ persistence/              # File read/write logic
│     │   └─ DataStore.java
│     ├─ security/                 # Security utilities
│     │   └─ SecurityUtil.java
│     ├─ ui/                       # Swing UI screens
│     │   ├─ LoginFrame.java
│     │   ├─ RegisterFrame.java
│     │   ├─ DashboardFrame.java
│     │   ├─ PropertyListFrame.java
│     │   ├─ BookingFrame.java
│     │   └─ AdminFrame.java
│     └─ util/                     # Utility classes (optional)
│         └─ SessionManager.java
└─ README.md
```
 Security Implementation

* Passwords are **never stored in plain text.
* Each password is hashed using SHA-256 with a unique random salt.
* The salt and hash are stored in the user file for verification.
* Login verification uses `SecurityUtil.verifyPassword()` for matching.

Features by Phase

Phase 1: System Planning & Setup

* User registration and login using Swing GUI.
* File-based storage for users (`users.dat`).
* Password hashing and session simulation.

Phase 2: Property Management

* Add, view, edit, and delete property listings.
* Store property data in `listings.dat`.
* Display available and booked properties on dashboard.

Phase 3: Booking & Reviews

* Book properties and update availability.
* Leave and view reviews for properties.
* Store reviews in `reviews.dat`.

Phase 4: Messaging & Admin Dashboard

* Implement user-to-host messaging.
* Admin dashboard to manage users, bookings, and listings.

How to Run the Project

1. Setup in NetBeans
2. Open NetBeans IDE.
3. Select Java with Ant → Java Applicatio.
4. Name the project: `AirbnbLite`.
5. Under Source Packages, create the following packages:

   * `com.airbnblite`
   * `com.airbnblite.model`
   * `com.airbnblite.persistence`
   * `com.airbnblite.security`
   * `com.airbnblite.ui`
5. Copy the `.java` files into their respective packages.
2. Run the Application**

* Right-click on `App.java` → **Run File**.
* The **Login Screen** will open.
* Click **Register** to create a new user.
* Log in using your credentials.

File-Based Data Example
users.dat (stored as serialized Java objects)**

Each user object contains:

```java
{
  "id": "a1b2c3d4",
  "username": "john_doe",
  "email": "john@example.com",
  "passwordHash": "Base64Hash",
  "salt": "Base64Salt",
  "role": "GUEST"
}
```

Later, you’ll add:

* `listings.dat` → property info
* `bookings.dat` → booking records
* `reviews.dat` → reviews per property

 Java Features Demonstrated

* Object-Oriented Programming (OOP)
* Swing GUI (JFrame, JPanel, JButton, JLabel, etc.)
* Streams & Lambda Expressions** for filtering, mapping, and sorting.
* Exception Handling and file I/O.
* Secure password management** using `MessageDigest` and salts.

Future Enhancements

* Replace file-based storage with a SQLite database.
* Add email notifications for bookings.
* Improve UI with images and property filtering.
* Add chart analytics for admin dashboard (bookings/revenue).

License

This project is developed for educational purposes as part of a **Java Desktop Application coursework project**.
You are free to modify or expand it for your personal learning.

Author

Developer: Sihle Kayise
Institution: CTU Training Solutions
Course: Occupational Certiface: Software Engneer 
Year:2025


