This is a straightforward yet effective student management system, designed as a desktop application for a school project. The system leverages the JDBC (Java Database Connectivity) driver and incorporates the Java Swing framework, particularly the JFrame class, to create a user-friendly graphical interface.


With the JDBC driver, the application seamlessly connects to a database, facilitating the storage and retrieval of student information. This ensures that data management is efficient and organized. The use of a database allows for easy scalability and adaptability to handle a growing amount of student records.
1. Install Visual Studio Code:

Make sure you have Visual Studio Code installed on your system. You can download it from the official website: Visual Studio Code.


2. Install Java Development Kit (JDK):

Ensure that you have Java Development Kit installed on your machine. You can download it from the official Oracle website or use OpenJDK.


3. Install Java Extension Pack:
Install the “Java Extension Pack” in VS Code. This pack includes essential extensions for Java development. You can find it in the Extensions view (Ctrl+Shift+X or Cmd+Shift+X) by searching for “Java Extension Pack.”


4. Configure JDK in VS Code:

Set up the Java Development Kit in VS Code. You can do this by going to File > Preferences > Settings (Ctrl+, or Cmd+,) and searching for “Java Home.” Set the path to your JDK installation.


Folder Structure

The workspace contains two folders by default, where:


src: the folder to maintain sources
lib: the folder to maintain dependencies
A simple Java Swing application for handling student data. You may add, remove, and search for student records.


Features

Add Student Records:
The application provides a comprehensive form for users to add new student records. This form captures vital details, including:
Name: Full name of the student.
ID: A unique identifier for each student.
Grade: Academic grade or class of the student.
Date of Birth: The birthdate of the student.
Gender: Male, female, or other.
Contact: Phone number of the student or guardian.
Email: Email address for communication.
Upon submitting the form, the data is validated for completeness and correctness before being added to the MySQL database.
Reset Form Fields:
To enhance user experience, a “Reset” button is implemented to clear all form fields, allowing users to start afresh or correct any input errors.
Delete Student Records:
Deleting a student record is a straightforward process. Users can select a student from the displayed list and choose the “Delete” option.
A confirmation prompt ensures that users do not accidentally delete records. Once confirmed, the corresponding entry is removed from the database.
earch for a Student by ID:
The application offers a search functionality that allows users to find specific student records by entering the student’s ID.
The search result is displayed prominently, showing all relevant information about the student.
Connects to a MySQL Database:
The application leverages JDBC to connect seamlessly to a MySQL database. This ensures the persistent storage and retrieval of student data.
The database schema includes tables for student information, and the application handles database connection, insertion, deletion, and retrieval operations.
User-Friendly GUI:
The graphical user interface (GUI) is designed using Java Swing components, providing an intuitive and visually appealing layout.
Tabs or panels organize different sections of the application, creating a seamless user experience.
Prerequisites

Before running the application, you need the following:


Java Development Kit (JDK)
MySQL Server
MySQL Connector/J library (JDBC driver)
A MySQL database named “student”
A MySQL user with the username “root” and password “user” (You can modify the database credentials in the code)
Xampp server or Mysql Workbench

MySQL Setup

Open a MySQL client (e.g., MySQL Workbench or the MySQL
To list all databases, run the following command:

SHOW DATABASES;
Copy

Create a new database named “student” if it doesn’t already exist:

CREATE DATABASE student;
Copy

Switch to the “student” database:

USE student;
Copy

Verify that you’re in the “student” database:

SELECT DATABASE();
Copy

Create a table named “students” to store student records. The table structure should match the fields you have in your Java application (name, ID, grade, date of birth, gender, contact, and email). Here’s an example table structure:
CREATE TABLE students (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255),
    student_id VARCHAR(255) UNIQUE,
    grade VARCHAR(255),
    date_of_birth DATE,
    gender VARCHAR(10),
    contact VARCHAR(20),
    email VARCHAR(255)
);
Copy

You can view the table structure with:

DESCRIBE students;
Copy

Now you have the “student” database and the “students” table ready to use with your Java application.
Installation

Download Zip file:
Open the project in your preferred Java IDE (e.g., VS Code, IntelliJ IDEA, or Eclipse).
Configure your MySQL database settings in the code:

private static final String DB_URL = "jdbc:mysql://localhost:3306/student";
private static final String DB_USER = "root";
private static final String DB_PASSWORD = "root";
Copy

Run the application.
Usage

Launch the application.
Enter student details, such as name, ID, grade, date of birth, gender, contact, and email.
Click the “Add Student” button to add a student record.
Use the “Reset” button to clear the input fields.
Select a record in the table and click the “Delete Record” button to remove it.
Use the “Search by ID” field to search for a student by ID.
