# Applied Data Analytics

## Wedge Project

The Wedge Project is an exercise in data engineering and analytics, centered around transaction data from the Wedge Co-op, a large cooperative grocery store. The project involves uploading and processing large datasets in Google BigQuery, sampling owner transaction records, and building summary tables that provide insights into sales trends, customer behaviors, and product popularity. This project applies core principles of the Extract-Transform-Load (ETL) process to prepare the data for analysis.

My efforts complete The Wedge Project at a B level, using the pre-cleaned Transaction dataset. 

### Task 1

* Files for this task:
   - **`Task-1-data-GBQ-upload.ipynb`**  
   This file contains the Python code that loads the Wedge transaction data into the Google BigQuery dataset, unzipping the folder and ensuring that all files are uploaded programmatically. It checks for existing tables in the dataset to avoid duplicate uploads and ensures proper schema consistency across the data. Note that I used a larger separate disk location on my computer for unzipping the zipped Wedge files. 
   
### Task 2

* Files for this task:
   - **`Task-2-Sample-of-Owners.ipynb`**  
   This file connects to the BigQuery dataset and builds a list of owners (excluding non-owners with `card_no = 3`). It then takes a random sample of the owners and extracts all their associated records from the Wedge dataset. The records are then written to a local CSV file for further analysis.

   The associated output file **`sampled_owner_transactions.txt`** was stored in the git-ignored data folder. 

### Task 3

* Files for this task:
   - **`Task-3-Building-Summary-Tables.ipynb`**  
   This file processes the owner transaction data to build three summary tables: "Sales by Date by Hour," "Sales by Owner by Year by Month," and "Sales by Product Description by Year by Month." These tables are stored in an SQLite database and are designed to potentially answer key business questions, such as identifying trends in sales, popular products, and owner shopping behaviors.

   The associated output file **`wedge_summary.db`** was stored in the git-ignored data folder. 


## Query Comparison Results

Fill in the following table with the results from the 
queries contained in `gbq_assessment_query.sql`. You only
need to fill in relative difference on the rows where it applies. 
When calculating relative difference, use the formula 
` (your_results - john_results)/john_results)`. 



|  Query  |  Your Results  |  John's Results | Difference | Rel. Diff | 
|---|---|---|---|---|
| Total Rows  |  98,034,139 | 85,760,139  |  12,274,000 |  0.140 |
| January 2012 Rows  |  1,070,907 | 1,070,907  | 0  | 0.000  |
| October 2012 Rows  |  1,042,287 | 1,042,287  |  0 | 0.000  |
| Month with Fewest  |  12 |  2 | No  | NA  |
| Num Rows in Month with Fewest  | 5,800,621  | 6,556,770  |  183,963 | 0.028  |
| Month with Most  | 3  |  5 | No  | NA  |
| Num Rows in Month with Most  | 5,936,267  | 7,758,372  |  -1,822,105 |  0.229 |
| Null_TS  | 8,765,980  | 7,123,792  | 1,642,188  |  0.230 |
| Null_DT  | 0  |  0 | 0  |  0 |
| Null_Local  |  234,843 |  234,843 | 0  | 0.000  |
| Null_CN  |  0 |  0 | 0  | 0  |
| Num 5 on High Volume Cards  | 14987  |  14987 | Yes  | NA  |
| Num Rows for Number 5 |  555,658 | 460,630  | 81,555  |  0.206 |
| Num Rows for 18736  |  12,153 | 12,153  | 0  |  0.000 |
| Product with Most Rows  | banana organic  |  banana organic | Yes  | NA  |
| Num Rows for that Product  | 1,086,927  |  908,639 |  178,288 | 0.196  |
| Product with Fourth-Most Rows  | avocado hass organic  | avocado hass organic  | Yes  | NA  |
| Num Rows for that Product  |  546,174 |  456,771 |  89.403 | 0.196  |
| Num Single Record Products  |  2,355 |  2,769 | -414  | -0.149  |
| Year with Highest Portion of Owner Rows  | 2014  |  2014 | Yes  | NA |
| Fraction of Rows from Owners in that Year  | 0.7591  |  0.7591 | 0  | 0.000  |
| Year with Lowest Portion of Owner Rows  | 2011  |  2011 | Yes  | NA |
| Fraction of Rows from Owners in that Year  | 0.7372  | 0.7372  | 0  |  0.000 |

## Reflections

The Wedge project tested all of my data engineering skills. 

Even in receiving cleaned Transaction files, the majority of my time spent troubleshooting ineffective code was on Task 1, as files would often fail to upload to Google BigQuery. I had to learn a lot about setting up error logging, tracing errors back to the specific code chunks, and doing more patient, targeted troubleshooting based on those error codes. Working out code to step sequentially through each file for upload, and then having a companion script to return a list of files that were not uploaded to GBQ, was a breakthrough on this front. 

In Task 2, effort was expended when data type inconsistencies prevented the querying and table creating of the owner-associated records. The schema files proved useful in helping to determine which columns of data had inconsistent data types. My first troubleshooting effort was aimed at casting each column to an appropriate and consistent datatype, but I was unable to overcome the numerous-file aspect of the Transactions database when attempting to cast these columns. The final solution came by ensuring the columns with inconsistent data types wer not likely needed for any future analysis, and as such were omitted. 

Task 3 proved much more straightforward in completing than either Task 1 or 2. My only hiccup was in recalling that I needed to upload the Department Lookup file to GBQ, rather than only have it stored/saved locally, else the query join would fail.

In all, I found the Wedge Project to be an informative and worthwhile project, with an appropriate level of openendedness and creativity available to us as students. 
