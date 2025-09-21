# Employee Payroll System

A simple Java-based Employee Payroll System demonstrating Object-Oriented Programming concepts such as **abstraction**, **inheritance**, and **polymorphism**.

This system allows you to manage **full-time** and **part-time** employees, calculate salaries, add or remove employees, and display employee details dynamically using an `ArrayList`.

---

## Features

- Add full-time and part-time employees
- Calculate salaries based on type
- Remove employees by ID
- Display employee details

---

## Classes Overview

1. **Employee (abstract class)**  
   - Holds common properties like `name` and `id`  
   - Abstract method `calculateSalary()` to be implemented by subclasses  

2. **FullTimeEmployee (subclass of Employee)**  
   - Stores `monthlySalary`  
   - Implements `calculateSalary()` to return `monthlySalary`  

3. **PartTimeEmployee (subclass of Employee)**  
   - Stores `hoursWorked` and `hourlyRate`  
   - Implements `calculateSalary()` as `hoursWorked * hourlyRate`  

4. **PayRollSystem**  
   - Manages an `ArrayList<Employee>`  
   - Methods to add, remove, and display employees  

5. **EmpMain**  
   - Main class to test the payroll system functionality  

---

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/EshaGolhar/EmployeePayrollSystem.git

