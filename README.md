Customer Feedback Portal
Overview
The Customer Feedback Portal allows users to submit feedback and view feedback statistics.
    Admins can view total feedback, average ratings, and rating distributions. This project is built using 
    Spring Boot, Thymeleaf, and MySQL/PostgreSQL for the back-end, and HTML, CSS, and JavaScript for the front-end.
Features

    - Customer Feedback Submission: Users can submit feedback with a rating and a text comment.
    - Admin Dashboard: Displays feedback statistics, including the total number of feedback submissions, average rating, and rating distribution.
    - Feedback List: Users can view a list of their submitted feedback with ratings and comments.
    - Data Persistence: Feedback is stored in a MySQL or PostgreSQL database.
    
Tech Stack

    - Backend: Spring Boot, Thymeleaf, JPA/Hibernate, MySQL/PostgreSQL
    - Frontend: HTML, CSS, JavaScript
    - Unit Testing: JUnit 5
    
Installation Instructions
Step 1: Clone the Repository

    git clone https://github.com/yourusername/customer-feedback-portal.git
    cd customer-feedback-portal
    
Step 2: Set Up the Database

    1. MySQL Database Setup:
        - Create a new database in MySQL 
        - Update the database connection details in src/main/resources/application.properties or application.yml.

    2. Run the Database Script (Optional):
        - If you need to set up the initial database schema, run the SQL schema provided in schema.sql.
    
Step 3: Build the Project

    If you are using Maven, run the following command to build the project:

    mvn clean install
    
Step 4: Start the Application

    Run the Spring Boot application:

    mvn spring-boot:run

    The application should be accessible at:

    - Feedback Form: http://localhost:8080/feedbackForm
    - Admin Dashboard: http://localhost:8080/admin/feedbacks
    - Feedback List: http://localhost:8080/feedbackList
    
Unit Testing

    Unit tests are written using JUnit 5. To run the tests:

    mvn test

    A test report will be generated under the target/site directory in the surefire-report folder.
    

File Structure

├── src/
│   ├── main/
│   │   ├── java/
│   │   │   ├── com/
│   │   │   │   ├── CustomerFeedback/
│   │   │   │   │   ├── Controller/
│   │   │   │   │   ├── Entity/
│   │   │   │   │   ├── Repository/
│   │   │   │   │   ├── Services/
│   │   ├── resources/
│   │   │   ├── application.properties
│   │   │   ├── templates/
│   │   │   ├── static/
│   ├── test/
│   │   ├── java/
│   │   │   ├── com/
│   │   │   │   ├── CustomerFeedback/
│   │   │   │   │   ├── Controller/
│   │   │   │   │   ├── Services/
├── pom.xml

Database Schema
Feedback Table Schema

    To set up the database for this application, use the following SQL schema. 
    This will create a feedback table to store user-submitted feedback:

    CREATE DATABASE feedback_db;

    USE feedback_db;

    CREATE TABLE feedback (
        id BIGINT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(255) NOT NULL,
        email VARCHAR(255) NOT NULL,
        feedbackText VARCHAR(500) NOT NULL,
        rating INT NOT NULL,
        submissionDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP
    );

    
Example Data:

    INSERT INTO feedback (name, email, feedbackText, rating)
    VALUES 
    ('John Doe', 'john.doe@example.com', 'Great service, I am very satisfied!', 5),
    ('Jane Smith', 'jane.smith@example.com', 'The product quality could be improved.', 3),
    ('Alice Brown', 'alice.brown@example.com', 'Good experience, will return again!', 4);

Additional Information

    - Ensure you have JDK 11+ installed on your machine to run the Spring Boot application.
    - For database setup, you can use either MySQL 
    
