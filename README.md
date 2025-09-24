// on 17/09/2025
# JAVA_PROGRAMMING_UWIMANA_AMINA_223009215_BIT_YEAR3
**Case study one**: Supermarket Billing System

package myassignment.java;

import java.util.Scanner;

public class supermarketbilling {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		 Scanner sc = new Scanner(System.in);
		 System.out.print("Enter number of different items customer bought: ");
	        int n = sc.nextInt();
	     // Arrays for storing item details
	        String[] itemName = new String[n];
	        double[] price = new double[n];
	        int[] quantity = new int[n];
	        double[] subtotal = new double[n];
	        
	        double total = 0;
	        // Input using for loop
	        for (int i = 0; i < n; i++) {
	            System.out.println("\nEnter name of item " + (i + 1) + ": ");
	            itemName[i] = sc.next();

	            System.out.print("Enter price per unit of " + itemName[i] + ": ");
	            price[i] = sc.nextDouble();

	            System.out.print("Enter quantity of " + itemName[i] + ": ");
	            quantity[i] = sc.nextInt();

	            subtotal[i] = price[i] * quantity[i];
	            total += subtotal[i];
	        }
	        // Apply discount
	        double discount = 0;
	        if (total > 50000) {
	            discount = total * 0.05;
	        }
	        double finalAmount = total - discount;
	        // Print receipt
	        System.out.println("\n========== SUPERMARKET RECEIPT ==========");
	        System.out.println();

	        for (int i = 0; i < n; i++) {
	            System.out.println();
	        }
	        System.out.println("\nGrand Total: " + total + " Rwf");
	        System.out.println("Discount: " + discount + " Rwf");
	        System.out.println("Final Amount Payable: " + finalAmount + " Rwf");
	        System.out.println("=========================================");

	        sc.close();
	        
	}

}
**case study 2:**  Student Grading System

package myassignment.java;
import java.util.Scanner;

public class gradingsystem {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		        Scanner input = new Scanner(System.in);
		        
		        int totalStudents = 0;
		        int passe = 0;
		        int fail= 0;
		        
		        System.out.println("=============GRADING SYSTEM ===========================");
		        System.out.println("Enter student marks between 0 to 100");
		        while (true) {
		            System.out.print("Enter marks: ");
		            int marks = input.nextInt();
		            if (marks == -1) {
		                break;
		            }
		            
		            totalStudents++;
		            String grade;
		            if (marks >= 80) {
		                grade = "A";
		            } else if (marks >= 70) {
		                grade = "B";
		            } else if (marks >= 60) {
		                grade = "C";
		            } else if (marks >= 50) {
		                grade = "D";
		            } else {
		                grade = "F";
		            }
		            
		            System.out.println("Grade: " + grade);
		            
		            // Count passes and fails
		            if (marks >= 50) {
		                passe++;
		            } else {
		                fail++;
		            }
		        }
		        
		        // Print summary report
		        System.out.println("=============== SUMMARY REPORT =======================");
		        System.out.println("Total number of students: " + totalStudents);
		        System.out.println(" if you Passed: " + passe);
		        System.out.println(" if you Failed: " + fail);
		        
		        if (totalStudents > 0) {
		            double passRate = (passe * 100) / totalStudents;
		            System.out.println("Pass rate: " + passRate + "%");
		        }
				input.close();
		    }
		
	}

	**case study 3**  Class Attendance Tracker

 package myassignment.java;
import java.util.Scanner;

public class attendancetracker {

	/**
	 * @param args
	 */
	public static void main(String[] args) {
		        Scanner input = new Scanner(System.in);		                
		        System.out.print("Enter total student number of class ");
		                int totalStudents = input.nextInt();
		                
		                int[] attendance = new int[30];
		                int dayCount = 0;
		                String continueInput;
		                
		                System.out.println("===================== attendance list=================================== ===");
		                
		             
		                do {
		                    System.out.print("Day " + (dayCount + 1) + "available Students : ");
		                    attendance[dayCount] = input.nextInt();
		                    dayCount++;
		                    
		                    System.out.print("Enter attendance for other day? (yes/no): ");
		                    continueInput = input.next();
		                    
		                } while (continueInput.equals("yes") && dayCount < 30);
		                int totalAttendance = 0;
		                for (int i = 0; i < dayCount; i++) {
		                    totalAttendance += attendance[i];
		                }
		                double average = (double) totalAttendance / dayCount;
		                int lowAttendanceDays = 0;
		                for (int i = 0; i < dayCount; i++) {
		                    if (attendance[i] < totalStudents * 0.5) {
		                        lowAttendanceDays++;
		                    }
		                }
		          
		                System.out.println("\n=== ATTENDANCE general ===");
		                System.out.println("Day\tStudents available");
		                System.out.println("\t_");
		                for (int i = 0; i < dayCount; i++) {
		                    System.out.println((i + 1) + "\t" + attendance[i]);
		                }
		                       System.out.println("=============================== STATISTICS ==================");
		                System.out.println("Total days recorded: " + dayCount);
		                System.out.println("Average : " + average);
		                System.out.println("Days with low attendance : " + lowAttendanceDays);
		                
		                double lowAttendancePercentage = (double) lowAttendanceDays / dayCount * 100;
		                System.out.println("low attendance days on 100: " + lowAttendancePercentage + "%");
		                
		                input.close();
		            }
		            
		        }

