# MILESTONE-Sprint-3
Overview
​This project implements a robust database system for Thika Level 5 Hospital to manage patients, doctors, departments, and clinical records. It includes formal relational algebra, normalization up to 3NF, and advanced performance optimization.  
​Database Design (Milestone 1 & 3)
​Entities: Patient, Doctor, Department, Ward.  
​Key Relationships:
​Patient assigned to Ward (Many-to-One).  
​Doctor treats Patient (Many-to-Many via ClinicalRecords).  
​Doctor belongs to Department (Many-to-One).  


Formal Query Foundations (queries.md)
​Relational Algebra (Milestone 3)
​To retrieve patients with a 'completed' status stored on server 'S1':


  Advanced Data Models (data.json)
​JSON Representation (Milestone 4)
​Grouping patient clinical data by patient_id to reduce joins in application layers:  


Performance & Reliability Analysis (Milestone 5 & 6)
​Concurrency Control: The system utilizes MVCC (Multi-Version Concurrency Control) to ensure that read operations (like generating hospital reports) do not block write operations (updating patient vitals).  
​Recovery: Implementation of ARIES (Algorithm for Recovery and Isolation Exploiting Semantics) ensures that in the event of a system crash, the database can restore to its last consistent state using Write-Ahead Logging (WAL).  
​CAP Theorem Trade-off: For a hospital system, we prioritize Consistency and Partition Tolerance (CP). Accurate patient records (Consistency) are more critical during a network partition than 100% availability if the data might be stale
