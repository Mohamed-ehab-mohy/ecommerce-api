# Ecommerce API — Laravel (Sanctum Auth + CRUD Products)

This is a basic Laravel RESTful API that supports:
- User registration & login using Laravel Sanctum
- CRUD operations for Products
- Image upload support for products
- Authentication-protected endpoints

---

## 🛠️ Technologies Used

- PHP 8
- Laravel 10+
- Sanctum (for API token authentication)
- MySQL (or any other DB)
- Postman for testing

---

## 📦 Features

### ✅ Authentication
- `POST /api/register` → Register a new user
- `POST /api/login` → Login and receive token
- `POST /api/logout` → Logout (requires Bearer token)
- `GET /api/user` → Get authenticated user info (requires token)

### ✅ Product Endpoints (Protected)
- `GET /api/products` → Get all products
- `POST /api/products` → Create new product (with image upload)
- `GET /api/products/{id}` → Show single product
- `PUT /api/products/{id}` → Update product
- `DELETE /api/products/{id}` → Delete product

---

## 🔐 Sanctum Authentication

To access protected routes:
1. Register/Login to get a token.
2. Pass the token as Bearer token in Postman or any HTTP client.

Example:
```http
Authorization: Bearer YOUR_TOKEN_HERE
🗃️ Database Schema: products
Column	Type	Description
id	BIGINT	Primary key
name	VARCHAR	Product name
description	TEXT	Optional
price	DECIMAL	Product price
quantity	INTEGER	Stock quantity
image	VARCHAR	Path to image file
timestamps	TIMESTAMP	created_at, updated_at

📤 Image Upload
While creating a product, use form-data in Postman:

name, price, quantity, description (optional) as text

image as File

Uploaded images are stored under storage/app/public/products

📁 Folder Structure
app/Http/Controllers/API/AuthController.php – Auth logic

app/Http/Controllers/ProductController.php – CRUD logic

routes/api.php – API routes

app/Models/Product.php – Product model

database/migrations/...create_products_table.php – Initial schema

✅ Setup Instructions
bash
Copy
Edit
git clone https://github.com/yourusername/ecommerce-api.git
cd ecommerce-api

composer install
cp .env.example .env
php artisan key:generate

# Set DB credentials in .env

php artisan migrate
php artisan storage:link

php artisan serve
🧪 Example Test (Postman)
Register/login → copy token.

Set token in Authorization header.

Test product endpoints.
