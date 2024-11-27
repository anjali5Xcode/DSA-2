## Boilerplate Code

### C++
```C++
#include <iostream>
#include <unordered_map>
#include <stack>
using namespace std;

// Vehicle structure
struct Vehicle {
    string type;          // Type of vehicle (car, bike)
    string license;       // License number
    int entryTime;        // Entry time in hours
};

class ParkingLot {
private:
    int totalSpots;     
    stack<int> availableSpots;               // Stack of available parking spots
    unordered_map<string, Vehicle> parkedVehicles; // Map of license -> Vehicle details
    unordered_map<string, int> vehicleSpotMap;     // Map of license -> Spot number

    // Define the required data structures by yourself                    

public:
    // Constructor
    ParkingLot(int n){
        for (int i = n; i >= 1; --i) {
            availableSpots.push(i);
        }
    }

    // Park a vehicle
    void parkVehicle(string vehicleType, string license, int entryTime);

    // Remove a vehicle and calculate the fee
    void removeVehicle(string license, int exitTime);
};

int main() {
    int totalSpots;
    cout << "Enter total parking spots: ";
    cin >> totalSpots;

    ParkingLot lot(totalSpots);

    int choice;
    while (true) {
        cout << "\n1. Park Vehicle\n2. Remove Vehicle\n3. Exit\nEnter choice: ";
        cin >> choice;
        if (choice == 3) break;

        string vehicleType, license;
        int time;
        switch (choice) {
            case 1:
                cout << "Enter vehicle type (car/bike): ";
                cin >> vehicleType;
                cout << "Enter license number: ";
                cin >> license;
                cout << "Enter entry time (0-23): ";
                cin >> time;
                lot.parkVehicle(vehicleType, license, time);
                break;
            case 2:
                cout << "Enter license number: ";
                cin >> license;
                cout << "Enter exit time (0-23): ";
                cin >> time;
                lot.removeVehicle(license, time);
                break;
            default:
                cout << "Invalid choice.\n";
        }
    }

    return 0;
}
```

### Java
```Java
import java.util.*;

class Vehicle {
    String type;     // Type of vehicle (car, bike)
    String license;  // License number
    int entryTime;   // Entry time in hours

    // Constructor
    public Vehicle(String type, String license, int entryTime) {
        this.type = type;
        this.license = license;
        this.entryTime = entryTime;
    }
}

class ParkingLot {
    private int totalSpots;
    // Define the required data structures by yourself
    private Stack<Integer> availableSpots;
    private Map<String, Vehicle> parkedVehicles;
    private Map<String, Integer> vehicleSpotMap;

    // Constructor
    public ParkingLot(int n) {
        totalSpots = n;
        availableSpots = new Stack<>();
        parkedVehicles = new HashMap<>();
        vehicleSpotMap = new HashMap<>();
        
        // Initialize parking spots
        for (int i = n; i >= 1; i--) {
            availableSpots.push(i);
        }
    }

    // Park a vehicle
    public void parkVehicle(String vehicleType, String license, int entryTime) {
        // Implement logic
    }

    // Remove a vehicle and calculate the fee
    public void removeVehicle(String license, int exitTime) {
        // Implement logic
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter total parking spots: ");
        int totalSpots = scanner.nextInt();
        ParkingLot lot = new ParkingLot(totalSpots);

        while (true) {
            System.out.println("\n1. Park Vehicle\n2. Remove Vehicle\n3. Exit");
            System.out.print("Enter choice: ");
            int choice = scanner.nextInt();

            if (choice == 3) break;

            switch (choice) {
                case 1:
                    System.out.print("Enter vehicle type (car/bike): ");
                    String vehicleType = scanner.next();
                    System.out.print("Enter license number: ");
                    String license = scanner.next();
                    System.out.print("Enter entry time (0-23): ");
                    int entryTime = scanner.nextInt();
                    lot.parkVehicle(vehicleType, license, entryTime);
                    break;

                case 2:
                    System.out.print("Enter license number: ");
                    String removeLicense = scanner.next();
                    System.out.print("Enter exit time (0-23): ");
                    int exitTime = scanner.nextInt();
                    lot.removeVehicle(removeLicense, exitTime);
                    break;

                default:
                    System.out.println("Invalid choice.");
            }
        }

        scanner.close();
    }
}

```

### Python
```Python
class Vehicle:
    def __init__(self, vehicle_type, license, entry_time):
        self.type = vehicle_type   # Type of vehicle (car, bike)
        self.license = license     # License number
        self.entry_time = entry_time  # Entry time in hours

class ParkingLot:
    def __init__(self, total_spots):
        self.total_spots = total_spots
        # Define the required data structures by yourself
        self.available_spots = list(range(total_spots, 0, -1))  # Available spots (LIFO)
        self.parked_vehicles = {}  # Map of license -> Vehicle
        self.vehicle_spot_map = {}  # Map of license -> Spot number

    def park_vehicle(self, vehicle_type, license, entry_time):
        # Implement logic
        pass

    def remove_vehicle(self, license, exit_time):
        # Implement logic
        pass

def main():
    total_spots = int(input("Enter total parking spots: "))
    parking_lot = ParkingLot(total_spots)

    while True:
        print("\n1. Park Vehicle\n2. Remove Vehicle\n3. Exit")
        choice = int(input("Enter choice: "))
        if choice == 3:
            break

        if choice == 1:
            vehicle_type = input("Enter vehicle type (car/bike): ")
            license = input("Enter license number: ")
            entry_time = int(input("Enter entry time (0-23): "))
            parking_lot.park_vehicle(vehicle_type, license, entry_time)
        elif choice == 2:
            license = input("Enter license number: ")
            exit_time = int(input("Enter exit time (0-23): "))
            parking_lot.remove_vehicle(license, exit_time)
        else:
            print("Invalid choice.")

if __name__ == "__main__":
    main()

```