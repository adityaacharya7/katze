# Katze - Pet Supplies E-commerce Website

Katze is a PHP-based e-commerce platform for selling pet supplies. It provides a complete online shopping experience, from browsing products to checking out. The project also includes features for user authentication, an adoption page, and a news section.

## Contributors

  * **[Aditya Acharya](https://www.linkedin.com/in/adityaacharyax/)**
  * **[Anamika Ashokkumar](https://www.linkedin.com/in/anamika-ashokkumar-100a232a5/)**
  * **[Tanmay Gawade](https://www.linkedin.com/in/tanmaygawade2005/)**

## Features

  * **User Authentication:** Secure user registration and login system with password hashing.
  * **Product Catalog:** Browse and search for pet supplies.
  * **Shopping Cart:** Add, remove, and manage items in the shopping cart.
  * **Checkout Process:** A multi-step checkout process with billing and shipping address forms.
  * **Adoption Page:** A dedicated page for pet adoption.
  * **News Section:** Keep users updated with the latest news.
  * **Contact Form:** A form for users to get in touch.
  * **Geolocation:** Detects the user's location to provide a personalized experience.

## Technologies Used

### Backend

  * PHP
  * MySQL
  * [PHPMailer](https://github.com/PHPMailer/PHPMailer) for sending emails.

### Frontend

  * HTML5
  * CSS3
  * JavaScript
  * [Bootstrap 4](https://getbootstrap.com/docs/4.6/getting-started/introduction/)
  * [jQuery](https://jquery.com/)
  * [Owl Carousel](https://owlcarousel2.github.io/OwlCarousel2/)
  * [Magnific Popup](https://dimsemenov.com/plugins/magnific-popup/)

## Setup and Installation

1.  **Prerequisites:**

      * A web server with PHP support (e.g., XAMPP, WAMP, or MAMP).
      * MySQL database.
      * [Composer](https://getcomposer.org/) for managing PHP dependencies.

2.  **Clone the repository:**

    ```bash
    git clone https://github.com/your-username/katze.git
    ```

3.  **Install dependencies:**

    ```bash
    composer install
    ```

4.  **Database Setup:**

      * Create a new database named `katze` in your MySQL server.
      * Import the `katze.sql` file (you'll need to create this file with the schema below) into the `katze` database.

5.  **Configuration:**

      * Update the database credentials in `db_connect.php` and `connect.php`:
        ```php
        $host = 'localhost';
        $user = 'your_db_user';
        $password = 'your_db_password';
        $database = 'katze';
        ```

6.  **Run the application:**

      * Place the project directory in your web server's root directory (e.g., `htdocs` for XAMPP).
      * Open your web browser and navigate to `http://localhost/katze` (or the appropriate URL for your setup).

## Database Schema

The database `katze` contains the following tables:

### `users`

| Column | Type | Description |
| --- | --- | --- |
| `id` | INT(11) | Primary Key, Auto Increment |
| `username` | VARCHAR(255) | User's name |
| `email` | VARCHAR(255) | User's email address (unique) |
| `password` | VARCHAR(255) | Hashed password |
| `remember` | TINYINT(1) | Remember me flag (0 or 1) |

### `medicines`

| Column | Type | Description |
| --- | --- | --- |
| `medicine_id` | INT(11) | Primary Key, Auto Increment |
| `name` | VARCHAR(255) | Name of the medicine/product|
| `price` | DECIMAL(10,2)| Price of the product |
| `image_url` | VARCHAR(255) | URL of the product image |

### `cart`

| Column | Type | Description |
| --- | --- | --- |
| `id` | INT(11) | Primary Key, Auto Increment |
| `user_id` | INT(11) | Foreign Key to `users` table (`id`) |
| `medicine_id`| INT(11) | Foreign Key to `medicines` table (`medicine_id`) |
| `quantity` | INT(11) | Quantity of the product in the cart |

## File Structure

```
.
├── assets/            # CSS, JS, images, and other assets
├── vendor/            # Composer dependencies
├── about.php          # About page
├── add_to_cart.php    # Logic to add items to the cart
├── adoptionpage.php   # Adoption page
├── cart.php           # Shopping cart page
├── checkout.php       # Checkout page
├── checkoutphp.php    # Logic for the checkout process
├── composer.json      # PHP dependencies
├── connect.php        # Database connection and login logic
├── db_connect.php     # Database connection
├── index.php          # Home page
├── login_page.php     # Login page
├── logout.php         # Logout logic
├── medicines.php      # (Assumed) Page to display medicines
├── news.php           # News page
├── remove_from_cart.php# Logic to remove items from the cart
├── shop.php           # Shop/products page
├── signup.php         # Signup logic
└── README.md          # This file
```
