import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class RefactoredStudentGradeCalculator {

    public static void runStudentGradeCalculator(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of students: ");
        int numberOfStudents = scanner.nextInt();
        scanner.nextLine(); // Consume the newline character

        List<String> studentNames = new ArrayList<>();
        List<Double> studentGrades = new ArrayList<>();

        for (int i = 0; i < numberOfStudents; i++) {
            System.out.print("Enter the name of student " + (i + 1) + ": ");
            String name = scanner.nextLine();
            studentNames.add(name);

            System.out.print("Enter the grade of student " + (i + 1) + ": ");
            double grade = scanner.nextDouble();
            studentGrades.add(grade);
            scanner.nextLine(); // Consume the newline character
        }

        double average = calculateAverage(studentGrades);

        printGradeReport(studentNames, studentGrades, average);
    }

    private static double calculateAverage(List<Double> grades) {
        double sum = 0.0;
        for (Double grade : grades) {
            sum += grade;
        }
        return sum / grades.size();
    }

    private static void printGradeReport(List<String> names, List<Double> grades, double average) {
        System.out.println("\nStudent Grade Report:");
        for (int i = 0; i < names.size(); i++) {
            System.out.println(names.get(i) + ": " + grades.get(i));
        }
        System.out.println("\nAverage Grade: " + average);
    }

    public static void main(String[] args) {
        runStudentGradeCalculator(args);
    }
}
