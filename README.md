# Oracle SQL Assignment 3 Repository

This repository contains the tasks for Assignment 3.

## Task 1: Creating Pluggable Database

I created a pluggable database named `plsql_class2024db` as requested. I used SQL Developer and then verified its existence via the command prompt, as shown in the screenshots below.

![creating](https://github.com/user-attachments/assets/f9996e37-3607-4754-a4b9-15ad029d665f)



The message displayed confirms that the database was created successfully.

![confirmation](https://github.com/user-attachments/assets/c9853523-23c6-4a1e-81a8-32a2197b1213)


Next, I set the database to read and write mode to allow modifications.
```sql
show pdbs;

ALter Pluggable database Plsql_Class2024db;
```

![pdb1](https://github.com/user-attachments/assets/e86ad2dc-0ad3-462d-98f0-4936113decd2)
Read/Write Mode

I then created a user named `EM_plsqlauca` (derived from the first two letters of my name, Emile).
```sql
Alter Session set container = Plsql_Class2024db;

Create user EM_plssqlauca identified by 12345;
```
<img width="959" alt="User Creation" src="https://github.com/user-attachments/assets/6f557e0e-d18c-4667-92e1-1a8720ecac6c">

## Task 2: Create and Delete Pluggable Database

I created a pluggable database named `EM_to_delete_pdb` in SQL Developer, as shown below.
```sql
Alter pluggable database EM_to_delete_pdb UNPLUG into 'C:\app\curry_emile\product\21c\admin\xe\dpdump\EM_to_delete_pdb.xml';

DROP PLUGGABLE DATABASE EM_to_delete_pdb including datafiles;
```

![creating](https://github.com/user-attachments/assets/976ca91d-dd24-40db-be3d-489e6dc0e093)

![em_to_delete_pdb](https://github.com/user-attachments/assets/27e289b1-812e-4afe-9a88-d48bae950306)
![confirm](https://github.com/user-attachments/assets/42eb097c-d6f3-4d40-95d5-629fdfa14394)


I then used SQL*Plus to unplug and drop the pluggable database, as shown below.

![deleting it](https://github.com/user-attachments/assets/52b6794d-3921-4d28-bdd0-7c1259445e01)


## Task 3 Configuring OEM

I started checking the ports of http and https, found that only http got none. then after i assigned port: 8080 to it,then shutdown and startup whole database as shwon below

```sql
SELECT DBMS_XDB_CONFIG.GETHTTPPORT() AS HTTP_PORT,
     DBMS_XDB_CONFIG.GETHTTPS() AS HTTPS_PORT
     FROM DUAL;

  BEGIN 
   DBMS_XDB_CONFIG.SETHTTPPORT(8080);
   END;
    /
```
![configuring](https://github.com/user-attachments/assets/71fad5a9-fc3c-4b00-8bc7-273839fc6019)
```sql
SHUTDOWN IMMEDIATE;

STARTUP;
```
![startup](https://github.com/user-attachments/assets/175d0d93-2f03-48d3-ac83-a85c75c67b58)

## Problem statement
i got huge distracted because of erors in querring because of my limited knowldge but hope as i practice and time goes i shall understand it better.
i want to cite the note you gave us 'lecture_05' because all the commands i used i gotted from there.



