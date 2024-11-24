# Bus Route Planner

## Problem Statement

You are tasked with designing a bus route planner for a city. The city consists of several bus stops, and buses run between them on different routes. The goal is to create a system that calculates the most efficient route between two bus stops based on the bus network. The problem will involve graph traversal, shortest path algorithms, and path reconstruction.

## Problem Details:

1. **Bus Stops and Routes**:
   - The city is represented as a graph where each node is a bus stop.
   - The edges between bus stops represent direct bus routes.
   - A bus route can have a specific time taken to travel between two bus stops.

2. **Input**:
   - You are given an integer `n` (1 ≤ n ≤ 1000) representing the number of bus stops.
   - You are also given a list of `m` (1 ≤ m ≤ 10000) routes where each route is represented as a tuple `(stop1, stop2, time)`. This means there is a direct bus route from `stop1` to `stop2` that takes `time` units of time.
   - You are given two bus stops `start` and `destination` (0-based indices) and asked to find the shortest time required to travel from `start` to `destination` using the available bus routes.

3. **Output**:
   - The shortest time required to travel from `start` to `destination`.
   - If there is no possible route between `start` and `destination`, return `-1`.

4. **Constraints**:
   - All bus routes are bidirectional (i.e., you can travel in both directions on each bus route).
   - You can assume the graph is connected.
   - There are no negative time values for any bus route.
   - A stop can have multiple routes connected to it, including multiple routes leading to the same destination with different times.

## Example:

### Input:
```bash
n = 5
routes = [(0, 1, 3), (1, 2, 2), (0, 2, 6), (2, 3, 1), (3, 4, 4)]
start = 0
destination = 4
```
### Output:
```bash
10
```

### Explanation:

- From stop 0, you can go to stop 1 in 3 units of time.
- From stop 1, you can go to stop 2 in 2 units of time.
- From stop 2, you can go to stop 3 in 1 unit of time.
- From stop 3, you can go to stop 4 in 4 units of time.
- The total time is 3 + 2 + 1 + 4 = 10 units.

## Requirements:

- Implement a graph structure to represent bus stops and routes.
- Use Dijkstra’s Algorithm to find the shortest time from `start` to `destination`.
- Ensure that the program handles edge cases such as when no route exists between `start` and `destination`.

## Bonus:

- Extend the problem to include the following features:
   - Allow multiple buses operating on the same route with different timings.
   - Implement a system to display the shortest path (bus stops) along with the total time taken.




## Boilerplate Code

### Java:
### C++:
### C:
### Python:
