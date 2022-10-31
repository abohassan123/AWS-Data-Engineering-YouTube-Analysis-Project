# AWS-Data-Engineering-YouTube-Analysis-Project

In this project trying to do this architecture:

![image](https://user-images.githubusercontent.com/55424201/199018368-ef8b0628-331b-404e-9925-36ef8e61adae.png)

so :

- uploaded the youtube data to an s3 bucket with CLI to fast control of partitioning and making folders with commands 
- data stored with its kind JSON files and CSV files
- made data catalog with AWS Glue data catalog and crawler for the CSV files and JSON files and the output will be used in Athena and  the tables in a database 

![image](https://user-images.githubusercontent.com/55424201/199006461-cbd3a531-c21b-44d3-8045-f9e11bb8a01c.png)


- after checking the out we found problems in the JSON files structures so it is needed to process and it will be as follows :

![image](https://user-images.githubusercontent.com/55424201/199007105-6e7ebdb4-d6b3-46b1-86c7-d31fd424098d.png)


- created AWS lambda and wrote a python function to edit and convert the JSON files to parquet files and made the trigger to the lambda when data is uploaded to the 
  s3 bucket and make the output be in the second s3 bucket and the second database in Athena after that we can check the Schema  and data types of the table 
  
- after cleaning the JSON files and converting them to parquet, also converted the CSV files to parquet  and do some of the processes with AWS glue ETL job and made 
  the cleaned output in the second s3 bucket
  
- after that made a second AWS Glue data catalog crawler for the cleaned version and made the output to the second database 

- so for now we have a cleaned table from the JSON files which was converted and processed to parquet  by lambda and a cleaned table from the CSV files which
  are converted and processed to parquet by ETL glue and they are all stored in the same database 
  
- the next step is to build a new ETL to join our tables and store the output in the final s3 bucket for doing analytics  with AWS Glue studio 

- our data now is ready to use in different things like dashboard reporting or machine learning models 

- as an example, we use the final data to make a simple dashboard with AWS quicksight 

 - data link : https://www.kaggle.com/datasets/datasnaek/youtube-new?select=KR_category_id.json
 
