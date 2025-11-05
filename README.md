🌩️ Nimbus Submission — Web Applications Using Servlets and JSP
This project contains three independent web applications demonstrating Servlets, JSP, and JDBC for user input handling, database interaction, and dynamic content generation.

Each part can be deployed separately on Apache Tomcat or run together in the same environment.

📁 Project Structure
Nimbus_WebApp/ │ ├── PartA_UserLogin/ │ ├── web/ │ │ ├── login.html │ │ └── WEB-INF/web.xml │ └── src/com/nimbus/servlets/LoginServlet.java │ ├── PartB_EmployeeRecords/ │ ├── web/ │ │ ├── employees.html │ │ └── WEB-INF/web.xml │ └── src/com/nimbus/servlets/EmployeeServlet.java │ └── database/create_employee_table.sql │ ├── PartC_AttendancePortal/ │ ├── web/ │ │ ├── attendance.jsp │ │ ├── success.jsp │ │ └── WEB-INF/web.xml │ └── src/com/nimbus/servlets/AttendanceServlet.java │ └── database/create_attendance_table.sql │ └── README.md

⚙️ Requirements
Apache Tomcat 9.0 or above
Java JDK 11 or above
MySQL Server 8.0 or above
JDBC driver: mysql-connector-j.jar (place in Tomcat’s lib folder)
🧩 Part A — User Login Using Servlet and HTML
Objective: Create a simple login form handled by a Java Servlet.

Features:

HTML form for username and password
Servlet validates credentials (hardcoded)
Displays personalized message on success
How to Run:

Copy the PartA_UserLogin folder into Tomcat’s webapps directory.
Start the Tomcat server.
Open http://localhost:8080/PartA_UserLogin/login.html.
Use credentials: Username: admin Password: 12345
🧩 Part B — Display Employee Records (Servlet + JDBC)
Objective: Integrate Servlets with a database to display and search employee data.

Database Table: CREATE TABLE Employee ( EmpID INT PRIMARY KEY, Name VARCHAR(50), Salary DECIMAL(10,2) );

Features:

View all employee records
Search employee by ID
Results displayed in an HTML table
How to Run:

Run create_employee_table.sql in MySQL to create and populate the Employee table.
Update the database username and password in EmployeeServlet.java.
Copy the PartB_EmployeeRecords folder into Tomcat’s webapps directory.
Start Tomcat and open http://localhost:8080/PartB_EmployeeRecords/employees.html.
🧩 Part C — Student Attendance Portal (JSP + Servlet + JDBC)
Objective: Develop a student attendance portal using JSP (frontend) and Servlets (backend).

Database Table: CREATE TABLE Attendance ( StudentID INT, AttendanceDate DATE, Status VARCHAR(10) );

Features:

JSP form for attendance input
Servlet inserts data into the database
Success message shown via JSP
How to Run:

Run create_attendance_table.sql in MySQL to create the Attendance table.
Update the database username and password in AttendanceServlet.java.
Copy the PartC_AttendancePortal folder into Tomcat’s webapps directory.
Start Tomcat and open http://localhost:8080/PartC_AttendancePortal/attendance.jsp.
🧠 Concepts Demonstrated
Part	Concept	Technologies Used
A	Handling HTML form data using Servlets	HTML, Java Servlet
B	Database integration using JDBC	HTML, Servlet, MySQL
C	MVC architecture with JSP and Servlet	JSP, Servlet, MySQL
🚀 Running the Whole Project Together
If you want to run all three parts under a single Tomcat instance:

Make sure MySQL is running and both Employee and Attendance tables are created.

Place all three folders (PartA_UserLogin, PartB_EmployeeRecords, PartC_AttendancePortal) inside Tomcat’s webapps directory.

Start Tomcat using bin/startup.bat (Windows) or bin/startup.sh (Linux/Mac).

Access each part from the browser:

Part A (Login): http://localhost:8080/PartA_UserLogin/login.html
Part B (Employees): http://localhost:8080/PartB_EmployeeRecords/employees.html
Part C (Attendance): http://localhost:8080/PartC_AttendancePortal/attendance.jsp
Verify database connectivity and credentials in each Servlet file.


Nimbus Submission: Spring and Hibernate Applications
Overview
This submission contains three parts demonstrating Java applications using Spring and Hibernate:

Part A: Dependency Injection using Spring with Java-based configuration.
Part B: CRUD operations on a Student entity using Hibernate ORM with MySQL.
Part C: Banking system demonstrating transaction management using Spring and Hibernate.
Each part includes source code, configuration files, and instructions to run the application.

Directory Structure

NimbusSubmission/
│
├── PartA_SpringDI/
│   ├── src/main/java/com/example/di/
│   │   ├── config/AppConfig.java
│   │   ├── model/Course.java
│   │   ├── model/Student.java
│   │   └── MainApp.java
│
├── PartB_HibernateCRUD/
│   ├── src/main/java/com/example/hibernatecrud/
│   │   ├── model/Student.java
│   │   ├── dao/StudentDAO.java
│   │   └── MainApp.java
│   └── resources/hibernate.cfg.xml
│
├── PartC_SpringHibernateTransaction/
│   ├── src/main/java/com/example/banking/
│   │   ├── config/AppConfig.java
│   │   ├── model/Account.java
│   │   ├── model/Transaction.java
│   │   ├── dao/AccountDAO.java
│   │   ├── service/BankingService.java
│   │   └── MainApp.java
│   └── resources/hibernate.cfg.xml
│
└── README.md

