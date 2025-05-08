# Softtrine Task - Product Management System

A full-stack web application for managing products with role-based login functionality for **Admin** and **User** roles. Built using React.js, Express.js, and MySQL.


## 📁 Project Structure

```
Softtrine_Task/
├── Backend/
│   ├── index.js             # Express backend
│   ├── package.json
├── Frontend/
│   ├── src/
│   │   ├── Components/
│   │   │   ├── Login.jsx
│   │   │   ├── Signup.jsx
│   │   │   ├── Seller.jsx
│   │   │   └── User.jsx
│   │   ├── Store.jsx
│   │   ├── main.jsx
│   │   ├── App.jsx
│   ├── public/
│   ├── package.json
```

---

## 🛠 Tech Stack

- **Frontend:** React.js, React Router, Axios, Bootstrap
- **Backend:** Node.js, Express.js, MySQL2
- **Database:** MySQL
- **Middleware:** CORS, Body-Parser

---

## 🚀 Features

- ✅ User & Admin login with role selection
- ✅ Admin can:
  - Add, Edit, Delete products
  - Toggle product availability status
  - Filter & search products by type/name
- ✅ User can:
  - View product listings
- ✅ Role-based navigation using React Router
- ✅ Responsive UI with Bootstrap

---

## 🧑‍💻 Getting Started
## Backend: Express Server (Node.js)

### Server Setup

- The backend is built using **Express.js** to handle HTTP requests.
- **MySQL** connection is established using the `mysql2` package.
- The server listens on port `5000`.
- **CORS** middleware is used to allow requests from different origins.
- **Body Parser** middleware is used to parse incoming JSON requests.

### API Routes

1. **/login**: Used for authenticating users.
2. **/products**: Handles product management operations (add, update, delete, and fetch product data).
    - **POST**: Add a new product.
    - **PUT**: Update an existing product.
    - **DELETE**: Delete a product.
    - **PATCH**: Toggle product status (active/inactive).

## Frontend: React Application

### App Setup

- React components are used to build the UI, with the following key components:
  - **Login**: For user authentication.
  - **Seller (Admin)**: For managing products (add, edit, delete, view).
  - **Signup**: For new user registration.
  - **User**: For user-specific functionalities.
- Routing is managed using **React Router**.
- The app handles dynamic routing for different user roles (`admin`/`user`).

### Login Component

- The user submits the login form with their **email**, **password**, and **role** (user/admin).
- Upon submission, the `handleLogin` function makes a **POST** request to the backend (`/login`).
- If login is successful, a **JWT token** and user role are stored in `localStorage`.
- The user is redirected to the appropriate page (`/admin` or `/user`) based on their role.

### Seller Component (Admin Functionality)

- Admin users can:
  - View a list of products in a table.
  - Search for products by name.
  - Filter products by type.
  - Edit product details (name, details, price, etc.).
  - Toggle product status between **Active** and **Inactive**.
  - Delete products from the system.
- A **modal** is used for adding or editing products, communicating with the backend via **POST**, **PUT**, and **DELETE** requests.

### State Management

- The app uses React's **useState** hook to manage state such as form data and product details.
- The **useEffect** hook is used to fetch products from the database and filter them based on search criteria and selected product type.

## Database Integration (MySQL)

### Database Structure

- **softtrine_task** database contains two primary tables:
  1. **users**: Stores user information for login and role management.
  2. **products**: Stores product details with the following fields:
      - `product_name`
      - `slug`
      - `product_details`
      - `product_url`
      - `product_type`
      - `brand`
      - `stock_quantity`
      - `price`

### CRUD Operations

- **Create**: New products can be added using a **POST** request.
- **Read**: Products are fetched and displayed in the UI.
- **Update**: Existing products can be updated using a **PUT** request.
- **Delete**: Products can be removed using a **DELETE** request.
- **Status Update**: The status of a product (active/inactive) can be toggled via a **PATCH** request.

## Product Management Flow

### Search & Filter

- The admin can search for products by **name** and filter by **product type**.
- These functionalities are managed by the `searchTerm` and `selectedType` states in the app.

### Product Actions

1. **Add New Product**:
   - The admin can add a new product by clicking the "Add New Product" button.
   - A modal opens to input product details, which are sent to the backend via a **POST** request.
   
2. **Edit Product**:
   - Admins can click the edit button for any product.
   - The product's current details are loaded into the modal, and any changes are sent to the backend via a **PUT** request.
   
3. **Delete Product**:
   - Admins can delete a product after confirming the action. A **DELETE** request is sent to the backend to remove the product.

4. **Toggle Product Status**:
   - Admins can toggle the status of a product between **Active** and **Inactive** by clicking the status button. A **PATCH** request is sent to the backend to update the product's status.
# Conclusion

This project demonstrates a simple product management system where an admin can manage products and their details. The system includes user authentication, role-based navigation, and full CRUD operations with a MySQL database backend.
## 🙋‍♀️ Developed by

**Saniya Bagwan**  
Email: [saniya.bagwan.9226@gmail.com](mailto:saniya.bagwan.9226@gmail.com)
