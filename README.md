# Securely Connect Python to PosgreSQL with Psycopg2 Using .env Files

Today, I’m working on connecting to a PostgreSQL database with Python. This beginner data engineering project involves setting up a connection between Python using Psycopg2, and PostgreSQL.

This project is ideal because it offers hands-on experience with both SQL and Python.

This Python SQL Connector allows me to build data models in SQL, and then use Python to query these data models and perform data analysis, visualisation or automate data manipulation tasks.

Not only does this project strengthen my skills in SQL and Database Design, but also enhances my ability to manipulate and interpret data with Python.

## Pre-Requisites

* **Create a Project Folder:** "python_sql_connector"
* **Setup Conda Environment:** Make sure to install "psycopg2", "python-dotenv" and "Jupyter" is installed
* **Create a .env file:** Make sure my database credentials are stored securely in a ".env" file
* **Import Libraries:** Make sure "psycopg2", "os" and "load_dotenv" are imported into the notebook

## Create .env File

To connect to the database, I need to provide sensitive information such as the database host, name, user, and password.

Storing my database credentials in a ".env" file ensures they are kept secure and away from my code.

To create the file, I simply used Notepad to store the sensitive information needed to connect to my PostgreSQL database. I formatted this information like this:

DB_HOST=localhost
DB_NAME=your_database_name
DB_USER=your_username
DB_PASSWORD=your_password

Next, I saved the file in the project folder as .env, for example, "python_sql_connector.env".

Finally, to keep my credentials safe, I added the ".env" file to my ".gitignore" to ensure my database credentials remain secure and not exposed in version control.

## Import Libraries

Once my Conda environment was set up and my .env file was created, I launched Jupyter Notebook, the environment used to import the necessary libraries for the project and establish the connection to the PostgreSQL database.

## Import PostgreSQL Credentials from .env with python-dotenv

To begin the process of connecting to the database, I specified the file containing my database credentials in the variable "dotenv_path". This ".env" file is located in my project folder and holds the sensitive information needed to establish the connection.

I then used an "if" statement in conjunction with the "load_dotenv " function to load my database credentials from the ".env" file. This approach not only attempts to load the credentials but also provides a visual confirmation of whether the loading process was successful.

If the credentials were loaded successfully, I receive a confirmation message; otherwise, a warning is displayed indicating a failure to load the credentials.

## Access Credentials from .env Using os

Once the ".env" file is loaded successfully, I need to then access these credentials so that I can pass them into psycopg2's connect function.

To achieve this, I used "os.getenv" to access and store the database credentials in variables. Although I could have hardcoded these credentials directly into the "psycopg2.connect" function, which is the next step, using "python-dotenv" and "os" keeps the credentials secure and separate from my code.

## Connect to PostgreSQL Database

To connect to the database, I use the "psycopg2.connect" function which establishes a connection to the PostgreSQL database using the credentials stored in the environment variables.

I have then used "autocommit=True" to ensure that each SQL statement made is immediately committed to the database.

Finally, I enclosed the connection setup in a "try/except" block to handle any potential errors that may arise when connecting to PostgreSQL. This also allowed me to see clear print messages indicating whether the connection was successful or if an error had occurred.

## Creating and Using a Database Cursor

Now that I had successfully connected to my PostgreSQL database in Python, the next step was to create a cursor, stored in the variable "curr".

This cursor is used to execute SQL statements. I have also enclosed this cursor creation in a "try/except" block to handle any potential errors that may arise.

Once I received the successful print message, I completed the Python-PostgreSQL connection process and could now start querying and manipulating data using Python, as well as directly interacting with the database.
