# Software Design Description (SDD) for Blinkit Clone

## 1. Introduction

### 1.1 Purpose
This Software Design Description (SDD) outlines the detailed design of a Blinkit clone, an on-demand grocery and essentials delivery application. The document covers the system architecture, components, interfaces, and interactions to ensure the implementation aligns with the system's functional and non-functional requirements.

### 1.2 Scope
The Blinkit clone system allows users to:
- Browse a variety of grocery products and essentials
- Add products to the cart
- Make payments using different payment methods
- Schedule deliveries or opt for immediate delivery
- Track orders in real-time
- Review and rate products and deliveries

The system consists of the mobile application (frontend), backend API services, payment processing system, user management, order management, product catalog, and integration with delivery partners.

---

## 4. Module Design

### 4.1 Mobile Application (Frontend)

#### 4.1.1 User Interface (UI)
The UI is designed to be simple, intuitive, and responsive. Key UI components include:
- **Home Screen**: Displays featured products, categories, discounts, and user’s shopping list.
- **Product Catalog**: Lists available products categorized by type (e.g., groceries, beverages, personal care).
- **Cart**: Shows selected items, quantity, total price, and allows users to modify or proceed to checkout.
- **Order Tracking**: Displays real-time order status, delivery time, and progress.
- **Profile & Settings**: Manages user profile, addresses, payment methods, and preferences.

#### 4.1.2 Controller Layer
Handles user interactions and communicates with the service layer to process the requests. Components include:
- **Authentication Controller**: Manages user login, registration, and authentication mechanisms.
- **Product Controller**: Handles user queries for products, categories, and offers.
- **Cart Controller**: Manages items added to the cart, modifications, and checkout process.
- **Order Controller**: Manages order placement, status updates, and cancellations.
- **Profile Controller**: Handles user details, address management, and payment information.

#### 4.1.3 Service Layer
The service layer contains business logic, validation, and integration with backend APIs. It includes:
- **User Service**: Manages user profile, login, and security.
- **Product Service**: Handles product searches, filtering, and retrieving product details.
- **Cart Service**: Handles the cart's add/remove operations and calculates the total price.
- **Order Service**: Processes order creation, updates, and cancellations.
- **Delivery Service**: Integrates with third-party delivery partners for delivery tracking and scheduling.

---

### 4.2 Backend System (Server-side)

#### 4.2.1 API Gateway
The API Gateway serves as the entry point for all client requests. It routes incoming API calls to the respective backend services based on the type of request.

#### 4.2.2 Authentication Service
Handles:
- User registration, login, and authentication (JWT-based)
- User password management (reset, recovery)
- Multi-factor authentication (optional)

#### 4.2.3 Product Service
Handles:
- Product catalog management (CRUD operations for products)
- Categorization of products
- Product search and filtering functionality
- Special offers and discounts

#### 4.2.4 Cart Service
Handles:
- Cart management (adding/removing items)
- Cart total calculation (with discounts, taxes)
- Checkout process (addresses, payment method selection)

#### 4.2.5 Order Service
Handles:
- Order placement, updating, and tracking
- Order cancellations and returns
- Integration with delivery partners for order fulfillment

#### 4.2.6 Payment Service
Handles:
- Integration with various payment gateways (UPI, credit/debit cards, wallets)
- Payment processing, confirmation, and refund mechanisms

#### 4.2.7 Delivery Service
Handles:
- Integration with third-party delivery services
- Real-time order tracking
- Estimated delivery time calculation

#### 4.2.8 Notification Service
Handles:
- User notifications via SMS, email, and push notifications for order updates, promotions, and offers.

#### 4.2.9 Security Service
Handles:
- Data encryption and decryption
- Secure API communication (SSL/TLS)
- Role-based access control and authorization
- Fraud detection and prevention

---

### Database Design

The system uses a relational database to store and manage the following data:

- **Users**: Stores user details such as name, contact information, and delivery addresses.
- **Products**: Stores product information, including name, description, price, category, and availability.
- **Orders**: Stores order-related information such as user ID, product IDs, order status, timestamps, and delivery details.
- **Payments**: Stores payment transaction data, including payment status, amount, method, and timestamp.
- **Cart**: Stores details about products added to the cart, including quantity and user ID.
- **Delivery**: Stores details of delivery partners and real-time status of ongoing deliveries.

![Design Diagram](https://github.com/user-attachments/assets/13c8fc20-1508-4baa-8690-5d7b43425467)

---

## 5. Interface Design

### 5.1 API Design
The API design for the Blinkit clone follows RESTful principles to ensure efficient, secure communication between the mobile app and backend services. Below are the key API endpoints:

- **GET /products**: Fetches a list of products, with support for category and price filters.
- **POST /cart/add**: Adds a product to the user's shopping cart.
- **GET /cart**: Retrieves the current cart for the user.
- **POST /order/place**: Places an order for the items in the cart.
- **GET /order/{orderId}**: Retrieves the status of a specific order.
- **POST /payment/checkout**: Initiates payment processing for the order.
- **POST /user/login**: Authenticates the user and provides a session token.

![API Design](https://github.com/user-attachments/assets/adda3597-7bc2-4c08-8e77-376fb134fa87)

---

## 6. System Quality Attributes

### 6.1 Concurrent User Handling
The system is designed to handle at least **15,000 simultaneous users** during peak hours, ensuring high availability during periods of heavy traffic.

### 6.2 Growth Accommodation
The backend architecture supports **horizontal scalability** to accommodate future growth in the number of users, orders, and product listings.

### 6.3 Operational Continuity
The system aims for **99.9% availability**, with redundant components, automatic failover, and disaster recovery mechanisms in place to ensure the system operates continuously.

### 6.4 Data Protection
The application employs **end-to-end encryption** for all sensitive data, including payment details and personal user information. It also ensures **multi-factor authentication** for secure user access.

---

## Final Remarks
This Software Design Description (SDD) provides a comprehensive overview of the Blinkit clone’s architecture, modules, database design, and API interfaces. The system is designed to be scalable, secure, and user-friendly, with a focus on handling real-time orders, efficient payment processing, and smooth integration with delivery services. By implementing this design, the system will be capable of efficiently managing high volumes of transactions while ensuring high availability and data protection.
