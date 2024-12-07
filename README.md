## UML Class Diagram for a E-Commerce Platform

### Overview
This class diagram models the core components of our e-commerce platform, including user authentication, product management, order handling, payments, and shipping.

### Key Entities

##### 1. User:
Represents the authentication layer.
Handles login/logout functionality.
Links to a Customer entity to manage personal and order-related information.

##### 2. Customer:
Represents a user who can place orders.
Stores personal details such as name, email, address, and phone.
Can place multiple orders.

##### 3. Product:
Represents items available for purchase.
Tracks product details such as name, description, price, and stockQuantity.
Includes methods for retrieving product details and updating stock after purchases.

##### 4. Order:
Represents a purchase made by a customer.
Contains information about the order's ID, date, status, and total amount.
Links to OrderItem, Payment, and Shipping entities.

##### 5. OrderItem:
Represents individual items within an order.
Tracks quantity and price for each product in the order.
Includes a method to calculate the subtotal for the item.

##### 6. Payment:
Handles payment details for an order.
Tracks the paymentId, payment method, amount, and status.
Includes a method to process payments.

##### 7. Shipping:
Tracks shipping details for an order.
Attributes include the shippingId, address, trackingId, and status.
Provides a method to update shipping status.

### Relationships
1. User ↔ Customer: A User represents login credentials, while Customer represents the associated personal information and order history.
2. Customer ↔ Order: A customer can place multiple orders (1-to-many relationship).
3. Order ↔ OrderItem: Each order can have multiple items (1-to-many relationship).
4. Order ↔ Payment: Each order is associated with one payment (1-to-1 relationship).
5. Order ↔ Shipping: Each order has a single shipping entry (1-to-1 relationship).

### Key Functionalities
#### User Login/Logout:
A User logs in to access the platform and perform operations like placing orders.
The logout() method ends the session.

#### Product Management:
Products have a stock quantity that can be updated when purchased.
Details of products can be retrieved with the getDetails() method.

#### Order Management:
Orders include a list of items (OrderItem) and link to their payment and shipping details.
The total cost of an order is calculated using calculateTotal().

#### Payment Processing:
Payments for orders are processed through the Payment entity.
Includes status tracking for successful or failed payments.

#### Shipping Tracking:
Shipping details such as address, tracking ID, and current status are managed.
The status can be updated dynamically.

### Diagram Multiplicities
1. User ↔ Customer: 1-to-1
2. Customer ↔ Order: 1-to-many
3. Order ↔ OrderItem: 1-to-many
4. Order ↔ Payment: 1-to-1
5. Order ↔ Shipping: 1-to-1

### Contributors
1. Chamal Randika Mallawaarachchi - 22ug1-0093
2. P.D.P. Nimsara Peiris           - 22ug1-0627