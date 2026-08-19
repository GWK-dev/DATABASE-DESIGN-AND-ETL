# DATABASE DESIGN & ER DIAGRAMS

💡 **Acknowledgement**: The foundational business requirements and structural case studies utilized in this project are credited to the [Aly-Habib/Database-Design-and-SQL](https://github.com/Aly-Habib/Database-Design-and-SQL) repository.

---

## 🎯 Project Overview

This repository contains my independent solutions for real-world relational database design and engineering challenges. For each case study, I execute a rigorous engineering process to translate narrative corporate workflows into production-ready schemas and automated ETL pipelines:

* **Requirements Analysis**: Analyzed raw operational requirements (`Company requirements document.docx`) to extract core business logic, entity attributes, and relational cardinalities.
* **Conceptual Modeling**: Mapped abstract tables, primary keys, and relationships visually using a standard Chen notation ER diagram (`Company Conceptual Chen Diagram`).
* **Physical Modeling**: Reverse-engineered the schema inside MySQL Workbench to generate an industry-standard Crow's Foot notation physical ER diagram, validating keys and data types (`Company Physical ER Diagram`).
* **SQL Schema**: Wrote and executed clean MySQL DDL scripts (`Company DB.sql`) to build the final database architecture with proper foreign key cascading constraints.
* **ETL Pipeline**: Built a dependency-aware Python script in Jupyter Notebook (`company_db.ipynb`) using `SQLAlchemy` and `pandas` to resolve circular foreign key constraints during automated data ingestion from `Book1.xlsx`.
* **Dynamic Rate Engineering**: Executed multi-step SQL queries to dynamically compute tiered hourly pay rates based on corporate hierarchy (Base Staff, Supervisors, Executive Leadership).
* **Automated Financial Reporting**: Leveraged SQL CTEs and `openpyxl` to aggregate departmental spend, project labor costs, and dependent family allowance bonuses, writing formatted analytical summaries back to dedicated sheets in `Book1.xlsx`.

---

## 📂 Case Study Assets (`company_db`)

* 📄 **Requirements**: `Company requirements document.docx`
* 📊 **Conceptual Blueprint (Chen Notation)**: `Company Conceptual Chen Diagram`
* 📉 **Physical Blueprint (Crow's Foot)**: `Company Physical ER Diagram`
* 💾 **SQL Script**: `Company DB.sql`
* 📓 **ETL & Data Analysis Notebook**: `company_db.ipynb`
* 📊 **Source & Export Workbook**: `Book1.xlsx`

*Click on any asset in the repository files above to view the project documentation, visual layouts, data workbook, and executable scripts directly.*

---

## 🛠️ Technical Highlights & Engineering Workflow

* **Dependency-Aware Ingestion**: Solved foreign key initialization errors in Python by ingesting unreferenced supervisor and department keys as `NULL` before programmatically executing backfill updates.
* **Tiered Salary Logic**: Computed tiered rates ($35.00–$45.00/hr for base staff, $55.00/hr for supervisors, $75.00/hr for executive leadership) to automate project spend calculations.
* **Multi-Sheet Reporting**: Extracted raw operational sheets from `Book1.xlsx` and appended engineered output sheets (`Salaries`, `Project_Employees`, `Project_Hours`, `Project_Spend`) without disrupting base raw tables.
