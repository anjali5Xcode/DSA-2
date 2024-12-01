## Boilerplate Code

### C++
```C++
#include <iostream>
#include <unordered_map>
#include <string>
#include <vector>

using namespace std;

class Student {
public:
    string name;
    int rollNumber;
    string className;
    vector<string> attendanceRecord;

    // Default constructor
    Student() {}

    // Parameterized constructor
    Student(string n, int roll, string c) {}

    void markAttendance(string status);
    void viewAttendance();
};

class AttendanceSystem {
private:
    unordered_map<int, Student> students;

public:
    // Method declaration
    void addStudent(string name, int rollNumber, string className);

    void markAttendance(int rollNumber, string status);

    void viewAttendance(int rollNumber);

    void removeStudent(int rollNumber);
};

int main() {
    AttendanceSystem system;
    int choice;
    int rollNumber;
    string name, className, status;

    while (true) {
        cout << "\n----- Student Attendance Management System -----\n";
        cout << "1. Add Student\n";
        cout << "2. Mark Attendance\n";
        cout << "3. View Attendance\n";
        cout << "4. Remove Student\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter student name: ";
                cin.ignore();
                getline(cin, name);
                cout << "Enter roll number: ";
                cin >> rollNumber;
                cout << "Enter class name: ";
                cin.ignore();
                getline(cin, className);
                // Call system.addStudent(name, rollNumber, className);
                break;

            case 2:
                cout << "Enter roll number: ";
                cin >> rollNumber;
                cout << "Enter attendance status (Present, Absent, Late): ";
                cin >> status;
                // Call system.markAttendance(rollNumber, status);
                break;

            case 3:
                cout << "Enter roll number: ";
                cin >> rollNumber;
                // Call system.viewAttendance(rollNumber);
                break;

            case 4:
                cout << "Enter roll number: ";
                cin >> rollNumber;
                // Call system.removeStudent(rollNumber);
                break;

            case 5:
                cout << "Exiting the system.\n";
                return 0;

            default:
                cout << "Invalid choice! Please try again.\n";
        }
    }

    return 0;
}

```


### Java
```Java
import java.util.*;

class Student {
    String name;
    int rollNumber;
    String className;
    List<String> attendanceRecord;

    // Default constructor
    public Student() {}

    // Parameterized constructor
    public Student(String name, int rollNumber, String className) {}

    public void markAttendance(String status) {}
    public void viewAttendance() {}
}

class AttendanceSystem {
    private Map<Integer, Student> students;

    public AttendanceSystem() {
        students = new HashMap<>();
    }

    // Method declarations
    public void addStudent(String name, int rollNumber, String className) {}
    public void markAttendance(int rollNumber, String status) {}
    public void viewAttendance(int rollNumber) {}
    public void removeStudent(int rollNumber) {}
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        AttendanceSystem system = new AttendanceSystem();
        int choice;
        int rollNumber;
        String name, className, status;

        while (true) {
            // Display menu
            System.out.println("\n----- Student Attendance Management System -----");
            System.out.println("1. Add Student");
            System.out.println("2. Mark Attendance");
            System.out.println("3. View Attendance");
            System.out.println("4. Remove Student");
            System.out.println("5. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            scanner.nextLine();  

            switch (choice) {
                case 1:
                    // Add student
                    System.out.print("Enter student name: ");
                    name = scanner.nextLine();
                    System.out.print("Enter roll number: ");
                    rollNumber = scanner.nextInt();
                    scanner.nextLine();  
                    System.out.print("Enter class name: ");
                    className = scanner.nextLine();
                    // Call system.addStudent(name, rollNumber, className);
                    break;

                case 2:
                    // Mark attendance
                    System.out.print("Enter roll number: ");
                    rollNumber = scanner.nextInt();
                    scanner.nextLine(); 
                    System.out.print("Enter attendance status (Present, Absent, Late): ");
                    status = scanner.nextLine();
                    // Call system.markAttendance(rollNumber, status);
                    break;

                case 3:
                    // View attendance
                    System.out.print("Enter roll number: ");
                    rollNumber = scanner.nextInt();
                    // Call system.viewAttendance(rollNumber);
                    break;

                case 4:
                    // Remove student
                    System.out.print("Enter roll number: ");
                    rollNumber = scanner.nextInt();
                    // Call system.removeStudent(rollNumber);
                    break;

                case 5:
                    // Exit the system
                    System.out.println("Exiting the system.");
                    scanner.close();
                    return;

                default:
                    System.out.println("Invalid choice! Please try again.");
            }
        }
    }
}
```


### Python
```Python
class Student:
    def __init__(self, name="", roll_number=0, class_name=""):
        self.name = name
        self.roll_number = roll_number
        self.class_name = class_name
        self.attendance_record = []

    # Method declarations
    def mark_attendance(self, status):
        pass

    def view_attendance(self):
        pass


class AttendanceSystem:
    def __init__(self):
        self.students = {}

    # Method declarations
    def add_student(self, name, roll_number, class_name):
        pass

    def mark_attendance(self, roll_number, status):
        pass

    def view_attendance(self, roll_number):
        pass

    def remove_student(self, roll_number):
        pass


# Main loop with menu options
if __name__ == "__main__":
    system = AttendanceSystem()

    while True:
        print("\n----- Student Attendance Management System -----")
        print("1. Add Student")
        print("2. Mark Attendance")
        print("3. View Attendance")
        print("4. Remove Student")
        print("5. Exit")
        choice = int(input("Enter your choice: "))

        if choice == 1:
            # Add student
            name = input("Enter student name: ")
            roll_number = int(input("Enter roll number: "))
            class_name = input("Enter class name: ")
            # system.add_student(name, roll_number, class_name)

        elif choice == 2:
            # Mark attendance
            roll_number = int(input("Enter roll number: "))
            status = input("Enter attendance status (Present, Absent, Late): ")
            # system.mark_attendance(roll_number, status)

        elif choice == 3:
            # View attendance
            roll_number = int(input("Enter roll number: "))
            # system.view_attendance(roll_number)

        elif choice == 4:
            # Remove student
            roll_number = int(input("Enter roll number: "))
            # system.remove_student(roll_number)

        elif choice == 5:
            print("Exiting the system.")
            break

        else:
            print("Invalid choice! Please try again.")

```