# Database Schema Design for HR Management System

## Tables

### Users
- **user_id** (INT, Primary Key): Unique identifier for each user
- **username** (VARCHAR): Username of the user
- **password** (VARCHAR): Password for user authentication
- **role** (VARCHAR): Role of the user (e.g., Admin, HR, Employee)
- **created_at** (DATETIME): Timestamp of when the user was created

### Employees
- **employee_id** (INT, Primary Key): Unique identifier for each employee
- **first_name** (VARCHAR): Employee's first name
- **last_name** (VARCHAR): Employee's last name
- **email** (VARCHAR): Employee's email address
- **phone** (VARCHAR): Employee's phone number
- **hire_date** (DATETIME): Date when the employee was hired
- **department_id** (INT, Foreign Key): References department table

### Departments
- **department_id** (INT, Primary Key): Unique identifier for each department
- **department_name** (VARCHAR): Name of the department

### Salaries
- **salary_id** (INT, Primary Key): Unique identifier for each salary record
- **employee_id** (INT, Foreign Key): References employee
- **amount** (DECIMAL): Salary amount
- **effective_date** (DATETIME): Date from which the salary is effective

### Attendance
- **attendance_id** (INT, Primary Key): Unique identifier for each attendance record
- **employee_id** (INT, Foreign Key): References employee
- **date** (DATE): Date of attendance
- **status** (ENUM): Attendance status (Present, Absent, Leave)

### Leave Requests
- **leave_id** (INT, Primary Key): Unique identifier for each leave request
- **employee_id** (INT, Foreign Key): References employee
- **leave_type** (VARCHAR): Type of leave (Sick, Vacation, etc.)
- **start_date** (DATE): Start date of the leave
- **end_date** (DATE): End date of the leave
- **status** (ENUM): Status of the leave request (Pending, Approved, Rejected)