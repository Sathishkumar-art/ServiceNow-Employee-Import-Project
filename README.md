# ServiceNow Employee Import Project

A ServiceNow employee data management project demonstrating **Import Sets, Transform Maps, Coalesce, Validation, Reports, and Dashboards**.

## Project Objective

Import employee information from a spreadsheet into a custom ServiceNow target table through an Import Set and Transform Map. Coalesce is used to prevent duplicate employee records when the same employee is imported again.

## Architecture

```text
Sample Spreadsheet
       |
       v
Import Set / Staging Table
       |
       v
Transform Map
       |
       +---- Field Mapping
       |
       +---- Coalesce (Employee ID)
       |
       v
Employee Test Table
       |
       +---- Reports
       |
       +---- Employee Analytics Dashboard
```

## ServiceNow Configuration

### Target Table
- Label: `Employee Test`
- Name: `u_employee_test`

Fields:
- Employee ID — String
- Employee Name — String
- Email — String
- Department — String
- Location — String

### Import Set Table
- Label: `Employee Import`
- Name: `u_employee_import`

### Transform Map
- Name: `Sample Spreadsheet Import`
- Source: `Employee Import`
- Target: `Employee Test`
- Auto Map Matching Fields: Enabled
- Coalesce: `Employee ID`

## Import Workflow

1. Prepare the spreadsheet.
2. Navigate to **Load Data**.
3. Upload `data/Sample Spreadsheet.xlsx`.
4. Use/create the `Employee Import` Import Set Table.
5. Create/open `Sample Spreadsheet Import`.
6. Auto-map matching fields.
7. Set `Employee ID` as Coalesce.
8. Run the Transform.
9. Check Transform History.
10. Verify records in `Employee Test`.

## Coalesce Test

The project demonstrates two important cases:

- Existing Employee ID + changed name/email → **Update**
- New Employee ID → **Insert**
- Re-uploading the exact same sheet → existing records are not duplicated.

## Reports

The project documentation includes the report setup for:
- Employees by Department
- Employees by Location
- Employee List Report

The department report uses a **Pie chart**, groups by **Department**, and uses **Count** aggregation.

## Dashboard

Dashboard name:

**Employee Analytics Dashboards**

The dashboard can contain:
- Employees by Department
- Employees by Location
- Employee List Report

## Repository Structure

```text
ServiceNow-Employee-Import-Project/
├── README.md
├── .gitignore
├── LICENSE
├── data/
│   ├── Sample Spreadsheet.xlsx
│   └── Sample Employee Data.csv
├── docs/
│   ├── ServiceNow Employee Import Project Report.docx
│   └── Project Notes.md
├── reports/
│   ├── Employees by Department.md
│   ├── Employees by Location.md
│   └── Employee List Report.md
├── servicenow/
│   ├── Target Table Configuration.md
│   ├── Import Set Configuration.md
│   ├── Transform Map Configuration.md
│   ├── Coalesce Test.md
│   └── Dashboard Configuration.md
└── screenshots/
    └── README.md
```

## Screenshots

Add your ServiceNow screenshots under `screenshots/` after completing each step. Suggested names are documented in `screenshots/README.md`.

## Result

The project provides a repeatable employee data import workflow with duplicate prevention through Coalesce and visual reporting through ServiceNow Reports and Dashboards.
