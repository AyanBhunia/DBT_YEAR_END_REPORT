# Year End Report Generation Plan

## 1. Environment Setup
- Initialize Node.js project.
- Install `xlsx` for data reading.

## 2. Data Processing (`process_data.js`)
- **Read Files:**
    - `whole_data/dbt__Employee__c.xlsx`: Employee details.
    - `whole_data/dbt__Timesheet__c.xlsx`: Weekly timesheet headers.
    - `whole_data/dbt__Timesheet_Line_Item__c.xlsx`: Daily entries (descriptions, hours, activity).
    - `whole_data/dbt__Project__c.xlsx`: Project names.
- **Relational Mapping:**
    - Link `Line Item` -> `Timesheet` -> `Employee`.
    - Link `Line Item` -> `Project`.
- **Analysis:**
    - **RPG Class:** Based on `dbt__Activity__c` distribution (e.g., Coding = Wizard, Meeting = Bard).
    - **Quest Log:** Hours per Project.
    - **Sidekicks:** Extract names from `dbt__Description__c` using NLP-like regex.
    - **Tech Tree:** Extract keywords (Python, Nosta, Salesforce, etc.).
    - **Timeline:** Heatmap of activity.

## 3. Report Generation
- Generate `report_data.json` containing stats for every employee.
- Create `index.html` (The "Fun Report" Viewer).
    - Loads `report_data.json`.
    - Features a "Select Employee" screen.
    - Displays the interactive "Wrapped" slides for the selected user.
