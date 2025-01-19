### Zomato Order Management System
Overview
This project is a Zomato Order Management System built using Flask, MySQL, and HTML. It allows users to place orders and view all orders through a web interface. The project demonstrates basic CRUD operations with a focus on order placement and retrieval.

### Features
Order Placement: Users can place orders by sending JSON data containing the cart items and delivery address.

View Orders: Users can view all placed orders.

Database Integration: Uses MySQL for data storage and retrieval.

### Getting Started
Prerequisites
Python 3.x

Flask

MySQL

HTML

### Installation
Clone the Repository: Clone the project repository to your local machine.

bash
git clone https://github.com/your-username/zomato-order-management.git
Install Dependencies: Install the required Python packages using pip.

bash
pip install flask mysql-connector-python
### Set Up MySQL:

Create a MySQL database named zomato.

Create the necessary tables for items and orders:

sql
CREATE TABLE items (
    item_id INT AUTO_INCREMENT PRIMARY KEY,
    item_name VARCHAR(255) NOT NULL
);

CREATE TABLE orders (
    order_id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    item_id INT,
    quantity INT,
    delivery_address TEXT
);
### Configure MySQL Credentials: Update the MySQL credentials in the create_connection function in your script.

python
def create_connection():
    return mysql.connector.connect(
        host='localhost',
        user='root',  # replace with your MySQL username
        password='admin',  # replace with your MySQL password
        database='zomato'
    )
Run the Application: Start the Flask application.

bash
python app.py
Usage
Place an Order: Send a POST request to the /place_order endpoint with JSON data containing the cart items and delivery address.

json
{
    "cart": [
        {"name": "Pizza", "quantity": 2},
        {"name": "Burger", "quantity": 1}
    ],
    "address": "123 Street, City, Country"
}
View Orders: Send a GET request to the /orders endpoint to retrieve all placed orders.

### File Structure
.
├── app.py             # Main application file
├── templates
│   └── index.html     # Home page template
└── README.md          # Project README file
### Contributing
We welcome contributions! If you'd like to contribute, please follow these steps:

Fork the repository and create your branch.

Commit your changes.

Push to the branch.

Open a pull request.
