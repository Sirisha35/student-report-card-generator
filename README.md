import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of students: ");
        int studentCount = sc.nextInt();
        sc.nextLine(); // consume newline

        for (int i = 0; i < studentCount; i++) {
            System.out.println("\nEnter details for Student " + (i + 1) + ":");

            System.out.print("Enter Student Name: ");
            String name = sc.nextLine();

            System.out.print("Enter Roll Number: ");
            int rollNumber = sc.nextInt();
            sc.nextLine();

            System.out.print("Enter number of subjects: ");
            int numSubjects = sc.nextInt();
            sc.nextLine();

            Subject[] subjects = new Subject[numSubjects];

            for (int j = 0; j < numSubjects; j++) {
                System.out.print("Enter name of subject " + (j + 1) + ": ");
                String subjectName = sc.nextLine();

                System.out.print("Enter marks for " + subjectName + ": ");
                int marks = sc.nextInt();
                sc.nextLine();

                subjects[j] = new Subject(subjectName, marks);
            }

            Student student = new Student(name, rollNumber, subjects);
            ReportCard.printReport(student);  // Print and save to file
        }

        System.out.println("\n--- All Students Report Cards from File ---");
        ReportCard.displayAllReports();

        sc.close();
    }
}
