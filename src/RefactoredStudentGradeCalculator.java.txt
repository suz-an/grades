import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;

public class RefactoredStudentGradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of students: ");
        int numberOfStudents = scanner.nextInt();
        scanner.nextLine(); // Consume newline

        List<String> studentNames = new ArrayList<>();
        List<Double> studentGrades = new ArrayList<>();

        for (int i = 0; i < numberOfStudents; i++) {
            String name = getStudentName(scanner, i);
            studentNames.add(name);

            double grade = getStudentGrade(scanner, i);
            studentGrades.add(grade);
        }

        displayGradeReport(studentNames, studentGrades);
    }

    private static String getStudentName(Scanner scanner, int index) {
        System.out.print("Enter the name of student " + (index + 1) + ": ");
        return scanner.nextLine();
    }

    private static double getStudentGrade(Scanner scanner, int index) {
        System.out.print("Enter the grade of student " + (index + 1) + ": ");
        while (!scanner.hasNextDouble()) {
            System.out.println("Invalid input. Please enter a numeric grade.");
            scanner.next(); // Clear invalid input
        }
        return scanner.nextDouble();
    }

    private static void displayGradeReport(List<String> studentNames, List<Double> studentGrades) {
        double average = calculateAverage(studentGrades);

        System.out.println("\nStudent Grade Report:");
        for (int i = 0; i < studentNames.size(); i++) {
            System.out.println(studentNames.get(i) + ": " + studentGrades.get(i));
        }

        System.out.printf("\nAverage Grade: %.2f%n", average);
    }

    private static double calculateAverage(List<Double> grades) {
        double sum = 0.0;
        for (double grade : grades) {
            sum += grade;
        }
        return grades.isEmpty() ? 0.0 : sum / grades.size();
    }
}
