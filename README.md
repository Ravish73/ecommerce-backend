# 🛒 E-Commerce Backend (Spring Boot)

## 🚀 Project Overview

This is a full-featured **E-Commerce Backend Application** built using **Spring Boot**.
It includes authentication, cart management, payment integration using PayPal, and order processing.

---

## 🔥 Features

### 🔐 Authentication & Security

* JWT-based authentication
* Secure APIs using Spring Security
* Role-based access (USER / ADMIN)

---

### 🛍️ Product Management

* View all products
* Admin can add/update/delete products
* Stock management

---

### 🛒 Cart System

* Add product to cart
* View cart items
* Update quantity
* Remove items from cart

---

### 💳 Payment Integration

* PayPal Sandbox integration
* Payment approval via PayPal UI
* Handles success & cancel flow

---

### 📦 Order Management

* Create order after successful payment
* Store order items
* Reduce product stock
* Clear cart after order

---

### 📜 Order History

* Fetch all orders of logged-in user

---

## 🧰 Tech Stack

* Java
* Spring Boot
* Spring Security (JWT)
* Hibernate / JPA
* MySQL
* PayPal Sandbox API

---

## ⚙️ How to Run the Project

1. Clone repository
2. Open in IDE (IntelliJ / Eclipse)
3. Configure database in `application.properties`
4. Add PayPal sandbox credentials
5. Run Spring Boot application

---

## 🔑 Authentication APIs

### ✅ Register

POST `/api/auth/register`

```json
{
  "name": "Ravi",
  "email": "test@gmail.com",
  "password": "pass123",
  "role": "ROLE_USER"
}
```

---

### ✅ Login

POST `/api/auth/login`

```json
{
  "username": "test@gmail.com",
  "password": "pass123"
}
```

👉 Copy JWT token from response

---

## 🛒 Cart APIs

### ➕ Add to Cart

POST `/api/cart/add`

Headers:

```
Authorization: Bearer <JWT_TOKEN>
```

Body:

```json
{
  "productId": 1,
  "quantity": 2
}
```

---

###  View Cart

GET `/api/cart`

Headers:

```
Authorization: Bearer <JWT_TOKEN>
```

---

### Update Quantity

PUT `/api/cart/update?itemId=1&quantity=3`

---

### ❌ Remove Item

DELETE `/api/cart/remove?itemId=1`

---

## 💳 Payment API

### 🧾 Create Payment

GET `/api/paypal/pay`

Headers:

```
Authorization: Bearer <JWT_TOKEN>
```

👉 Returns PayPal approval URL

---

### 💰 Complete Payment

1. Open returned PayPal URL
2. Login using sandbox account
3. Click **Pay Now**
4. Redirect to success API

---


Headers:

```
Authorization: Bearer <JWT_TOKEN>
```

---

## 🧪 How to Test Full Flow

1. Register user
2. Login → get JWT token
3. Add product to cart
4. View cart
5. Call `/api/paypal/pay`
6. Open PayPal link in browser
7. Login with sandbox account
8. Click **Pay Now**
9. Order created successfully
10. Check `/api/orders`

---

## 💳 PayPal Sandbox Credentials (For Testing)

⚠️ These are TEST accounts (no real money)

Buyer Account:

```
Email: sb-j7eko50199144@personal.example.com
Password: 2nn#m)+W
```

---

## 📌 Notes

* Do NOT use real PayPal account
* Use sandbox only
* JWT token required for protected APIs

---

## 🏆 Key Highlights

* Complete real-world e-commerce flow
* Secure authentication system
* Payment gateway integration
* Clean layered architecture (Controller → Service → Repository)

---

## 👨‍💻 Author

Raviraj Raje
