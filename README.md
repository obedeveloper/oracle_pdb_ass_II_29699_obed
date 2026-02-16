# ORACLE Pluggable database assignment 2

This assignment consists of three primary tasks: creating permanent and temporary pluggable databases (PDBs) using Oracle SQL*Plus, and utilizing the Oracle Enterprise Manager (OEM) for database management.

**Repository Link:** [GitHub URL](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed)\
**PDB Name Created:** ob_pdb_29699\
**Issues Encountered:** No

## Environment Used

| Component          | Details                       |
|--------------------|-------------------------------|
| **Operating System** | Windows 11                   |
| **Database**         | Oracle 21c                   |
| **Text Editor**      | Visual Studio Code (VS Code) |
| **Terminal**         | Git Bash                     |
| **Browser**          | Firefox Developer Edition    |

## Task 1: Create a New Pluggable Database

In this task, a permanent pluggable database named **ob_pdb_29699** was created. The following SQL commands were executed:

```sql
-- Create pluggable database
CREATE PLUGGABLE DATABASE ob_pdb_29699
ADMIN USER obed_plsqlauca_29699 IDENTIFIED BY admin
FILE_NAME_CONVERT = (
    'C:\USERS\SCHOOL\ORACLE21C\ORADATA\ORCL\pdbseed',
    'C:\USERS\SCHOOL\ORACLE21C\ORADATA\ORCL\ob_pdb_29699'
    );

-- Open pluggable database
ALTER PLUGGABLE DATABASE ob_pdb_29699 OPEN;

-- Save the pdb state
ALTER PLUGGABLE DATABASE ob_pdb_29699 SAVE STATE;
```

![Task 1](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.45.jpeg)

Verification of the PDB creation and its status was performed using the following SQL query:

```sql
-- Check pluggable database creation and status
SELECT pdb_name, status
FROM dba_pdbs;
```

![Task 1 Verification](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46.jpeg)

## Task 2: Create and Delete a PDB

In this task, a temporary pluggable database named **ob_to_delete_pdb_29699** was created. The database's creation was followed by verification and subsequent deletion. Here are the SQL commands executed for this task:

```sql
-- Create temporary pluggable database
CREATE PLUGGABLE DATABASE ob_to_delete_pdb_29699
ADMIN USER obed_to_deleteplsqlauca_29699 IDENTIFIED BY admin
FILE_NAME_CONVERT = (
    'C:\USERS\SCHOOL\ORACLE21C\ORADATA\ORCL\pdbseed',
    'C:\USERS\SCHOOL\ORACLE21C\ORADATA\ORCL\ob_to_delete_pdb_29699'
    );

-- Verify that it exists
SELECT pdb_name
FROM dba_pdbs;

-- Delete it completely
DROP PLUGGABLE DATABASE ob_to_delete_pdb_29699 INCLUDING DATAFILES;

-- Confirm that it no longer exists
SELECT pdb_name
FROM dba_pdbs
WHERE pdb_name = 'OB_TO_DELETE_PDB_29699';
```

![Task 2](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(1).jpeg)

## Task 3: Oracle Enterprise Manager (OEM)

In this task, Oracle Enterprise Manager was used to gain insights and manage the pluggable databases visually. The screenshots provide a detailed overview of the database activities and performance metrics that can be monitored using OEM.

![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(2).jpeg)
![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(3).jpeg)
![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(4).jpeg)

## Reference

- [Pluggable Databases Tutorial](https://www.youtube.com/watch?v=dPHerZHvUyk)
- [Oracle Enterprise Manager Tutorial](https://www.youtube.com/watch?v=FgXivcsuxUA)

## Integrity

All sources were properly cited.\
Implementations and analysis represent original work.\
No AI- generated content was copied without attribution or adaptation.
