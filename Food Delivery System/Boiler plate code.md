# FOOD DELIVERY SYSTEM IMPLEMENTATION

# PYTHON IMPLEMENTATION
class Restaurant:
    def __init__(self, name, cuisine):
        self.name = name
        self.cuisine = cuisine
        self.menu = {}

    def add_item(self, item, price):
        self.menu[item] = price

class FoodDeliverySystem:
    def __init__(self):
        self.restaurants = {}
        self.orders = {}
        self.order_id_counter = 100

    def add_restaurant(self, name, cuisine):
        self.restaurants[name] = Restaurant(name, cuisine)
        print(f"Restaurant '{name}' added successfully!")

    def add_menu_item(self, restaurant_name, item, price):
        if restaurant_name in self.restaurants:
            self.restaurants[restaurant_name].add_item(item, price)
            print(f"Item '{item}' added to the menu of {restaurant_name}")
        else:
            print("Restaurant not found.")

    def place_order(self, restaurant_name, items):
        if restaurant_name in self.restaurants:
            total_price = 0
            for item in items:
                if item in self.restaurants[restaurant_name].menu:
                    total_price += self.restaurants[restaurant_name].menu[item]
            order_id = self.order_id_counter
            self.orders[order_id] = f"{restaurant_name} | {items} | Total: ${total_price}"
            self.order_id_counter += 1
            print(f"Order placed successfully. Order ID: {order_id}")
        else:
            print("Restaurant not found.")

    def view_order_history(self):
        if not self.orders:
            print("No orders placed yet.")
        else:
            print("Order History:")
            for order_id, details in self.orders.items():
                print(f"Order ID: {order_id} | Details: {details}")

    def cancel_order(self, order_id):
        if order_id in self.orders:
            del self.orders[order_id]
            print(f"Order ID {order_id} has been cancelled.")
        else:
            print("Order not found.")

# JAVA IMPLEMENTATION
'''
import java.util.*;

class Restaurant {
    String name;
    String cuisine;
    Map<String, Double> menu;

    public Restaurant(String name, String cuisine) {
        this.name = name;
        this.cuisine = cuisine;
        this.menu = new HashMap<>();
    }

    public void addItem(String item, double price) {
        menu.put(item, price);
    }
}

class FoodDeliverySystem {
    private final Map<String, Restaurant> restaurants = new HashMap<>();
    private final Map<Integer, String> orders = new HashMap<>();
    private int orderIdCounter = 100;

    public void addRestaurant(String name, String cuisine) {
        restaurants.put(name, new Restaurant(name, cuisine));
        System.out.println("Restaurant '" + name + "' added successfully!");
    }

    public void addMenuItem(String restaurantName, String item, double price) {
        Restaurant restaurant = restaurants.get(restaurantName);
        if (restaurant != null) {
            restaurant.addItem(item, price);
            System.out.println("Item '" + item + "' added to the menu of " + restaurantName);
        } else {
            System.out.println("Restaurant not found.");
        }
    }

    public void placeOrder(String restaurantName, List<String> items) {
        Restaurant restaurant = restaurants.get(restaurantName);
        if (restaurant != null) {
            double totalPrice = 0;
            for (String item : items) {
                if (restaurant.menu.containsKey(item)) {
                    totalPrice += restaurant.menu.get(item);
                }
            }
            int orderId = orderIdCounter++;
            orders.put(orderId, restaurantName + " | " + items + " | Total: $" + totalPrice);
            System.out.println("Order placed successfully. Order ID: " + orderId);
        } else {
            System.out.println("Restaurant not found.");
        }
    }

    public void viewOrderHistory() {
        if (orders.isEmpty()) {
            System.out.println("No orders placed yet.");
        } else {
            System.out.println("Order History:");
            for (Map.Entry<Integer, String> entry : orders.entrySet()) {
                System.out.println("Order ID: " + entry.getKey() + " | Details: " + entry.getValue());
            }
        }
    }

    public void cancelOrder(int orderId) {
        if (orders.containsKey(orderId)) {
            orders.remove(orderId);
            System.out.println("Order ID " + orderId + " has been cancelled.");
        } else {
            System.out.println("Order not found.");
        }
    }

    public static void main(String[] args) {
        FoodDeliverySystem system = new FoodDeliverySystem();
        system.addRestaurant("Pizza Palace", "Italian");
        system.addMenuItem("Pizza Palace", "Margherita Pizza", 10);
        system.addMenuItem("Pizza Palace", "Garlic Bread", 5);
        system.placeOrder("Pizza Palace", Arrays.asList("Margherita Pizza", "Garlic Bread"));
        system.viewOrderHistory();
    }
}
'''

# C++ IMPLEMENTATION
'''
#include <iostream>
#include <unordered_map>
#include <vector>
#include <string>
using namespace std;

class Restaurant {
public:
    string name;
    string cuisine;
    unordered_map<string, double> menu;

    Restaurant(string name, string cuisine) : name(name), cuisine(cuisine) {}

    void addItem(string item, double price) {
        menu[item] = price;
    }
};

class FoodDeliverySystem {
private:
    unordered_map<string, Restaurant> restaurants;
    unordered_map<int, string> orders;
    int orderIdCounter = 100;

public:
    void addRestaurant(string name, string cuisine) {
        restaurants[name] = Restaurant(name, cuisine);
        cout << "Restaurant '" << name << "' added successfully!" << endl;
    }

    void addMenuItem(string restaurantName, string item, double price) {
        if (restaurants.find(restaurantName) != restaurants.end()) {
            restaurants[restaurantName].addItem(item, price);
            cout << "Item '" << item << "' added to the menu of " << restaurantName << endl;
        } else {
            cout << "Restaurant not found." << endl;
        }
    }

    void placeOrder(string restaurantName, vector<string> items) {
        if (restaurants.find(restaurantName) != restaurants.end()) {
            double totalPrice = 0;
            for (const auto& item : items) {
                if (restaurants[restaurantName].menu.find(item) != restaurants[restaurantName].menu.end()) {
                    totalPrice += restaurants[restaurantName].menu[item];
                }
            }
            int orderId = orderIdCounter++;
            orders[orderId] = restaurantName + " | " + "Items: ";
            for (const auto& item : items) orders[orderId] += item + " ";
            orders[orderId] += "| Total: $" + to_string(totalPrice);
            cout << "Order placed successfully. Order ID: " << orderId << endl;
        } else {
            cout << "Restaurant not found." << endl;
        }
    }

    void viewOrderHistory() {
        if (orders.empty()) {
            cout << "No orders placed yet." << endl;
        } else {
            cout << "Order History:" << endl;
            for (const auto& entry : orders) {
                cout << "Order ID: " << entry.first << " | Details: " << entry.second << endl;
            }
        }
    }

    void cancelOrder(int orderId) {
        if (orders.find(orderId) != orders.end()) {
            orders.erase(orderId);
            cout << "Order ID " << orderId << " has been cancelled." << endl;
        } else {
            cout << "Order not found." << endl;
        }
    }
};

int main() {
    FoodDeliverySystem system;
    system.addRestaurant("Pizza Palace", "Italian");
    system.addMenuItem("Pizza Palace", "Margherita Pizza", 10);
    system.addMenuItem("Pizza Palace", "Garlic Bread", 5);
    system.placeOrder("Pizza Palace", {"Margherita Pizza", "Garlic Bread"});
    system.viewOrderHistory();
    return 0;
}
'''


