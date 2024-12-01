# Student Attendance Management System

## Problem Statement

A school requires a digital system to manage the attendance of students effectively. Your task is to implement a Student Attendance Management System that offers the following functionalities:

1. **Add Student:** Register a new student by capturing their name, roll number, and class.
2. **Mark Attendance:** Record the attendance for a specific student as either Present, Absent, or Late.
3. **View Attendance:** Display the complete attendance record of a specific student.
4. **Remove Student:** Delete a student’s record permanently from the system.

Handle all edges case appropriately.

Obtain the Boiler Plate code from `boilerplate_code.md` in C++/Java/Python.

---

### Input Format

1. **Student Details:**
   - `name`: Name of the student.
   - `roll_number`: A unique integer identifier for the student.
   - `class`: The class in which the student is enrolled.
2. **Attendance Details:**
   - `roll_number`: The unique roll number of the student.
   - `status`: The attendance status (Present, Absent, or Late).

---

### Output Format

- **Add Student:** Confirmation message, e.g., `"Student added: John Doe, Roll No: 101"`
- **Mark Attendance:** Confirmation message, e.g., `"Attendance marked for Roll No: 101 as Present"`
- **View Attendance:** List of all attendance records for the requested roll number.
- **Remove Student:** Confirmation message, e.g., `"Student with Roll No: 101 removed successfully"`

---

### Example Input 1

```
Add Student
Name: John Doe
Roll Number: 101
Class: 10A
```

### Example Output 1
```
Student added: John Doe, Roll No: 101
```
---
### Example Input 2

```
Mark Attendance
Roll Number: 101
Status: Present
```

### Example Output 2
```
Attendance marked for Roll No: 101 as Present
```

### Example Input 3
---
```
View Attendance
Roll Number: 101
```

### Example Output 3
```
Attendance record for Roll No: 101:
1. Present
2. Absent
3. Late
```
---
### Example Input 4

```
Remove Student
Roll Number: 101
```

### Example Output 4
```
Student with Roll No: 101 removed successfully
```

## Constraints
- Each roll number must be unique.
- The attendance status can only be Present, Absent, or Late.
- Students must be added before marking their attendance.
- Return message `Error: Student with Roll No: [roll number] does not exist` incase Mark Attendance / View Attendance / Remove Student operation is used for a studen that does not exist.
- Return message `Error: Student with Roll No: [roll number] already exists in database` incase Add Student operation tries to add a new student with pre-exisiting roll number.

