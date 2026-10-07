 Oracle PDB Assignment II

* Name: Gakuru Eljah
* Student ID: 28808
* Course:Database Development with PL/SQL (INSY 8311)
* DBMS:Oracle Database 21c Enterprise Edition
* Assignment: Individual Assignment II – Oracle Pluggable Databases (PDB) Management

1. Overview

This assignment demonstrates the management of Oracle Pluggable Databases (PDBs) using Oracle Database 21c. 
The tasks include creating a PDB, creating and deleting a temporary PDB, configuring Oracle Enterprise Manager (OEM), and documenting the work using GitHub.

 2. Oracle Environment

* Database: Oracle Database 21c Enterprise Edition
* Architecture: Multitenant Container Database (CDB)
* Root Container: CDB$ROOT
* Created PDB: GE_PDB_29793
* Temporary PDB: GE_TO_DELETE_PDB_28808
* OEM HTTPS Port: 5502

3. Task 1 – Create a New PDB

PDB Created

The required PDB was created using the name:
`GE_PDB_29793`
The PDB was created with the required administrative user:
`ELIJAH_PLSQLAUCA_29793`
The PDB was then opened and its state was saved.

Verification

The PDB was verified using the Oracle PDB status command/query and was shown as:

* PDB Name: PH_PDB_29793
* Open Mode: READ WRITE
* Restricted: NO
The administrative user was also verified inside the PDB.
Evidence
Screenshots are available in:
`PDB_creation.png`


4. Task 2 – Create and Delete a Temporary PDB

Temporary PDB Created
A temporary PDB was created using:
`GE_TO_DELETE_PDB_29793`

The PDB was successfully created for testing the deletion process.
Temporary PDB Deleted
The temporary PDB was deleted using:

```sql
DROP PLUGGABLE DATABASE GE_TO_DELETE_PDB_29793 INCLUDING DATAFILES;
```
The deletion was confirmed by querying the database and verifying that the temporary PDB no longer existed.

Evidence
Screenshots are available in:
`delete.png`


5. Task 3 – Oracle Enterprise Manager

Oracle Enterprise Manager Database Express was configured and accessed for the created PDB.
The PDB initially had no HTTPS port configured. A dedicated HTTPS port was configured as:
`5502`
OEM was then successfully accessed through the browser and the Oracle Enterprise Manager dashboard was displayed.

Evidence

The OEM dashboard screenshot is available in:
``


6. Challenges and Solutions

Challenge 1: ORA-65016
During PDB creation, Oracle returned:
`ORA-65016: FILE_NAME_CONVERT must be specified`

Solution

The PDB was created using the `FILE_NAME_CONVERT` clause with the correct Oracle PDB seed datafile paths.
The seed files were identified and mapped to the new PDB datafile location.

Challenge 2: Invalid Container Name in OEM
While accessing OEM, an `Invalid Container Name` message appeared.

 Solution

The HTTPS port for the PDB was checked and found to be `0`, meaning that no dedicated HTTPS port was configured.
A dedicated HTTPS port, `5502`, was configured for `GE_PDB_29793`. OEM was then successfully accessed through the PDB-specific URL.


7. Submission Details

* Repository Name: `oracle-pdb_28808_Gakuru_Elijah`
* Repository Visibility: Public
* Repository Link: https://github.com/gakuruElijah/oracle-pdb_28808_Gakuru_Elijah
* PDB Name Created: `GE_PDB_29793`
* Issues Encountered: Yes

9. Integrity Statement

I confirm that this assignment represents my own work. 
I completed the Oracle PDB management tasks, documented the procedures and results, and organized the evidence in the GitHub repository.
