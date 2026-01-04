🎓 Examination System & Modern Data Warehouse
End-to-End Data Engineering & BI Project | ITI Graduation Project

📌 Project Overview
This project demonstrates a full-cycle data solution for an educational Examination System. It begins with designing a normalized relational database (OLTP) to manage students, exams, and grading. It progresses to operational reporting using SSRS, and concludes with a modern cloud-based data warehouse implementation using Microsoft Fabric and Power BI to analyze student performance and freelance market revenue.




📂 Repository Architecture
This repository is organized into four main modules representing the data lifecycle:

Plaintext

/ITI-Examination-System
│
├── 📁 01-Database-OLTP           # Transactional System Design (SQL Server)
│   ├── ERD_Diagram.png           # Database entity relationships 
│   ├── Schema_Mapping.pdf        # Table mapping documentation [cite: 47]
│   ├── 01_Create_Tables.sql      # DDL scripts for Students, Exams, Questions, etc.
│   └── 02_Stored_Procedures.sql  # Logic for Exam Generation & Grading [cite: 126]
│
├── 📁 02-Reporting-SSRS          # Operational Reporting (Visual Studio)
│   ├── Student_Grades.rdl        # Report: Student Transcript by ID [cite: 269]
│   ├── Branch_Tracks.rdl         # Report: Tracks available per Branch [cite: 433]
│   └── Instructor_Courses.rdl    # Report: Courses taught by Instructor [cite: 499]
│
├── 📁 03-Fabric-DataWarehouse    # Cloud ETL & Warehousing (Microsoft Fabric)
│   ├── Fabric_Architecture.png   # High-level cloud architecture 
│   ├── Notebooks/                # PySpark code for data ingestion [cite: 1227]
│   │   └── data_loader.ipynb     # Python script reading CSVs (e.g., Certifications) [cite: 1297]
│   └── Dataflow_Logic.md         # Documentation of Dataflow Gen2 transformations 
│
├── 📁 04-PowerBI-Dashboards      # Analytical Dashboards
│   ├── Examination_System.pbix   # The complete Power BI file [cite: 1395]
│   └── assets/                   # Screenshots of dashboard pages
│
└── README.md                     # Project Documentation
🚀 Technical Modules
1. Database Design & Logic (OLTP)
The foundation of the system is a normalized SQL Server database used to handle day-to-day transactions.


ER Diagram: Mapped complex relationships between Students, Intakes, Branches, and Tracks.

Stored Procedures: Implemented advanced business logic using T-SQL to automate the exam lifecycle:


sp_CreateExam: Generates exams (manual or random question selection).


sp_StudentSubmitExam: Handles student answers and submissions.


sp_Grade_Unprocessed_Exams: Automates the grading process.


sp_OpenNewIntake: Streamlines the setup for new academic years.

2. Operational Reporting (SSRS)
Built utilizing Visual Studio to serve immediate administrative needs.



Student Grades Report: Retrieves detailed grades and "Pass/Fail" status based on dynamic thresholds (e.g., >90 = Excellent).


Department Analysis: Lists students by Department ID.

3. Cloud Modernization (Microsoft Fabric)
The system was migrated to the cloud to separate analytical workloads from transactional processing.


Ingestion: Data uploaded to Azure SQL Database.


ETL (Extract, Transform, Load): utilized Dataflow Gen2 in Microsoft Fabric to clean and transform data.


Data Lakehouse: Utilized PySpark (Python) notebooks to ingest CSV files (e.g., Student Certifications, Freelance Profiles) into the Lakehouse.



Modeling: Transformed the normalized schema into a Star Schema (Fact/Dimension) optimized for read-heavy analytics.


4. Analytics & Insights (Power BI)
A suite of interactive dashboards was developed to visualize KPIs.

Key Dashboards:


Intake Overview: Tracks student distribution across branches (Cairo, Alexandria, etc.).


Performance Analysis: Monitors the global Pass Rate (93.06%) and identifies failure trends by track.


Freelance Impact: A unique module tracking student career outcomes, visualizing $882k+ in total freelance revenue across platforms like Upwork and TopTal.



Instructor Performance: Analyzes instructor activity levels and student pass rates per instructor.

📊 Sample Visuals
Architecture

Figure 1: The flow from OLTP Database to Microsoft Fabric Data Warehouse.

Power BI Dashboard: Freelancing Analysis

Figure 2: Analysis of student freelance revenue by platform and year.

🛠️ Tools Used

Database: SQL Server, SSMS, Azure SQL Database.



Cloud & ETL: Microsoft Fabric, Dataflow Gen2, OneLake.



Coding: T-SQL, Python (PySpark).



Reporting: SSRS (Visual Studio), Power BI.



Design: Draw.io (ERD Modeling).

👤 Author
Mohamed Elbasuoney Power BI Development Track - ITI
