#include <iostream>
#include <vector>
using namespace std;

struct Assignment {
    int id;
    string title;
    string subject;
    bool submitted;
};

vector<Assignment> assignments;
int counter = 1;

// Add assignment
void addAssignment() {
    Assignment a;
    a.id = counter++;
    cout << "Enter title: ";
    cin.ignore();
    getline(cin, a.title);

    cout << "Enter subject: ";
    getline(cin, a.subject);

    a.submitted = false;
    assignments.push_back(a);

    cout << "Assignment added successfully!\n";
}

// View assignments
void viewAssignments() {
    if (assignments.empty()) {
        cout << "No assignments found.\n";
        return;
    }

    for (auto &a : assignments) {
        cout << "\nID: " << a.id;
        cout << "\nTitle: " << a.title;
        cout << "\nSubject: " << a.subject;
        cout << "\nStatus: " << (a.submitted ? "Submitted" : "Pending") << "\n";
    }
}

// Submit assignment
void submitAssignment() {
    int id;
    cout << "Enter assignment ID to submit: ";
    cin >> id;

    for (auto &a : assignments) {
        if (a.id == id) {
            a.submitted = true;
            cout << "Assignment submitted!\n";
            return;
        }
    }
    cout << "Assignment not found.\n";
}

// Delete assignment
void deleteAssignment() {
    int id;
    cout << "Enter assignment ID to delete: ";
    cin >> id;

    for (auto it = assignments.begin(); it != assignments.end(); ++it) {
        if (it->id == id) {
            assignments.erase(it);
            cout << "Assignment deleted.\n";
            return;
        }
    }
    cout << "Assignment not found.\n";
}

int main() {
    int choice;

    do {
        cout << "\n--- Assignment Management System ---\n";
        cout << "1. Add Assignment\n";
        cout << "2. View Assignments\n";
        cout << "3. Submit Assignment\n";
        cout << "4. Delete Assignment\n";
        cout << "5. Exit\n";
        cout << "Enter choice: ";
        cin >> choice;

        switch (choice) {
            case 1: addAssignment(); break;
            case 2: viewAssignments(); break;
            case 3: submitAssignment(); break;
            case 4: deleteAssignment(); break;
            case 5: cout << "Exiting...\n"; break;
            default: cout << "Invalid choice!\n";
        }

    } while (choice != 5);

    return 0;
}
