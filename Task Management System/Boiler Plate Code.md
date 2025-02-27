C++ 
--------------------------------------------------------------------------------------------------------------------------------------------------------

#include <iostream>
#include <vector>
#include <algorithm>
#include <unordered_map>
using namespace std;

class TaskManager {
private:
    struct Task {
        int id;
        int time;
        int priority;
    };
    vector<Task> tasks; // Stores all tasks
    unordered_map<int, int> taskIndex; // Maps task_id to its index in the vector

    // Custom comparator for sorting by priority and then time
    static bool compareTasks(const Task &a, const Task &b) {
        if (a.priority == b.priority)
            return a.time < b.time;
        return a.priority > b.priority;
    }

public:
    void addTask(int id, int time, int priority) {
        
    }

    int getHighestPriorityTask() {

    }

    void removeTask(int id) {
       
    }
};

int main() {
    TaskManager manager;

    int n, q;
    cin >> n;
    for (int i = 0; i < n; ++i) {
        int id, time, priority;
        cin >> id >> time >> priority;
        manager.addTask(id, time, priority);
    }

    cin >> q;
    while (q--) {
        int queryType;
        cin >> queryType;
        if (queryType == 1) {
            int id, time, priority;
            cin >> id >> time >> priority;
            manager.addTask(id, time, priority);
        } else if (queryType == 2) {
            cout << manager.getHighestPriorityTask() << endl;
        } else if (queryType == 3) {
            int id;
            cin >> id;
            manager.removeTask(id);
        }
    }

    return 0;
}
 JAVA
--------------------------------------------------------------------------------------------------------------------------------------------------------

import java.util.*;

class TaskManager {
    private static class Task {
        int id, time, priority;

        Task(int id, int time, int priority) {
            this.id = id;
            this.time = time;
            this.priority = priority;
        }
    }

    private List<Task> tasks = new ArrayList<>();
    private Map<Integer, Integer> taskIndex = new HashMap<>();

    // Comparator for sorting tasks by priority and then time
    private static Comparator<Task> taskComparator = (a, b) -> {
        if (a.priority == b.priority)
            return Integer.compare(a.time, b.time);
        return Integer.compare(b.priority, a.priority);
    };

    public void addTask(int id, int time, int priority) {
       
    }

    public int getHighestPriorityTask() {
       
    }

    public void removeTask(int id) {
       
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        TaskManager manager = new TaskManager();

        int n = sc.nextInt();
        for (int i = 0; i < n; ++i) {
            int id = sc.nextInt();
            int time = sc.nextInt();
            int priority = sc.nextInt();
            manager.addTask(id, time, priority);
        }

        int q = sc.nextInt();
        while (q-- > 0) {
            int queryType = sc.nextInt();
            if (queryType == 1) {
                int id = sc.nextInt();
                int time = sc.nextInt();
                int priority = sc.nextInt();
                manager.addTask(id, time, priority);
            } else if (queryType == 2) {
                System.out.println(manager.getHighestPriorityTask());
            } else if (queryType == 3) {
                int id = sc.nextInt();
                manager.removeTask(id);
            }
        }
    }
}
PYTHON
--------------------------------------------------------------------------------------------------------------------------------------------------------


class TaskManager:
    class Task:
        def __init__(self, task_id, time, priority):
            self.id = task_id
            self.time = time
            self.priority = priority

    def __init__(self):
        self.tasks = []
        self.task_index = {}

    def add_task(self, task_id, time, priority):
       

    def get_highest_priority_task(self):
        

    def remove_task(self, task_id):
       

if __name__ == "__main__":
    manager = TaskManager()

    n = int(input())
    for _ in range(n):
        task_id, time, priority = map(int, input().split())
        manager.add_task(task_id, time, priority)

    q = int(input())
    for _ in range(q):
        query = input().split()
        query_type = int(query[0])

        if query_type == 1:
            task_id, time, priority = map(int, query[1:])
            manager.add_task(task_id, time, priority)
        elif query_type == 2:
            print(manager.get_highest_priority_task())
        elif query_type == 3:
            task_id = int(query[1])
            manager.remove_task(task_id)
