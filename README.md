Ecommerce Product API with Laravel
This project is a simple RESTful API built with Laravel that allows users to register, log in, and manage products (CRUD operations). It also supports image upload and token-based authentication using Laravel Sanctum.
Features
•	• User Registration & Login (Token-based)
•	• Authenticated Routes with Laravel Sanctum
•	• Create / Read / Update / Delete Products
•	• Upload product image (stored in storage/app/public)
•	• Basic validation for inputs
Tech Stack
•	• PHP 8.x
•	• Laravel 10/11/12 (depending on your version)
•	• Laravel Sanctum
•	• MySQL
•	• Postman (for testing API endpoints)
API Endpoints
Authentication
POST /api/register - Register a new user
POST /api/login - Login and get token
POST /api/logout - Logout (requires token)
GET /api/user - Get current user info (requires token)
Products
GET /api/products - List all products
GET /api/products/{id} - Get a single product
POST /api/products - Create a product (auth required)
PUT /api/products/{id} - Update a product (auth required)
DELETE /api/products/{id} - Delete a product (auth required)
Product creation supports multipart/form-data with an image field.
How to Run Locally
•	• Clone the repo:
  git clone https://github.com/yourusername/ecommerce-api.git
  cd ecommerce-api
•	• Install dependencies:
  composer install
•	• Create .env and set your DB credentials:
  cp .env.example .env
  php artisan key:generate
•	• Run migrations:
  php artisan migrate
•	• Serve the app:
  php artisan serve
•	• Link storage for image uploads (optional):
  php artisan storage:link
Testing with Postman
Use form-data for product creation with:
- name
- description
- price
- quantity
- image (type: File)
Author
Mohamed Ehab
Laravel Backend Developer
