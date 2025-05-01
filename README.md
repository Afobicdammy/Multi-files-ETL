# Welcome to my first ETL project!

My First ETL project - At least thats what I thought! Realized that I have been doing ETL/ELT everyday in my current role as a data analyst in the healthcare domain:

    - **Extract**: Making conncetion to the Data repository
        - Using SAS, we connect to multiple tables in the CMS IDR. 
        - Using Proq SQL, we combine multiple tables from hundreds of views 
        (Sometimes the tables can be up to 25) into a single Master table.

    - **Transform**: Here we add various formats to the master table 
        - changing the column name from SAS formats to readable column names 
        e.g Recip_1st_Name to "Recipients First Name"
        - Create features in the tables using the CASE statments, an example will 
        be something like WHEN Charg_amt > 0 then "Paid" else "Denied". Now we have 
        a new column that shows if a claim was Paid or denied.
        - This master table usually contain a large volume so claims data - sometimes 
        about 4 million rows and over 100 columns.
        - We create meaningful summaries from this tables and basically break the table 
        down into smaller conscience tables such as summaries by year, procedure codes, providers, etc..

    - **Load**: At this stage the data is ready for analysis.
        - Using SAS, we load this data in desired BI tools...Excel, Power BI ...

Even though that process seems like a lot, and I have several analysts denpending on it upstream, I myself depend on the ETL process of data engineers downstream to get data from multiple sources (EHRs, Databases, lakehouse) into the IDR.

Hence, my ETL projects contains scenarios encountered by the real life data engineers.

# The actual Project:

In this project, I used python to Extract, Transform and load data from multiple files with different file extensions like .json, .csv, .xml.

#### Importing the neccessary libraries:
Here the only 2 libraries I used for the first time are:
    1. **glob**: Helps find all the files with specific extensions

    2. **ElementTree**: We will need this to parse information from the xml file. 

### Extract: 
    1. **json and csv**: Pandas!

    2. **xml** Parse using ElementTree then Pandas!

    3. Combined the 3 different types of data into a Master table.

### Tansform:
Any operation here should not be a problem as a data analyst.

### Load:
Dumped the data from the Master table into a CSV.

## Whats next?
    - Most of the operations here were done using functions. I would like to see how to redo the whole project using OOP.
    - Since ETL is just a part of a Pipeline, looking forward to building an entire pipeline.
