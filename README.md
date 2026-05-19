# 🏥 Hospital Management System — Database

A fully normalized relational database system for hospital management,
built in MySQL. Designed, normalized, and validated as part of a 
Database Systems course at GCU Lahore.

**Developed by:** Tehreem Ahmad & Wafa Rahman  
**Course:** Database Systems | GCU Lahore  
**Instructor:** Sir M. Hafeez  
**Grade:** Passed with live SQL viva assessment ✦

---

## 📋 Overview

This database manages the complete operational, clinical, and financial
workflows of a hospital — from patient registration to billing and payment.

It covers **18 fully normalized tables** across three domains:

| Domain | Coverage |
|---|---|
| Clinical | Patients, Doctors, Encounters, Prescriptions, Lab Tests |
| Administrative | Departments, Wards, Rooms, Admissions, Appointments |
| Financial | Billing, Payments, Insurance |

---

## 🗃️ Database Schema

### Tables (18)
`Patient` · `Patient_History` · `Insurance` · `Department` · `Doctor`  
`Ward` · `Room` · `Encounter` · `Appointment` · `Admission`  
`Emergency` · `Prescription` · `Medicine` · `Prescription_Medicine`  
`Lab_Test` · `Test_Report` · `Billing` · `Payment`

### Key Design Decisions
- **Normalization:** Schema normalized from 1NF → 3NF independently
- **Referential Integrity:** All foreign keys enforced with ON DELETE / ON UPDATE actions
- **Junction Table:** `Prescription_Medicine` handles many-to-many between prescriptions and medicines
- **Encounter-centric design:** OPD, IPD, and Emergency all flow through a central `Encounter` entity
- **Optional linkage:** Insurance is nullable in Billing — supports both insured and uninsured patients

---

## 🔗 Entity Relationship
Patient ──< Encounter >── Doctor
│
┌─────────┼──────────┐
Appointment  Admission  Emergency
│
┌─────────┼──────────┐
Prescription  Test_Report  Billing
│                        │
Prescription_Medicine      Payment
Full ERD (unresolved + normalized) available in `Documentation.pdf`

---

## 🚀 How to Run

1. Open **MySQL Workbench** or any MySQL client
2. Run the SQL file:

```sql
SOURCE hospital_management.sql;
```

Or import via MySQL Workbench:
- Server → Data Import → Import from Self-Contained File
- Select `hospital_management.sql`
- Click Start Import

3. The script will:
   - Create the `hosp_dbms` database
   - Create all 18 tables with constraints
   - Insert sample data (30 patients, 30 encounters, full billing records)

---

## 📊 Sample Data Includes

- **30 patients** with demographics, history, and insurance records
- **6 doctors** across 6 departments
- **30 encounters** (OPD, IPD, Emergency) spanning 2024–2025
- **25+ prescriptions** with medicine linkage
- **30 billing records** with payment tracking
- **5 lab tests** with 25+ test reports

---

## 📄 Documentation

See `Documentation.pdf` for:
- Full entity descriptions
- ERD cardinality and modality table
- Normalization summary (unresolved → normalized ERD)
- Database validation rules for all 18 entities
- System architecture overview

---

## 🛠️ Tech Stack

![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Database-blue?style=flat)

---

## 👩‍💻 Author

**Tehreem Ahmad**  
BSc Computer Science — GCU Lahore  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/tehreem-ahmadch/)
