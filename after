import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class StudentGradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of students: ");
        int numberOfStudents = scanner.nextInt();

        List<Student> students = new ArrayList<>();

        for (int i = 0; i < numberOfStudents; i++) {
            students.add(createStudent(scanner, i + 1));
        }

        double averageGrade = calculateAverageGrade(students);

        printStudentGradeReport(students, averageGrade);
    }

    private static Student createStudent(Scanner scanner, int studentNumber) {
        System.out.print("Enter the name of student " + studentNumber + ": ");
        String name = scanner.next();

        System.out.print("Enter the grade of student " + studentNumber + ": ");
        double grade = scanner.nextDouble();

        return new Student(name, grade);
    }

    private static double calculateAverageGrade(List<Student> students) {
        double total = 0.0;
        for (Student student : students) {
            total += student.getGrade();
        }
        return total / students.size();
    }

    private static void printStudentGradeReport(List<Student> students, double averageGrade) {
        System.out.println("\nStudent Grade Report:");
        for (Student student : students) {
            System.out.println(student.getName() + ": " + student.getGrade());
        }

        System.out.println("\nAverage Grade: " + averageGrade);
    }
}

class Student {
    private String name;
    private double grade;

    public Student(String name, double grade) {
        this.name = name;
        this.grade = grade;
    }

    public String getName() {
        return name;
    }

    public double getGrade() {
        return grade;
    }
}
