## About the project

The idea here was to look at Federal Procurement Data, that I've worked with in the past and see if I can derive anything interesting utilizing what I've learnt during our class.

#### About the source of data (from wikipedia)

The Federal Procurement Data Center (FPDC), part of the U.S. General Services Administration, manages the Federal Procurement Data System (FPDS), which is operated and maintained by IBM.[2] The FPDS-NG is the current central repository of information on Federal contracting. The system contains detailed information on contract actions over $3,000 (FY2004 and later data). The Executive departments and agencies award over $200 billion annually for goods and services. The system can identify who bought what, from whom, for how much, when and where.

#### Steps needed to aquire the data
Data comes in in a form of xml files. The size varies from a few KBs to files over 30GBs.
Large files needed to be split with a bash script into smaller chunks so they can transformed with XSLT into tabular format.
Original xml files contained a header with the count of 'actions' per file which then was used to validate and compare against processed records.
Running data type/size checks (isDate, isBoolean or len(column)) was used to validate whether the XSLT transformation was correct and didnt mangle any of the original data.

Once processed and validated, I picked the columns that I thought were somewhat meaningful and loaded them into .csv file.

I ran this entire process for all Fed contract data that took over 12 hours of processing yielding over 60 millions rows of data across over 200 columns.

### Project details:

Please refer to [FedData.ipynb](./FedData.ipynb) notebook.

I've added another [readme file](ThingsLearnt.md) to document things I've learnt during this project.
