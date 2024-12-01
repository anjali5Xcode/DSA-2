# Food Delivery System

This project is a simple **Food Delivery System** built in **Java**, **C++**, and **Python**. It allows users to add restaurants, place orders, search restaurants, view order history, and cancel orders within a specific time frame. Below is the detailed implementation and features of the system.

## Features
- **Add Restaurant**: Add a new restaurant with its name, cuisine type, and menu (list of items with prices).
- **Search Restaurant**: Search restaurants by cuisine or name.
- **Place Order**: Place an order from a restaurant with multiple items. Generate an order ID for tracking.
- **View Order History**: View all previous orders with details like restaurant name, items ordered, total price, and timestamp.
- **Cancel Order**: Cancel an order within 5 minutes of placing it.

## Concepts Used
- **Hash Maps**: For storing restaurant data.
- **Queues**: For order processing and handling cancellation.
- **Lists**: For managing menu items and orders.
- **String Matching**: For searching restaurant names and cuisine types.

## Example Usage
1. **Add Restaurant**:
   - Name: "Pizza Palace", Cuisine: "Italian", Menu: ["Margherita Pizza - $10", "Garlic Bread - $5"]
2. **Place Order**:
   - Order ID: 101
   - Items: ["Margherita Pizza", "Garlic Bread"]
   - Total: $15
3. **View Order History**:
   - Returns details of past orders like restaurant name, items ordered, total price, and timestamp.

---
