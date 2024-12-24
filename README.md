Flask User Management API
Description
This project is a Flask web application that provides basic user management functionality. Users can be added to the system, and their details can be viewed. The application interacts with a MySQL database to store user information, such as name, email, and role.

Features
1.View a list of all users.
2.Add new users with details like name, email, and role.
3.View user details by ID.
4.Basic form validation and flash messaging for feedback.

Prerequisites
1.Python 3.x
2.MySQL server
3.A MySQL database with the necessary table for storing user data.

Installation
1.Clone the repository:

git clone https://github.com/shreyash1231/Assignment.git
2.Set up your MySQL database:

Log into MySQL and create a database named users (or update db_config in app.py for a different name).

Run the following SQL query to create a users table:

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    role VARCHAR(50) NOT NULL
);
3.Update the database connection details in app.py:

Change the values in the db_config dictionary to match your MySQL credentials.
db_config = {
    'host': 'localhost',
    'user': 'root',      # Your MySQL username
    'password': 'your_password',  # Your MySQL password
    'database': 'users'  # Your database name
}
4.Install the Library

pip install Flask mysql-connector-python
5.Run the Flask application:

python app.py
The application should now be running at http://127.0.0.1:5000/.

Endpoints
1.GET /hello:

Returns the message "Hello World!"
2.GET /users:

Retrieves a list of all users stored in the MySQL database.
3.POST /new_user:

Creates a new user. Requires name, email, and role fields in the form. Displays a success or error message upon form submission.
4.GET /users/{id}:

Retrieves details of a user with a specific id. If the user does not exist, it returns a "User not found!" message.
Database Schema
The database schema includes a single table, users, with the following columns:

1.id: The unique identifier for each user (auto-incremented).
2.name: The name of the user (string).
3.email: The email address of the user (string, must be unique).
4.role: The role assigned to the user (string).
To populate the table with sample data, you can run the following SQL:

INSERT INTO users (name, email, role) VALUES
('Alice', 'alice@example.com', 'Admin'),
('Bob', 'bob@example.com', 'User');
Git Workflow
1.Initialize a new Git repository:

git init
2.Create a branch named assignment for your work:

git checkout -b assignment
3.Add files and make commits as you work on the Flask API and database functionality.

git add .
git commit -m "Implemented user management API"
4.Push the assignment branch to GitHub:

git push origin assignment
5.Create a pull request on GitHub from the assignment branch to the main branch.

Additional Dependencies
1.Flask: A micro web framework used for building the application.
2.MySQL Connector: A library used to interact with the MySQL database.
Flask==2.2.2
mysql-connector-python==8.0.30
Contributing
1.Fork the repository.
2.Create a branch for your feature (git checkout -b feature-name).
3.Commit your changes (git commit -am 'Add new feature').
4.Push the branch (git push origin feature-name).
5.Create a pull request.
