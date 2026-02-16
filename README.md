# ORACLE Pluggable database assignment 2

This assignment is made of 3 tasks:
- Creating permanent pluggable database using oracle sql-plus
- Creating temporary pluggable database and deleting it after creation
- Using Oracle enterprise manager

## Environment used

**Operating System**: Windows 11\
**Database**: Oracle 21c\
**Text Editor**: VS Code\
**Terminal**: Git Bash

## Task 1: Create a New Pluggable Database

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

```sql
-- Check pluggable database creation and status
SELECT pdb_name, status
FROM dba_pdbs;
```

![Task 1 Verification](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46.jpeg)

## Task 2: Create and Delete a PDB

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

![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(2).jpeg)
![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(3).jpeg)
![](https://github.com/obedeveloper/oracle_pdb_ass_II_29699_obed/blob/7ec6f7de41f16ae7a583dd87a4dc3d7184fca150/screenshots/Image%202026-02-16%20at%2010.05.46(4).jpeg)
