# Bus Route Planner

## Problem Statement

A city operates a network of buses connecting various bus stops. Each bus route connects two stops and has a time cost associated with it. Your task is to develop a bus route planner system that calculates the **shortest travel time** between two stops while adhering to the following constraints:

1. **Maximum Transfers**: Each trip must use no more than a specified number of bus transfers.
2. **Service Hours**: Each bus route operates only during specified time periods.
3. **Penalties**: A penalty is applied for taking certain bus routes (e.g., congested routes).

The planner should compute:
1. **Shortest travel time**.
2. **Total penalty** for the selected route.

If no valid route exists under the given constraints, return `-1`.

---

### Input Format

1. **Number of Stops**: `n` (integer)  
2. **Bus Routes**: A list of routes, where each route is represented as:
- `start`, `end`: Bus stops connected by the route.
- `time`: Travel time in minutes.
- `start_hour`, `end_hour`: Operational hours of the route.
- `penalty`: Penalty cost for taking this route.
3. **Query**: A query containing:
- `start`: Starting bus stop.
- `destination`: Destination bus stop.
- `max_transfers`: Maximum allowed transfers.
- `current_hour`: The current hour of the day.

---

### Output Format

Return the shortest time and the total penalty for the computed route as a tuple `(time, penalty)`. If no valid route exists, return `-1`.

---

### Example Input

```plaintext
Number of Stops: 5
Routes:
0 1 3 6 20 2
1 2 2 8 18 3
0 2 6 10 16 1
2 3 1 9 21 4
3 4 4 6 20 0

Query:
start = 0
destination = 4
max_transfers = 2
current_hour = 15
```
### Example Output
```plaintext
Output: (10, 4)
```

## Constraints
- 1 <= n <= 100
- 1 <= number of routes <= 10,000
- 1 <= time <= 60 (in minutes)
- 0 <= start_hour, end_hour <= 23
- 0 <= penalty <= 10
- max_transfers >= 0
