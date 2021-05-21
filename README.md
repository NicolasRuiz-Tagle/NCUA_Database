# NCUA5300CallReport_ETL

iformation about the data provided:

 5300 Call Report Quarterly Data Reports 
-------------------------------------------------------------
                     Readme Help File
-------------------------------------------------------------
CONTENTS
-------------------------------------------------------------
1. Overview
2. How to download and access the 5300 Call Report Quarterly Data files 
3. List of files included
4. Contents of each file
-------------------------------------------------------------

----------
Overview
----------
   The 5300 Call Report Quarterly Data Reports are part of the National Credit Union
   Administration Financial and Statistical (FAS) Call Report
   data collection system. If you have any questions please contact
   the NCUA Technical Support Center at 1-800-827-3255.

------------------------------------------------------------------------
How to download and the access the 5300 Call Report Quarterly Data files 
------------------------------------------------------------------------ 
   

1. Go to NCUA's 5300 Call Report Quarterly Data Files webpage at: 
   https://www.ncua.gov/analysis/Pages/call-report-data/quarterly-data.aspx
    
2. Click on the applicable cycle's file link, a file download window
   will open. Click the Save button and select a location to save the file

3. Locate and click on the saved 5300 Call Report Quarterly Data Zip file and Extract the files (the
   WinZip application is required to extract the files)

4. The 5300 Call Report Quarterly Data files are saved in a comma delimited text format that can be 
   easily imported into a database or spreadsheet application such as Microsoft Access or Excel

5. See the Account Descriptions (AcctDesc.txt) file for specific
   information on the accounts and table locations

-----------------------
List of Files Included
-----------------------
   Following is a list of files included in a cycle's Zip file.

   	  FOICUDES.txt
          AcctDesc.txt
          ATM Locations.txt
          Credit Union Branch Information.txt
          Foicu.txt
          FS220.txt 
          FS220A.txt
          FS220B.txt
          FS220C.txt
          FS220D.txt
          FS220G.txt
          FS220H.txt
          FS220I.txt
          FS220J.txt
          FS220K.txt
          FS220L.txt
          FS220M.txt
          FS220N.txt
          Grants.txt
          TradeNames.txt	          
          Report1.txt
          Readme.txt

--------------------------------------
Contents of each file in the Zip file
--------------------------------------
   FOICUDES.txt              Information pertaining to the fields in FOICU table, such as field name and field description, 
                                can be found in this file.
   AcctDesc.txt              This file contains account numbers, account names, account descriptions and the table name 
                                where the accounts are located.
  
   ATM Locations.txt         This file contains Credit Union ATM location information.
   Credit Union          
    Branch Information.txt   This file contains Credit Union Branch information.
   Foicu.txt                 This file contains information related to the FOICU table. 
   FS220.txt                 This file contains information related to the FS220 table.
   FS220A.txt                This file contains information related to the FS220A table.
   FS220B.txt                This file contains information related to the FS220B table.
   FS220C.txt                This file contains information related to the FS220C table.
   FS220D.txt                This file contains information related to the FS220D table.
   FS220G.txt                This file contains information related to the FS220G table.
   FS220H.txt                This file contains information related to the FS220H table.
   FS220I.txt                This file contains information related to the FS220I table.
   FS220J.txt                This file contains information related to the FS220J table.
   FS220K.txt                This file contains information related to the FS220K table.
   FS220L.txt                This file contains information related to the FS220L table.
   FS220M.txt                This file contains information related to the FS220M table.
   FS220N.txt                This file contains information related to the FS220N table.  	   	 
   Grants.txt                This file contains information on the grants the credit union has received including dates and amounts.
   Trade Names.txt           This file contains information on trade names.
   Report1.txt               This file is a report listing total number of Credit Unions in each table.
   Readme.txt                This is the File that you are reading at this moment.



------------------------------------------------------------------------------------------------------------------------------------------
Overview

This Reports contain almost 2,700 Facts (Accounts), from over 5,000 Credit Unions in over 17 tables. The information is stored as two dimension tables, with each row repreenting a specific credit union and each column an account. The number of accounts varies by table, but the one I worked on had 70 columns.
As I want to link each credit union with information about the credit union(DIM_Credit_Unions), and each account with all the information about that account (DIM_Accounts), I will feed the information of these tables to a dimensional model.

Will not go into data types or conseps that make a relational database.

This Relational Model is composed of 3 Dimensions that will be shared by all Fact tables.
DIM_Credit_Union
DIM_Date
DIM_Accounts

FACT_FS220
CU_Number       FK to DIM_Credit_Union
CYCLE_DATE      FK to DIM_Date
Account_name    FK to DIM_Accounts
value          FACT

This program will focus in create the Fact tables. As an example everithing will be done with table FS220, but the code can be modifed to be used in all tables. To do this we need to transform the data provided by NCUA into a 1 dimension Fact table.
 
 
Requirements

    Anaconda - We will be using Jupyter Notebooks and the code will be written in Python.
    SQL Database - We will be using mySQL for this particular ETL, but the code can be updated for use in Oracle, SQL Server.


Procedure:

    Navigate to the NCUA website containing the zip files. Website can be found here: https://www.ncua.gov/analysis/credit-union-corporate-call-report-data/quarterly-data

    Download the desired zip file that you will be extracting.
    Open the Python upload file to acces the code


