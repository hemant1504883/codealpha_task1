# codealpha_task1

Here's an explanation of the CGPA calculator program in C++ provided:

Objective:
The objective of this CGPA calculator program is to compute the Cumulative Grade Point Average (CGPA) based on the grades and credit hours of courses taken over multiple semesters. It allows users to input course details such as name, credits, and grade, calculates the GPA for each semester, and finally computes the CGPA from these GPAs.

 Key Points:
1. **Input**: Users input the number of courses for each semester along with details for each course (name, credits, and grade).
   
2. **GPA Calculation**: The GPA for each semester is calculated based on the grades (converted to GPA scale) and corresponding credit hours.
   
3. **CGPA Calculation**: Once GPAs for all semesters are calculated, the CGPA is computed by averaging these GPAs.
   
4. **Modularity**: The program is structured using functions (`calculateGPA` for semester GPA calculation and `calculateCGPA` for CGPA calculation) for clarity and reusability.
   
5. **User Interaction**: The program interacts with the user to input semester details, calculates GPAs, and prompts for adding more semesters until the user decides to stop.

Functions:
The program defines two main functions to achieve its objective:

1. **`calculateGPA`**:
   - **Parameters**: `vector<Course> courses`
   - **Functionality**: Calculates the GPA for a semester based on the grades and credit hours entered by the user. It uses a switch statement to convert letter grades (`A` to `F`) to corresponding GPA values and computes the weighted GPA for each course.
   - **Return**: Returns the GPA for the semester as a `double`.

2. **`calculateCGPA`**:
   - **Parameters**: `vector<double> gpas`
   - **Functionality**: Calculates the CGPA based on a vector of GPAs from multiple semesters. It computes the average of all GPAs.
   - **Return**: Returns the CGPA as a `double`.

 Example Usage:
Here’s how the program is structured and used in the `main` function:

```cpp
#include <iostream>
#include <vector>
#include <string>

using namespace std;

// Structure to represent a course
struct Course {
    string name;
    int credits;
    char grade;
};

// Function to calculate GPA for a semester
double calculateGPA(vector<Course> courses) {
    double totalCredits = 0.0;
    double totalGradePoints = 0.0;

    for (Course course : courses) {
        totalCredits += course.credits;

        switch (course.grade) {
            case 'A':
                totalGradePoints += course.credits * 4.0;
                break;
            case 'B':
                totalGradePoints += course.credits * 3.0;
                break;
            case 'C':
                totalGradePoints += course.credits * 2.0;
                break;
            case 'D':
                totalGradePoints += course.credits * 1.0;
                break;
            case 'F':
                totalGradePoints += course.credits * 0.0;
                break;
            default:
                cout << "Invalid grade." << endl;
                return 0.0;
        }
    }

    return totalGradePoints / totalCredits;
}

// Function to calculate CGPA
double calculateCGPA(vector<double> gpas) {
    double totalGPA = 0.0;

    for (double gpa : gpas) {
        totalGPA += gpa;
    }

    return totalGPA / gpas.size();
}

int main() {
    int numCourses;
    vector<Course> courses;
    vector<double> gpas;

    cout << "Enter the number of courses: ";
    cin >> numCourses;

    for (int i = 0; i < numCourses; i++) {
        Course course;
        cout << "Enter course name: ";
        cin >> course.name;
        cout << "Enter course credits: ";
        cin >> course.credits;
        cout << "Enter course grade: ";
        cin >> course.grade;

        courses.push_back(course);
    }

    double gpa = calculateGPA(courses);
    cout << "GPA for this semester: " << gpa << endl;
    gpas.push_back(gpa);

    char response;
    cout << "Do you want to add more semesters? (y/n): ";
    cin >> response;

    while (response == 'y') {
        courses.clear();
        cout << "Enter the number of courses: ";
        cin >> numCourses;

        for (int i = 0; i < numCourses; i++) {
            Course course;
            cout << "Enter course name: ";
            cin >> course.name;
            cout << "Enter course credits: ";
            cin >> course.credits;
            cout << "Enter course grade: ";
            cin >> course.grade;

            courses.push_back(course);
        }

        gpa = calculateGPA(courses);
        cout << "GPA for this semester: " << gpa << endl;
        gpas.push_back(gpa);
        cout << "Do you want to add more semesters? (y/n): ";
        cin >> response;
    }

    double cgpa = calculateCGPA(gpas);
    cout << "CGPA: " << cgpa << endl;

    return 0;
}

Output:




Explanation:
- Structure: Uses a `Course` structure to store course details (name, credits, grade).
- Functions: `calculateGPA` computes semester GPA based on user input, while `calculateCGPA` computes overall CGPA from a vector of semester GPAs.
- Main Function: Manages user interaction, input, and output. It allows users to enter multiple semesters, calculates GPA for each, and finally computes the CGPA.