Prerequisites
Java 17 or higher
Maven or manual JAR dependencies (Spring Core, Hibernate ORM, MySQL JDBC Driver)
MySQL installed and running
Database nimbusdb created for Parts B and C
Part A: Dependency Injection in Spring
Description
Demonstrates Dependency Injection using Spring annotations.
Student depends on Course.
Java-based configuration using @Configuration and @Bean.
How to Run
Navigate to PartA_SpringDI/src/main/java.
Compile all Java files:
javac -cp "path_to_spring_jars/*" com/example/di/*.java com/example/di/config/*.java com/example/di/model/*.java
Run the application:
java -cp ".:path_to_spring_jars/*" com.example.di.MainApp
Expected Output:

Student Name: John Doe
Enrolled in course: Artificial Intelligence
Part B: Hibernate CRUD Operations
Description
Performs Create, Read, Update, Delete operations on Student entity.
Uses Hibernate ORM with MySQL database.
Hibernate configuration in hibernate.cfg.xml.
How to Run
Make sure MySQL is running and nimbusdb exists. Update hibernate.cfg.xml with your username/password.
Navigate to PartB_HibernateCRUD/src/main/java.
Compile all Java files:
javac -cp "path_to_hibernate_jars/*:path_to_jpa_jars/*:path_to_mysql_connector/*" com/example/hibernatecrud/*.java com/example/hibernatecrud/model/*.java com/example/hibernatecrud/dao/*.java
Run the application:
java -cp ".:path_to_hibernate_jars/*:path_to_jpa_jars/*:path_to_mysql_connector/*" com.example.hibernatecrud.MainApp
Expected Output:

Adds sample students
Displays all students
Updates a student
Deletes a student
Shows final student list
Part C: Spring + Hibernate Transaction Management
Description
Banking system demonstrating transaction management using Spring and Hibernate.
BankingService ensures atomic money transfer between accounts.
Uses @Transactional annotation for declarative transactions.
How to Run
Make sure MySQL is running and nimbusdb exists. Update hibernate.cfg.xml with your credentials.
Navigate to PartC_SpringHibernateTransaction/src/main/java.
Compile all Java files:
javac -cp "path_to_spring_jars/*:path_to_hibernate_jars/*:path_to_jpa_jars/*:path_to_mysql_connector/*" com/example/banking/*.java com/example/banking/config/*.java com/example/banking/dao/*.java com/example/banking/model/*.java com/example/banking/service/*.java
Run the application:
java -cp ".:path_to_spring_jars/*:path_to_hibernate_jars/*:path_to_jpa_jars/*:path_to_mysql_connector/*" com.example.banking.MainApp
Expected Output:

Creates two accounts
Performs money transfer
Prints updated balances
If transfer fails (e.g., insufficient funds), the transaction is rolled back
Notes
All Spring beans are configured using Java-based configuration; no XML for Spring.
Hibernate sessions are managed manually in Parts B and C.
Ensure all dependencies are added to the classpath before compiling and running.
You can use Maven or Gradle for easier dependency management.


Online Student Management System
Overview
This is a Spring + Hibernate-based mini project for managing students, courses, and fee payments. It demonstrates:

Dependency Injection using Spring Java-based configuration
CRUD operations using Hibernate ORM
Transaction Management for fee payments and refunds
Integration of Spring + Hibernate in a layered architecture
The system provides a menu-driven console interface for performing operations like adding students, enrolling in courses, updating student data, deleting records, and handling payments and refunds.

Features
Student Management

Add, update, delete, and view students
Assign students to courses
Course Management

Add, update, delete, and view courses
Fee Management

Pay fees
Refund fees
Ensures atomic transactions with rollback in case of failure
Console Interface

Menu-driven for easy interaction
Real-time success/failure messages
Technologies Used
Java 11+
Spring Framework (Core, ORM, TX)
Hibernate ORM
MySQL / H2 Database
Maven for dependency management
Log4j for logging
Folder Structure
OnlineStudentManagementSystem/
│
├── src/main/java/com/osm/
│   ├── app/
│   │   └── MainApp.java
│   ├── config/
│   │   └── AppConfig.java
│   ├── dao/
│   │   ├── StudentDAO.java
│   │   ├── StudentDAOImpl.java
│   │   ├── CourseDAO.java
│   │   ├── CourseDAOImpl.java
│   │   └── PaymentDAO.java
│   ├── model/
│   │   ├── Student.java
│   │   ├── Course.java
│   │   └── Payment.java
│   └── service/
│       ├── FeeService.java
│       └── FeeServiceImpl.java
│
├── src/main/resources/
│   ├── hibernate.cfg.xml
│   ├── log4j.properties
│   └── schema.sql
│
├── pom.xml
└── README.md
Database Setup
Create a MySQL database:
CREATE DATABASE osm_db;
(Optional) Run schema.sql to create tables:
USE osm_db;
-- Run the script provided in resources/schema.sql
Update database credentials in hibernate.cfg.xml if necessary:
<property name="hibernate.connection.username">root</property>
<property name="hibernate.connection.password">password</property>
Running the Project
Clone the repository or download the project folder.
Open in IDE (IntelliJ IDEA or Eclipse).
Build with Maven:
mvn clean install
Run the application:
From IDE: Run MainApp.java
Or via terminal (if using Maven Shade plugin):
java -jar target/OnlineStudentManagementSystem-1.0-SNAPSHOT.jar
Interact via console menu:
=== Online Student Management System ===
1. Add Student
2. View Student by ID
3. View All Students
4. Pay Fee
5. Refund Fee
0. Exit
Enter your choice:
Follow prompts to perform operations.
Notes
Transaction management ensures atomic payments/refunds.
Hibernate will auto-create/update tables using hbm2ddl.auto=update.
For testing without MySQL, you can switch to H2 in-memory database.

