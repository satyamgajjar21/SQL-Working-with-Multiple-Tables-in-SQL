# Hands-on Lab: Working with Multiple Tables in SQL

## Overview

This hands-on lab is designed to give you practical experience in writing SQL queries that work with **multiple tables** in a relational database. You will explore different techniques such as **sub-queries**, **implicit joins**, and **Cartesian joins** using the **IBM Db2** database on IBM Cloud.

## Lab Objectives

By the end of this lab, you will be able to:

- Write SQL queries that access more than one table.
- Compose queries using nested statements in the `WHERE` clause.
- Use implicit joins with multiple tables in the `FROM` clause.
- Perform cross joins and inner joins using implicit syntax.
- Use table aliases and fully qualified column names in SQL queries.

## Database & Tools

- **RDBMS**: IBM Db2 (on IBM Cloud)
- **Database Schema**: Sample **HR Database** containing 5 tables:
  - `EMPLOYEES`
  - `JOB_HISTORY`
  - `JOBS`
  - `DEPARTMENTS`
  - `LOCATIONS`
- **Tool Used**: Db2 Console - SQL Run Tool

To set up the environment, make sure to follow these prerequisite labs:
1. **Sign up for IBM Cloud, create a Db2 instance, and get started with the console**
2. **Create HR tables using SQL scripts and load sample data**

## Key Concepts Covered

### ✅ Accessing Multiple Tables with Sub-Queries

Example problems include:
- Retrieve employees for valid job IDs in the `JOBS` table.
- Filter employees based on job titles like 'Jr. Designer'.
- Fetch job info for employees earning more than $70,000.
- Retrieve job info for employees born after 1976, optionally filtering by gender.

Example SQL:
```sql
SELECT * 
FROM employees 
WHERE JOB_ID IN (
    SELECT JOB_IDENT 
    FROM jobs
);
