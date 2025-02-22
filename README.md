# Solar E-commerce Platform

A modern e-commerce platform built with Node.js and Express, specifically designed for solar product sales. This platform offers a complete shopping experience from product browsing to order fulfillment.

## 🌟 Key Features

- **Product Management**
  - Dynamic product catalog
  - Detailed single product views
  - Product search and filtering

- **Shopping Cart System**
  - Real-time cart updates
  - Quantity adjustment
  - Price calculation with sale price support
  - Cart persistence using sessions

- **Checkout Process**
  - Secure order placement
  - Customer information collection
  - Multiple payment options
  - Order tracking system

- **Order Management**
  - Order history tracking
  - Transaction recording
  - Payment status updates
  - Order items management

## 🛠️ Technical Stack

- **Backend:** Node.js with Express.js
- **Database:** MySQL
- **Template Engine:** EJS
- **Session Management:** express-session
- **Request Parsing:** body-parser
- **Static Files:** express.static

## 📋 Prerequisites

- Node.js (v14 or higher)
- MySQL Server
- npm (Node Package Manager)

## 🚀 Installation

1. **Clone the Repository**
   ```bash
   git clone [your-repository-url]
   cd solar-project
   ```

2. **Install Dependencies**
   ```bash
   npm install express ejs body-parser mysql express-session
   ```

3. **Database Setup**
   ```sql
   CREATE DATABASE node_project;
   USE node_project;
   ```

4. **Configure Database**
   - Update the database configuration in `app.js`:
   ```javascript
   const dbConfig = {
       host: "localhost",
       user: "root",
       password: "",
       database: "node_project"
   }
   ```

5. **Start the Server**
   ```bash
   node app.js
   ```
   Server will run on `http://localhost:8080`

## 📊 Database Structure

### Products Table
```sql
CREATE TABLE products (
    id INT PRIMARY KEY,
    name VARCHAR(255),
    price DECIMAL(10,2),
    sale_price DECIMAL(10,2),
    image VARCHAR(255)
);
```

### Orders Table
```sql
CREATE TABLE orders (
    id VARCHAR(255) PRIMARY KEY,
    cost DECIMAL(10,2),
    name VARCHAR(255),
    email VARCHAR(255),
    status VARCHAR(50),
    city VARCHAR(100),
    address TEXT,
    phone VARCHAR(20),
    date DATETIME,
    products_ids TEXT
);
```

### Order Items Table
```sql
CREATE TABLE order_items (
    order_id VARCHAR(255),
    product_id INT,
    product_name VARCHAR(255),
    product_price DECIMAL(10,2),
    product_image VARCHAR(255),
    product_quantity INT,
    order_date DATETIME
);
```

### Payments Table
```sql
CREATE TABLE payments (
    order_id VARCHAR(255),
    transaction_id VARCHAR(255),
    date DATETIME
);
```

## 🛣️ API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/` | GET | Home page with product listings |
| `/add_to_cart` | POST | Add product to shopping cart |
| `/cart` | GET | View shopping cart |
| `/checkout` | GET | Checkout page |
| `/place_order` | POST | Process order placement |
| `/payment` | GET | Payment processing page |
| `/verify_payment` | GET | Verify payment transaction |
| `/products` | GET | View all products |
| `/single_product` | GET | View single product details |

## 🔐 Security Features

- Session-based cart management
- Secure payment processing
- Order verification system
- Transaction tracking

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/YourFeature`)
3. Commit changes (`git commit -m 'Add YourFeature'`)
4. Push to branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

## 📝 License

MIT License - feel free to use this project for your own purposes.
