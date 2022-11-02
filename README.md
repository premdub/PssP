# PssP
HHA504-Assignment-7

Homework PssP:Admin (Patient Self Service Portal - Admin View) 

1. Create a new github repo called PssP in your github  

2. Copy the code (files, folders, subfolders) from Part6_CRUD in our HHA-504-2022 repo (https://github.com/hantswilliams/HHA-504-2022/tree/main/Part6_CRUD) 

3. Re-create your own cloud-managed mysql database (either in GCP or Azure) or re-use one if you already have one running, and execute the scripts located in Part5_DBs to create some testing data (https://github.com/hantswilliams/HHA-504-2022/tree/main/Part5_DBs)   

4. Then create your .ENV file with the proper credentials/keys so the flask PssP app nows how to connect to the database 

5. Then update the PssP code in the following ways: 
Include in at least 3 additional patient demographic fields that are displayed in the /patients and patient details views (note, you may need to update your SQL schema depending on what you decide to use or not use)  
Update the EDIT functionality to include the ability to also edit the 3 new fields in the edit modal window dialogue 
Update the NEW PATIENT functionality to include the ability to also include the 3 new fields in the new patient modal window dialogue 
OPTIONAL: attempt to replicate the 'EDIT' functionality within the medications detail view; I have provided the code currently within conditions, try and create a similar process 
6. Include a new folder in the repo called IMAGES - this folder should contain the following screen shots: 
Screen shot of the app running on your browser on the /patients list page, showing dummy patients with the newly added demographics
Screen shot of the app running on your browser on one of the patient details pages - showing some dummy patient details with the newly added demographics  
Screen shot of the updated modal window for EDITING a patient from the /patients list view 
Screen shot of the updated modal window for the NEW PATIENT action from the /patients list view
----------------------------------------------------------
# Run instructions 

## IMPORTANT // GOTCHAS
- BE SURE TO INSTALL https://pypi.org/project/mysqlclient/ 
- you will need to install this before it can work 
- IF that doesnt work (e.g., you are on a m1 processor): 
    - do pip install `pip install pymysql` 
    - and update mysql+mysqldb TO mysql+pymysql
- .ENV file 
    - be sure to put it in the rool directory, at the same the Part1_ Part6_ folders 

## Details

- Since this version has the __main__, you can run this flask app using the pythong command: 
    - `sudo python app.py` 
- Or you can use python3 if that is what is found on your machine: 
    - `sudo python3 app.py` 
- The reason why we need `sudo` permissions here, is that if we are deploying our app on a remote server, to port :80, which is a special port (e.g., website traffic), we need to have elevated permissions

## ENV file structure: 
```
MYSQL_USERNAME = "SDF"
MYSQL_PASSWORD = "fSDFDF!"
MYSQL_HOST = "104.343.111.186"
```


- Other notes to organize: 
    - using the flask version of sqlalchemy https://flask-sqlalchemy.palletsprojects.com/en/3.0.x/quickstart/ 
    - declaring models https://flask-sqlalchemy.palletsprojects.com/en/3.0.x/models/
    - connecting to a MySQL database https://docs.sqlalchemy.org/en/14/dialects/mysql.html#module-sqlalchemy.dialects.mysql.mysqldb 

## Dependencies: 
- pip install flask flask-sqlalchemy PyMySQL 

## Future: 
- Signin: 
    - Azure AD ? 
    - GCP Firebase ? 
    - Build it ourselves? 

## Helpful tutorials: 
- Example 1: https://morioh.com/p/f38e3272d126 