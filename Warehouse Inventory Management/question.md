# Warehouse Inventory Management

### Problem Statement
You are managing a warehouse inventory system. Each product in the warehouse has a unique ID, a name, and a quantity. You are tasked with implementing the following functionalities:

1. Add a Product: Add a new product to the inventory. If the product already exists, update its quantity.
2. Remove a Product: Remove a certain quantity of a product. If the quantity becomes zero or negative, remove the product from the inventory entirely.
3. Search a Product: Search for a product by its ID to get its name and quantity.
Write a program to implement the above functionalities.

### Input Format
The first line contains an integer N, the number of operations to be performed.
The next N lines describe the operations in the format:

1. ID NAME QUANTITY (Add a product with ID, NAME, and QUANTITY).
2. ID QUANTITY (Remove a certain QUANTITY of the product with ID).
3. ID (Search for the product with ID).

### Output Format
For each search operation (3 ID):

* If the product exists, output its NAME and QUANTITY.
* If the product does not exist, output "Product not found".

Example Input

```
6
1 101 Apple 50
1 102 Banana 30
3 101
2 101 20
3 101
3 103

```

Example Output

```
Apple 50
Apple 30
Product not found
```

Constraints
* 1 ≤ N ≤ 10<sup>4</sup>
* 1 ≤ QUANTITY ≤ 10<sup>6</sup>
* 1 ≤ ID ≤ 10<sup>6</sup>
* Product names are alphanumeric and have a maximum length of 20 characters.




