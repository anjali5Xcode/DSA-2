Task Management System
**********************

Problem Statement
------------------
A company uses a task management system to assign tasks to employees. Each task has an associated ID, estimated completion time, and priority level. Your task is to create a system that processes a list of tasks and retrieves information based on user queries.

The system should perform the following operations:

Add Task: Add a new task with its details.
Retrieve Highest Priority Task: Retrieve the task ID with the highest priority and the shortest estimated time if there are ties.
Remove Task: Remove a task based on its ID.
Input Format
Number of Tasks: n (integer)

Task Details: A list of tasks, where each task is represented as:

task_id: Unique identifier for the task (integer).
time: Estimated time to complete the task (integer in hours).
priority: Priority level of the task (integer, higher is more important).
Queries: A list of queries, where each query can be:

1 task_id time priority: Add a task with the given details.
2: Retrieve the task ID of the highest priority task.
3 task_id: Remove the task with the given ID.
Output Format
For each query of type 2, output the task ID with the highest priority. If no tasks are available, output -1.
---------------------------------------------------------------------------------------------------------------------------------------------------------
Example Input
plaintext
Copy code
Number of Tasks: 3
Tasks:
1 5 10
2 3 8
3 2 10
Queries:
1 4 4 7
2
3 1
2
Example Output
plaintext
Copy code
2
3
---------------------------------------------------------------------------------------------------------------------------------------------------------
Constraints
1 <= n <= 100
1 <= time <= 100
1 <= priority <= 10
All task IDs are unique.
The number of queries does not exceed 200.
