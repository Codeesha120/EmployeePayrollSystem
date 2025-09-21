package EmployeePayroll;

import java.util.ArrayList;


abstract class Employee{
	
	private String name;
	
	private int id;
	
	public Employee(String name, int id) {
		this.name=name;
		this.id=id;
	}
	public String getname() {
		return name;
		
	}
	public int getid() {
		return id;
		
	}
	// Abstract method to be implemented by subclasses
	public abstract  double calculateSalary() ;
		 
	 @Override 
	 public String toString() {
		 return "Employee[name="+name+", id="+id+",salary="+calculateSalary()+"]";
	 }
	 
	 
			
}
 class  FullTimeEmployee extends Employee{
	 
	 private double monthlySalary;
	 
	 public  FullTimeEmployee(String name, int id, double monthlySalary) {
		 super(name,id);
		 this.monthlySalary=monthlySalary;
		 }
		 
		 @Override
		 public double calculateSalary() {
			 return monthlySalary;
			 
		  }
 }
 
 class PartTimeEmployee  extends Employee{
	 
	 private int houresWork;
	 private double hourlyRate;
	 
	 public PartTimeEmployee( String name ,int id,int houresWork,int  hourlyRate) {
		 super(name,id);
		 this.houresWork=houresWork;
		 this.hourlyRate= hourlyRate;
	 }
	 @Override
	 public double calculateSalary() {
		 return houresWork * hourlyRate;
		 
	  }
}
	 
//ArrayList<Integer>arr= new ArrayList<>(); 
 //It uses an ArrayList<Employee> to dynamically hold multiple employees.
 class PayRollSystem  {
	 private  ArrayList<Employee> employeeList;
	 
	 public PayRollSystem() {
		 employeeList =new ArrayList<>();
	 }
	 
	 public void addEmployee(Employee employee) {
		 employeeList.add(employee);
	 }
	 
	 public void romoveEmployee( int id) {
		 Employee employeeToRemovw=null;
		 for(Employee employee: employeeList) {
			 if(employee.getid()==id) {
				 employeeToRemovw=employee;
				 break;
			 }
			 
		 }
		 if(employeeToRemovw != null) {
			 employeeList.remove(employeeToRemovw);
		 }
		 
	 }
	 public void displayEmployee()
	 {
		for(Employee employee: employeeList) {
			System.out.println(employee);
		}
	 }
 }
public class EmpMain {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		PayRollSystem  payRollSystem = new PayRollSystem ();
		
		 FullTimeEmployee emp1 = new FullTimeEmployee("Esha", 1, 70000.0);
		 // Create and add a part-time employee
		 PartTimeEmployee emp2 = new PartTimeEmployee("Atul", 2, 40, 200);
	    
		 payRollSystem.addEmployee(emp1);
		 
		 payRollSystem.addEmployee(emp2);
		 System.out.println("Initial Employee Details:");
		 
		 System.out.println();
		 
		 
		 payRollSystem.displayEmployee();
		 System.out.println("Rmoveing Employees");
		 
		 System.out.println();
		 
		 
		 payRollSystem.romoveEmployee(2);
		 System.out.println("Remaining Employees Details :");
		 
		 
		 System.out.println();
		 payRollSystem.displayEmployee();
	}

}
