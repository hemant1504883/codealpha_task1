Name: Hemant Baghel
Company: CODE ALPHA
ID: CA/JL1/20299
Domain: C++ programming 
Duration: 15 July to 15 August
 

Overview of the Project

Project: Creating a cgpa calculator using C++ programming

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
#
# OUTPUT-
![Screenshot (42)](https://github.com/user-attachments/assets/53187b82-f812-4d50-a493-83b2b5e4c0ec)


