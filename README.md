# metho-overloading-seni

package com.raj.blc;

public class Employee1 {
protected int id;
protected String name;
public Employee1(int id, String name) 
{
	super();
	if(id<=0) {
		System.err.println("Id must be +ve");
		System.exit(0);
	}
//	if(name.trim().isEmpty()) {
//		System.err.println("Name feild is Mandatory");
//		System.exit(0);
//	}
	this.id = id;
	this.name = name;
}

public  double calculateSalary() 
{
	
	return 0.0;
	
}


}
//
package com.raj.blc;

public class FullTimeEmployee extends Employee1{
	protected double salary;

	public FullTimeEmployee(int id, String name, double salary)
	{
		super(id, name);
		if(salary <=0) 
		{
			System.err.println("Salary can't be negative!!!");
			System.exit(0);
		}
		this.salary = salary;
		
		
		
	}
	@Override
	public double calculateSalary() {
		
		return salary;
	}
	

}

//
package com.raj.blc;

public class PartTimeEmployee extends Employee1 {
	protected double hourlyRate;
	protected int hoursWorked;
	public PartTimeEmployee(int id, String name, double hourlyRate, int hoursWorked) {
		super(id, name);
		if(hourlyRate<=0) {
			System.err.println("Employee hourly rate can't be zero OR Negative");
			System.exit(0);
		}		
		if(hoursWorked<=0) 
		{
			System.err.println("Employee hours of work can't be Negative");
			System.exit(0);
		}
		this.hourlyRate = hourlyRate;
		this.hoursWorked = hoursWorked;
	}
	@Override
public double calculateSalary() 
	{
	
		return hourlyRate*hoursWorked;
	
}
}

elc file 
package com.raj.elc;

import java.util.Scanner;
import com.raj.blc.Employee1;
import com.raj.blc.FullTimeEmployee;
import com.raj.blc.PartTimeEmployee;

public class EmployeeSalary {

	public static void main(String[] args) {
		Scanner sc=new Scanner(System.in);
		Employee1 emp=null;
		System.out.println("***Salary Calculation Menu***	");
		System.out.println("1) FullTime Employees ");
		System.out.println("2) PartTime Employees  ");
		System.out.println("Please select the Employee type");
		int option=sc.nextInt();
		switch(option) {
		case 1 : 
			System.out.println("Enter   Fulltime  Employee Id :");
			int id=sc.nextInt();
			System.out.println("Enter   Fulltime  Employee Name :");
			String name=sc.nextLine();
			name=sc.nextLine();
		System.out.println("Enter Fulltime Employee  salary :");
		double salary=sc.nextDouble();
		emp=new FullTimeEmployee(id, name, salary);
		 
		  System.out.println(name+" Salary is :"+emp.calculateSalary());
		break;
		
		case 2:
			System.out.println("Enter   PartTime Employee Id :");
			int id1=sc.nextInt();
			System.out.println("Enter PartTime Employee Name :");
			String name1=sc.nextLine();
			name=sc.nextLine();
			System.out.println("Enter your hourly rate:");
			double hourate=sc.nextDouble();
			System.out.println("Enter your total works hour in the month :");
			int hoursWorked=sc.nextInt();
			emp=new PartTimeEmployee(id1, name1,  hourate,  hoursWorked);
			System.out.println(name+"salary is"+emp.calculateSalary());
			break;
			
	  default : System.out.println("invalid choise ");
	 
		}

	}

}




