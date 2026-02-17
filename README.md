# Oracle Pluggable Database (PDB) Management - Assignment II

## Student Information
- **Name:** Ngoga Nelly Urujeni
- **Student ID:** 29139
- **Course:** Database Development with PL/SQL (INSY 8311)
- **Instructor:** Eric Maniraguha

## Overview

This assignment demonstrates practical understanding of Oracle Multitenant Architecture, including the creation and management of Pluggable Databases (PDBs), user administration within a PDB, and usage of Oracle Enterprise Manager (OEM) Express.

## Oracle Environment

- **Oracle Version:** Oracle Database 21c Express Edition (Release 21.3.0.0.0)
- **Platform:** Microsoft Windows x86 64-bit
- **Tool Used:** SQL*Plus, Oracle Enterprise Manager Database Express

## Task 1: Create a New Pluggable Database

A new Pluggable Database was created using the following naming conventions:

- **PDB Name:** `ne_pdb_29139`
- **Username inside PDB:** `nelly_plsqlauca_29139`
- **Password:** Configured during setup

### Steps Performed
1. Connected to the Container Database (CDB) as SYSDBA
2. Created the pluggable database `ne_pdb_29139`
3. Opened the PDB and saved its state
4. Switched session to the new PDB
5. Created user `nelly_plsqlauca_29139` with appropriate privileges (CREATE SESSION, CREATE TABLE, UNLIMITED TABLESPACE)
6. Verified the user was created successfully

**Evidence:** See `screenshots/` folder  PDB creation command, PDB open state, and username clearly visible.

## Task 2: Create and Delete a PDB

A temporary PDB was created and then completely removed to demonstrate the full lifecycle of a Pluggable Database.

- **Temporary PDB Name:** `ne_to_delete_pdb_29139`

### Steps Performed
1. Switched back to CDB$ROOT
2. Created the temporary pluggable database `ne_to_delete_pdb_29139`
3. Opened the PDB and verified its existence using `SELECT pdb_name, status FROM cdb_pdbs`
4. Closed the PDB with `CLOSE IMMEDIATE`
5. Dropped the PDB with `INCLUDING DATAFILES`
6. Confirmed the PDB no longer exists by querying `cdb_pdbs`

**Evidence:** See `screenshots/` folder PDB creation, verification, deletion, and confirmation that it no longer exists.

## Task 3: Oracle Enterprise Manager (OEM)

Oracle Enterprise Manager Database Express was accessed and configured to reflect the Oracle environment.

### Steps Performed
1. Accessed EM Express via `https://localhost:5500/em`
2. Logged into the CDB dashboard confirmed PDB environment and Data Storage showing `NE_PDB_29139`
3. Logged into the PDB `ne_pdb_29139` directly using user `nelly_plsqlauca_29139`
4. Dashboard displays: Oracle environment, PDB name (`XE / NE_PDB_29139`), and username (`nelly_plsqlauca_29139`)

**Evidence:** See `screenshots/` folder OEM dashboard screenshots showing Oracle environment, PDB, and username.

## Challenges Faced

- **Oracle Managed Files:** Initially used `FILE_NAME_CONVERT` for PDB creation but later switched to Oracle Managed Files (`db_create_file_dest`) for a cleaner setup.
- **EM Express Access:** Required granting `EM_EXPRESS_ALL` role to the PDB user to allow login with the assignment-specific username.

Both challenges were resolved successfully.

## Submission Details

- **Repository Link:** [GitHub URL]
- **PDB Name Created:** `ne_pdb_29139`
- **Issues Encountered:** Yes (resolved  see Challenges above)

## Integrity Statement

I confirm that this assignment is entirely my own work. All commands were executed individually, all screenshots reflect my own Oracle environment, and no content was copied from classmates or shared repositories.
