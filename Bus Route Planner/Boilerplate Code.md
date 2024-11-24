## JAVA

```java
import java.util.*;

class BusRoutePlanner {

    private int n;
    private List<int[]>[] adj;

    public BusRoutePlanner(int n, int[][] routes) {
        this.n = n;
        this.adj = new ArrayList[n];
        for (int i = 0; i < n; i++) {
            adj[i] = new ArrayList<>();
        }
        buildGraph(routes);
    }

    private void buildGraph(int[][] routes) {
        // Add route to graph
    }

    public int[] findShortestRoute(int start, int destination, int maxTransfers, int currentHour) {
        // Implement the logic
        return new int[]{-1};
    }

    public static void main(String[] args) {
        int n = 5;
        int[][] routes = {
            {0, 1, 3, 6, 20, 2},
            {1, 2, 2, 8, 18, 3},
            {0, 2, 6, 10, 16, 1},
            {2, 3, 1, 9, 21, 4},
            {3, 4, 4, 6, 20, 0}
        };
        int start = 0, destination = 4, maxTransfers = 2, currentHour = 15;

        BusRoutePlanner planner = new BusRoutePlanner(n, routes);
        System.out.println(Arrays.toString(planner.findShortestRoute(start, destination, maxTransfers, currentHour)));
    }
}
```

## C++
```C++
#include <iostream>
#include <vector>
#include <queue>
#include <climits>

using namespace std;

class BusRoutePlanner {
public:
    BusRoutePlanner(int n, vector<vector<int>>& routes) {
        this->n = n;
        adj.resize(n);
        buildGraph(routes);
    }

    void buildGraph(vector<vector<int>>& routes) {
        // Add route to graph
    }

    pair<int, int> findShortestRoute(int start, int destination, int maxTransfers, int currentHour) {
        // Implement the logic
        return {-1, -1};
    }

private:
    int n;
    vector<vector<tuple<int, int, int, int>>> adj;
};

int main() {
    int n = 5;
    vector<vector<int>> routes = {
        {0, 1, 3, 6, 20, 2},
        {1, 2, 2, 8, 18, 3},
        {0, 2, 6, 10, 16, 1},
        {2, 3, 1, 9, 21, 4},
        {3, 4, 4, 6, 20, 0}
    };

    int start = 0, destination = 4, maxTransfers = 2, currentHour = 15;

    BusRoutePlanner planner(n, routes);
    auto result = planner.findShortestRoute(start, destination, maxTransfers, currentHour);
    cout << "(" << result.first << ", " << result.second << ")" << endl;

    return 0;
}
```
## Python
```python
from collections import defaultdict
import heapq

class BusRoutePlanner:
    def __init__(self, n, routes):
        """
        Initializes the BusRoutePlanner with the number of stops and routes.
        
        :param n: int - Number of bus stops.
        :param routes: List[Tuple[int, int, int, int, int, int]] 
                       (start, end, time, start_hour, end_hour, penalty)
        """
        self.n = n
        self.routes = routes
        self.adj = defaultdict(list)
        self._build_graph()

    def _build_graph(self):
        """
        Builds the graph from the given routes.
        Each route is added as a directed edge in the adjacency list.
        """
        

    def find_shortest_route(self, start, destination, max_transfers, current_hour):
        """
        Finds the shortest route from 'start' to 'destination' 
        under the constraints.

        :param start: int - Starting bus stop.
        :param destination: int - Destination bus stop.
        :param max_transfers: int - Maximum number of allowed transfers.
        :param current_hour: int - Current hour in 24-hour format.
        :return: Tuple[int, int] - (Shortest travel time, Total penalty) or -1 if no valid route exists.
        """
        # Implement the logic
        return -1, -1


# Example Usage:
if __name__ == "__main__":
    n = 5
    routes = [
        (0, 1, 3, 6, 20, 2),
        (1, 2, 2, 8, 18, 3),
        (0, 2, 6, 10, 16, 1),
        (2, 3, 1, 9, 21, 4),
        (3, 4, 4, 6, 20, 0)
    ]

    planner = BusRoutePlanner(n, routes)
    start = 0
    destination = 4
    max_transfers = 2
    current_hour = 15

    print(planner.find_shortest_route(start, destination, max_transfers, current_hour))
    # Expected output: (Shortest travel time, Total penalty)
```
