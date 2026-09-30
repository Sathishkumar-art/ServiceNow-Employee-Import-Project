# ServiceNow Employee Import & Analytics Project

## Project Name
Employee Data Management using ServiceNow Import Sets, Transform Maps, Coalesce, Reports and Dashboard

## Main Tables
- Target table: `u_employee_test` (Employee Test)
- Import Set table: `u_employee_import` (Employee Import)

## Target Fields
- Employee ID — String
- Employee Name — String
- Email — String
- Department — String
- Location — String

## Transform Map
- Name: Sample Spreadsheet Import
- Source: Employee Import
- Target: Employee Test
- Use Auto Map Matching Fields
- Configure Employee ID as Coalesce for duplicate prevention.

## Sample Excel
Use `Sample Spreadsheet.xlsx` as the initial import file.

## Reports
1. Employees by Department — Pie chart, Group by Department, Count aggregation.
2. Employees by Location — report grouped by Location.
3. Employee List Report — list/table report of employee records.

## Dashboard
Dashboard name:
`Employee Analytics Dashboards`

Add the three reports to this dashboard.

## Validation
After importing:
- Open Employee Test.
- Verify employee records.
- Run Transform.
- Check Transform History for inserted/updated/ignored records.
- Re-upload the same sheet to confirm Coalesce prevents duplicate records.
