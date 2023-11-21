## Clinical-Outcomes-and-Patient-Satisfaction-Analysis-in-Telehealth-Services

Project Overview and Problem Definition:
A healthcare organization has implemented a telehealth program to provide remote medical consultations to its patients. However, the organization needs to assess the program's effectiveness in terms of clinical outcomes and 
patient satisfaction compared to traditional in person care. They want to determine whether telehealth services are achieving equivalent or better results and whether patients are satisfied with the remote care experience.

### Project Goals:
The primary objective is to conduct a comprehensive analysis of the telehealth program's impact on clinical outcomes and patient satisfaction. This involves comparing various healthcare metrics between telehealth and 
in-person care, identifying trends, and understanding patient preferences and perceptions.

### Data Sources:
Agency for Healthcare Research and Quality
 https://www.ahrq.gov/sdoh/index.html

### Data Cleansing
* Joining SDOH data for 2018-2020
This step involves merging multiple datasets of social determinants of health (SDOH) data for the years 2018-2020 into a single dataset. This can be done using a variety of tools and software packages, such as
GitHub and Python.
* Joining SDOH data to COAPCD
To join the SDOH data to COAPCD, we needed to identify common fields between the two datasets. For example, we  joined the two datasets on the county code field.

* Removing null values
Null values are missing values in a dataset. It is important to remove null values from your dataset before proceeding with any further analysis. This can be done using a variety of methods, such as dropping rows
with null values or filling in missing values with estimates.

* Feature selection and reduction
Correlation analysis: Correlation analysis was used to identify features that are highly correlated with each other. Highly correlated features were removed because we weren’t losing much information.
Principal component analysis (PCA): PCA is used to identify new features that represent the most important variation in the data. These new features can then be used instead of the original features.
Random forests: Random forests can be used to identify features that are important for predicting the target variable.

* Mock data creation via a multiplier
Created data for in person services. We included False data in our dataset because we did not have access to real data and obtaining real data would be costly.

### Data Preprocessing for Machine Learning
Data preprocessing is a fundamental phase in preparing for machine learning analysis. This involves transforming raw data into an understandable format for machines. In our project, one of the key preprocessing steps 
was the addition of the “service count per 1k population” column. This was achieved by calculating the ratio of ‘Telehealth services count’ to ‘population per 1k’. This new feature provides a normalized measure of service
utilization relative to population size, enhancing the model's ability to understand patterns in service usage. Another critical preprocessing step was handling missing values. We replaced null values with the average of
the respective column. This approach, known as mean imputation, helps in maintaining the overall distribution of the data while dealing with missing values. By ensuring that our data is clean, well-structured, and 
thoughtfully preprocessed, we lay a solid foundation for effective machine learning modeling.
