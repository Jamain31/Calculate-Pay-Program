# Calculate-Pay-Program
This application stores employees into a list and calculate their gross income.

 This program prompt the user to enter the employee’s name, rate of pay, and hours worked. The output display the information entered into the program along with the calculations for gross pay, total amount of deductions, and net pay.
 
 calculatePayProgram<Source Code>
 
 package calculatePayProgram;

import java.util.Scanner;

public class program {

	public static void main(String[] args) {
		// Calculate Pay Program
		// Jamain Hughes
		// CPT307: Data Structures and Algorithms
		// Carl Marquez
		//9/19/2022
		Scanner keyboard = new Scanner(System.in);
		
		// Varible declaration
		final int Standard_Work = 40;
		String empName;
		double hoursWorked;
		double hourlyRate;
		double basicPay;
		double overTimeWorked = 0;
		double overTimeRate;
		double overTimePay;
		double overTimeSalary;
		double grossSalary;
		double amountDeduction;
		double federalTaxAmount;
		double stateTaxAmount;
		double medicareAmount;
		double socialSecurityAmount;
		double unemployedInsuranceAmount;
		double totalDeductions;
		double netPay;
		
		// Input Statements
		System.out.println(" ---------Welcome to my Calculate Pay Program.-----------");
		System.out.print(" Enter an employee's Name ");
		empName = keyboard.nextLine();
		System.out.print(" Enter the number of hours worked ");
		hoursWorked = keyboard.nextDouble();
		System.out.print(" Enter the hourly rate ");
		hourlyRate = keyboard.nextDouble();
		
		// Solutions
		if (hoursWorked <= Standard_Work) {
			basicPay = hoursWorked * hourlyRate;
			grossSalary = keyboard.nextDouble();
		}
		else {
			basicPay = Standard_Work * hourlyRate;
			overTimeRate = hoursWorked - Standard_Work;
			overTimeRate = hourlyRate * 1.5;
			overTimePay = overTimeRate * overTimeWorked;
			grossSalary = basicPay + overTimePay;
		}
		// Tax deduction Solutions
		federalTaxAmount = 15 * grossSalary;
		stateTaxAmount = 3.07 * grossSalary;
		medicareAmount = 1.45 * grossSalary;
		socialSecurityAmount = 6.2 * grossSalary;
		unemployedInsuranceAmount = .07 * grossSalary;
		totalDeductions = federalTaxAmount + stateTaxAmount + medicareAmount + socialSecurityAmount + unemployedInsuranceAmount;
		netPay = grossSalary - totalDeductions;
		
	
		
		// Print
		System.out.println(" Employee name: " + empName + " Rate of Pay: " + hourlyRate + " Hours Worked: " + hoursWorked + " Overtime Worked " + overTimeWorked + " Gross Pay: " + grossSalary + " Total Amount of Deductions" + totalDeductions + " NetPay " + netPay );

	}

}

![calculatepaycreenshot](https://user-images.githubusercontent.com/108758588/195983034-29219c3d-9b7e-4bd2-a5d0-12935bf2fed9.png)
