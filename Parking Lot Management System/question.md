# Parking Lot Management System

## Problem Statement

A parking lot operates as a system to manage vehicle entries, parking spot allocation, and exits. Your task is to develop a Parking Lot Management System that handles multiple operations efficiently, using data structures for optimal performance. The system must track vehicles, allocate spots, and calculate fees based on the duration of parking.

1. **Park Vehicle:** Allocate the nearest available parking spot to a vehicle when it arrives.
2. **Remove Vehicle:** Remove the vehicle and calculate the parking fee based on the parking duration at a fixed rate (₹20 per hour).

If the parking lot is full , return `-1`. If the system tries to remove a vehicle not parked in a lot then return `-1` as the parking fee.

Obtain the Boiler Plate code from `boilerplate code.md` in C++/Java/Python.

---

### Input Format

1. **Parking Lot Details** `total_spots`: Total parking spots available.
2. **Vehicle Details:** A list of details where each operation is represented as:
   - `operation_type`: The type of operation (park, remove).
   - `vehicle_type`: Type of vehicle (car, bike).
   - `license_plate`: Unique license number of the vehicle.
3. **Time Details:** Entry and exit timestamps for vehicles.

---

### Output Format

- **For `park` operations:** Output the allocated parking spot number. If no spots are available, return `-1`.
- **For `remove` operations:** Output the parking fee and free the parking spot. If the vehicle is not found, return `-1`.

---

### Example Input

```
Parking Lot: 3 spots

Operations:  
1. park car ABC-123 0
2. park bike XYZ-456 2
3. remove ABC-123 2
```

### Example Output
```
Output:  
1. Spot 3 allocated to car ABC-123  
2. Spot 2 allocated to bike XYZ-456  
3. Car ABC-123 removed from Spot 3. Parking fee: ₹40  

```

## Constraints
- 1 <= total_spots <= 1000
- Operations are restricted to park and remove.
- Parking fee is charged at ₹20 per hour (round up to the nearest hour).
- Vehicles are uniquely identified by their license plate.
- Spot allocation follows a LIFO principle (use stacks).










