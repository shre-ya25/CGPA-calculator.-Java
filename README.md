# CGPA-calculator.-Java
📘 What is CGPA? (Cumulative Grade Point Average)

CGPA is a number that represents a student's overall academic performance in a course over a period of time—typically across semesters or years.


---

🧮 CGPA Formula

> CGPA = Total Grade Points Earned / Total Number of Subjects



Each subject is assigned a grade, and each grade has a numeric value (called a grade point). The CGPA is the average of these grade points.


---

🎯 Grade to Grade Point Example (10-point scale)


---

📌 Example Without Credits

Suppose a student has 5 subjects with the following grade points:

Subject 1: 9

Subject 2: 8

Subject 3: 10

Subject 4: 7

Subject 5: 8


Then:

Total Grade Points = 9 + 8 + 10 + 7 + 8 = 42
Number of Subjects = 5

CGPA = 42 / 5 = 8.4


---

📌 Example With Credits (Weighted CGPA)

Each subject may carry different credits (weight). Use this formula:

> CGPA = (Sum of (Grade Point × Credit)) / (Total Credits)



Example:

Total = (10×4) + (8×3) + (7×3) = 40 + 24 + 21 = 85
Total Credits = 4 + 3 + 3 = 10

CGPA = 85 / 10 = 8.5


---

🧠 Key Points:

CGPA shows your average performance, not just a single semester.

SGPA (Semester GPA) is for one semester; CGPA combines all semesters.

CGPA is not a percentage. Some universities convert it using:

> Percentage = CGPA × 9.5 (used by CBSE, India)

Here's a java code for cgpa calculator 

import java.util.Scanner;

class CGPACalculator {
    private double[] marks;
    private int[] credits;

    public CGPACalculator(double[] marks, int[] credits) {
        this.marks = marks;
        this.credits = credits;
    }

    public double calculateCGPA() {
        double totalGradePoints = 0.0;
        int totalCredits = 0;
        
        for (int i = 0; i < marks.length; i++) {
            double grade = marks[i] / 10.0;
            totalGradePoints += grade * credits[i];
            totalCredits += credits[i];
        }
        return totalGradePoints / totalCredits;
    }
}

public class CGPA {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the number of subjects:");
        int n = sc.nextInt();

        double[] marks = new double[n];
        int[] credits = new int[n];
        
        System.out.println("Enter marks and credits for each subject:");
        for (int i = 0; i < n; i++) {
            System.out.print("Subject " + (i + 1) + " marks: ");
            marks[i] = sc.nextDouble();
            System.out.print("Subject " + (i + 1) + " credits: ");
            credits[i] = sc.nextInt();
        }

        CGPACalculator calculator = new CGPACIndicator(marks, credits);
        double cgpa = calculator.calculateCGPA();
        System.out.println("CGPA: " + cgpa);

        sc.close();
    }
}
