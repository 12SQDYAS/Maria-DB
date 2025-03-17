# Maria-DB
# First of all link your Sales data to maria-db using python

##Step 1:
import pandas as pd

##Step 2:
import mariadb
import pandas as pd

# Database connection details
config = {
    "host": "127.0.0.1",
    "port": 3306,
    "user": "root",
    "password": "datascience1234",
    "database": "mysql"
}

create_table_query = """
CREATE TABLE IF NOT EXISTS sales_data (
    invoice_id VARCHAR(20) NOT NULL PRIMARY KEY,
    branch CHAR(1) NOT NULL,
    city VARCHAR(50) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    product_line VARCHAR(50) NOT NULL,
    unit_price FLOAT NOT NULL,
    total FLOAT NOT NULL,
    rating FLOAT NOT NULL
);
"""

csv_file_path = r"C:\Users\dell\Downloads\data.csv"

try:
    # Step 1: Connect to MariaDB
    connection = mariadb.connect(**config)
    cursor = connection.cursor()

    # Step 2: Create the table
    cursor.execute(create_table_query)
    print("Table 'sales_data' created successfully.")

    # Step 3: Load data from CSV using pandas
    data = pd.read_csv(csv_file_path)

    # Debug: Print the columns to check names
    print("CSV Columns:", data.columns)

    # Standardize column names (optional but helpful)
    data.columns = data.columns.str.strip().str.lower()
    print("Standardized Columns:", data.columns)

    # Ensure columns match the database schema
    expected_columns = ['invoice_id', 'branch', 'city', 'gender', 'product_line', 'unit_price', 'total', 'rating']
    print("Expected Columns:", expected_columns)

    # Match the DataFrame with the expected schema
    data = data[expected_columns]

    # Step 4: Insert data into the table
    insert_query = """
    INSERT INTO sales_data (invoice_id, branch, city, gender, product_line, unit_price, total, rating)
    VALUES (?, ?, ?, ?, ?, ?, ?, ?)
    """
    for _, row in data.iterrows():
        cursor.execute(insert_query, tuple(row))

    # Commit the transaction
    connection.commit()
    print("Data inserted successfully.")

except KeyError as ke:
    print(f"Column mismatch error: {ke}")
except mariadb.Error as e:
    print(f"Database error: {e}")
finally:
    # Close resources
    if cursor:
        cursor.close()
    if connection:
        connection.close()

##Step 3

import mariadb

# Database connection details
config = {
    "host": "127.0.0.1",        # Hostname
    "port": 3306,               # Port
    "user": "root",             # Username
    "password": "datascience1234",  # Password
    "database": "mysql"         # Database name
}

# SQL query to create the table
create_table_query = """
CREATE TABLE IF NOT EXISTS sales_data (
    invoice_id VARCHAR(20) NOT NULL PRIMARY KEY,
    branch CHAR(1) NOT NULL,
    city VARCHAR(50) NOT NULL,
    gender VARCHAR(10) NOT NULL,
    product_line VARCHAR(50) NOT NULL,
    unit_price FLOAT NOT NULL,
    total FLOAT NOT NULL,
    rating FLOAT NOT NULL
);
"""

try:
    # Step 1: Connect to MariaDB
    connection = mariadb.connect(**config)
    cursor = connection.cursor()

    # Step 2: Create the table
    cursor.execute(create_table_query)
    print("Table 'sales_data' created successfully.")

except mariadb.Error as e:
    print(f"Error: {e}")

finally:
    # Close resources
    if cursor:
        cursor.close()
    if connection:
        connection.close()
