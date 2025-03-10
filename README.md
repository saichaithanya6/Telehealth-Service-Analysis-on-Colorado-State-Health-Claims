## Telehealth Service Analysis on Colorado State Health Claims


Project Overview and Problem Definition:
A healthcare organization has implemented a telehealth program to provide remote medical consultations to its patients. However, the organization needs to assess the program's effectiveness in terms of clinical outcomes and patient satisfaction compared to traditional in person care. They want to determine whether telehealth services are achieving equivalent or better results and whether patients are satisfied with the remote care experience.

### Project Goals:
The primary objective is to conduct a comprehensive analysis of the telehealth program's impact on clinical outcomes and patient satisfaction. This involves comparing various healthcare metrics between telehealth and 
in-person care, identifying trends, and understanding patient preferences and perceptions.

### Data Sources:
Agency for Healthcare Research and Quality
 https://www.ahrq.gov/sdoh/index.html

### Data Cleansing
* Joining SDOH(Social Determinants of Health) datasets between 2018-2020 years

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
Data Preprocessing for Machine Learning: Data preprocessing is a fundamental phase in preparing for machine learning analysis. This involves transforming raw data into an 
understandable format for machines. In our project, one of the key preprocessing steps was the addition of the “service count per 1k population” column. This was achieved 
by calculating the ratio of ‘Telehealth services count’ to ‘population per 1k’. This new feature provides a normalized measure of service utilization relative to population 
size, enhancing the model's ability to understand patterns in service usage. Another critical preprocessing step was handling missing values. We replaced null values with 
the average of the respective column. This approach, known as mean imputation, helps in maintaining the overall distribution of the data while dealing with missing values.
By ensuring that our data is clean, well-structured, and thoughtfully preprocessed, we lay a solid foundation for effective machine learning modeling. These preprocessing 
steps are essential in ensuring that the data fed into our machine learning models is of high quality, which is crucial for the accuracy and reliability of our predictive 
insights.

### Machine Learning Findings
Developed Individual Conditional Expectation(ICE) plots using the GAMI-NET Machine learning technique to identify how the target variable changes if the feature increases 
or decreases. The below graph shows the ICE plot of AHRF_DAYS_AIR_QLT feature which explains the number of air quality days in every county. Each line in the plot is an 
Instance of how the Prediction Value (“Services per 1k”) changes when AHRF_DAYS_AIR_QLT changes. The dense line in the bottom indicates that even though the 
feature(AHRF_DAYS_AIR_QLT ) changes there is no change in taking the services in that county but for some of the lines are increasing when the feature (AHRF_DAYS_AIR_QLT ) 
increase which means that the people change their behavior of taking telehealth services when there is increase in air quality days.

### Conclusions
These trends are significant for healthcare providers and policymakers because they highlight the need for flexibility in healthcare service delivery.
The data can inform future planning for healthcare services, indicating that telehealth is an important alternative or supplement to in-person care, especially in times of 
crisis. The charts would also be useful for assessing the impact of external events on healthcare service utilization and for planning infrastructure investments to support
the increased demand for telehealth services. The analysis shows a clear example of how healthcare delivery can rapidly change and adapt in response to societal changes and 
emphasizes the growing role of telehealth in the healthcare industry.

