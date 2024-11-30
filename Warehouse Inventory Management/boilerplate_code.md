## C++

```C++
#include <iostream>
#include <unordered_map>
#include <string>
using namespace std;

// Product class to represent a single product
class Product {
public:
    string name;
    int quantity;

    Product(string name, int quantity) {
        this->name = name;
        this->quantity = quantity;
    }
};

// WarehouseInventory class to manage inventory operations
class WarehouseInventory {
private:
    unordered_map<int, Product*> inventory;

public:
    // Add or update a product in the inventory
    void addProduct(int id, string name, int quantity) {
        // To be implemented
    }

    // Remove a product or reduce its quantity
    void removeProduct(int id, int quantity) {
        // To be implemented
    }

    // Search for a product by ID
    string searchProduct(int id) {
        // To be implemented
    }
};

int main() {
    WarehouseInventory warehouse;
    int n;
    cin >> n;

    for (int i = 0; i < n; i++) {
        int operation;
        cin >> operation;

        if (operation == 1) { // Add a product
            int id, quantity;
            string name;
            cin >> id >> name >> quantity;
            warehouse.addProduct(id, name, quantity);

        } else if (operation == 2) { // Remove a product
            int id, quantity;
            cin >> id >> quantity;
            warehouse.removeProduct(id, quantity);

        } else if (operation == 3) { // Search a product
            int id;
            cin >> id;
            cout << warehouse.searchProduct(id) << endl;
        }
    }

    return 0;
}
```

## Java

```Java
import java.util.*;

class Product {
    String name;
    int quantity;

    public Product(String name, int quantity) {
        this.name = name;
        this.quantity = quantity;
    }
}

class WarehouseInventory {
    private Map<Integer, Product> inventory;

    public WarehouseInventory() {
        inventory = new HashMap<>();
    }

    // Add or update a product in the inventory
    public void addProduct(int id, String name, int quantity) {
        // To be implemented
    }

    // Remove a product or reduce its quantity
    public void removeProduct(int id, int quantity) {
        // To be implemented
    }

    // Search for a product by ID
    public String searchProduct(int id) {
        // To be implemented
        return "";
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        WarehouseInventory warehouse = new WarehouseInventory();

        int n = sc.nextInt();
        sc.nextLine(); // Consume the newline character

        for (int i = 0; i < n; i++) {
            String[] operation = sc.nextLine().split(" ");
            int opType = Integer.parseInt(operation[0]);

            if (opType == 1) { // Add a product
                int id = Integer.parseInt(operation[1]);
                String name = operation[2];
                int quantity = Integer.parseInt(operation[3]);
                warehouse.addProduct(id, name, quantity);

            } else if (opType == 2) { // Remove a product
                int id = Integer.parseInt(operation[1]);
                int quantity = Integer.parseInt(operation[2]);
                warehouse.removeProduct(id, quantity);

            } else if (opType == 3) { // Search a product
                int id = Integer.parseInt(operation[1]);
                System.out.println(warehouse.searchProduct(id));
            }
        }

        sc.close();
    }
}

```

## Python

```Python
class Product:
    def __init__(self, name, quantity):
        self.name = name
        self.quantity = quantity

class WarehouseInventory:
    def __init__(self):
        self.inventory = {}

    def add_product(self, product_id, name, quantity):
        pass  # Implement this

    def remove_product(self, product_id, quantity):
        pass  # Implement this

    def search_product(self, product_id):
        pass  # Implement this

# Main function to take input and call methods
def main():
    warehouse = WarehouseInventory()
    n = int(input())
    for _ in range(n):
        operation = input().split()
        op_type = int(operation[0])
        
        if op_type == 1:  # Add a product
            product_id = int(operation[1])
            name = operation[2]
            quantity = int(operation[3])
            warehouse.add_product(product_id, name, quantity)
        
        elif op_type == 2:  # Remove a product
            product_id = int(operation[1])
            quantity = int(operation[2])
            warehouse.remove_product(product_id, quantity)
        
        elif op_type == 3:  # Search a product
            product_id = int(operation[1])
            result = warehouse.search_product(product_id)
            print(result)

if __name__ == "__main__":
    main()

```
