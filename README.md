Flask User Management API
Description
This project is a Flask web application that provides basic user management functionality. Users can be added to the system, and their details can be viewed. The application interacts with a MySQL database to store user information, such as name, email, and role.

Features
View a list of all users.
Add new users with details like name, email, and role.
View user details by ID.
Basic form validation and flash messaging for feedback.
Prerequisites
Python 3.x
MySQL server
A MySQL database with the necessary table for storing user data.
Installation
Clone the repository:

git clone https://github.com/shreyash1231/Assignment.git
Set up your MySQL database:

Log into MySQL and create a database named users (or update db_config in app.py for a different name).

Run the following SQL query to create a users table:

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    role VARCHAR(50) NOT NULL
);
Update the database connection details in app.py:

Change the values in the db_config dictionary to match your MySQL credentials.
db_config = {
    'host': 'localhost',
    'user': 'root',      # Your MySQL username
    'password': 'your_password',  # Your MySQL password
    'database': 'users'  # Your database name
}
Install the Library

pip install Flask mysql-connector-python
Run the Flask application:

python app.py
The application should now be running at http://127.0.0.1:5000/.

Endpoints
GET /hello:

Returns the message "Hello World!"
GET /users:

Retrieves a list of all users stored in the MySQL database.
POST /new_user:

Creates a new user. Requires name, email, and role fields in the form. Displays a success or error message upon form submission.
GET /users/{id}:

Retrieves details of a user with a specific id. If the user does not exist, it returns a "User not found!" message.
Database Schema
The database schema includes a single table, users, with the following columns:

id: The unique identifier for each user (auto-incremented).
name: The name of the user (string).
email: The email address of the user (string, must be unique).
role: The role assigned to the user (string).
To populate the table with sample data, you can run the following SQL:

INSERT INTO users (name, email, role) VALUES
('Alice', 'alice@example.com', 'Admin'),
('Bob', 'bob@example.com', 'User');
Git Workflow
Initialize a new Git repository:

git init
Create a branch named assignment for your work:

git checkout -b assignment
Add files and make commits as you work on the Flask API and database functionality.

git add .
git commit -m "Implemented user management API"
Push the assignment branch to GitHub:

git push origin assignment
Create a pull request on GitHub from the assignment branch to the main branch.

Additional Dependencies
Flask: A micro web framework used for building the application.
MySQL Connector: A library used to interact with the MySQL database.
Flask==2.2.2
mysql-connector-python==8.0.30
Contributing
Fork the repository.
Create a branch for your feature (git checkout -b feature-name).
Commit your changes (git commit -am 'Add new feature').
Push the branch (git push origin feature-name).
Create a pull request.
