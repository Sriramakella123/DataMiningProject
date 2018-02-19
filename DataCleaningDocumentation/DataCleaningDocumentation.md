# Data Cleaning Documentation - 500 Cities Health Dataset

## Issues encountered with data

1. **Data validity and relativeness** - The data being collected for understanding the health of 500 cities in Unites States is limited to entire United States, respective city and census tract levels to undersatnd the Health Outcomes and Prevention categories. 
Assuming the data with respect to 2013 and 2014 the parameters are hence analyzed.

2. **Missing Values** - In the column CityName , DataValue , Data_Value_Footnote , PopulationCount has data range values having 'Blanks' that need to be filled with meaningful and reasonable datavalues that add meaning and value to the dataset and helps in efficient understanding of data.

3. **Unstandardized data** - The column UniqueID has data values '59', '107000' , '0107000-01073000100' etc. which doesn't follow a specified pattern or a clarity in naming the ID or providing definition for the ID. Moreover the value or ID details is not necessary. These need to be fixed or deleted based on the mode of data cleaning and the goal of cleansing the data.

4. **Irrelevant data with respect to Data cleaning and Visualization Goals** - The column UniqueID is not necessary with respect to evaluation of data or the pre-determined research goals. So I choose to delete the column. Also, the Data_Value_Unit which is in '%' can be deleted .The CityFIPS, TractFIPS, ShortQuestionText can be deleted

## Steps for Data Remediation

1. I am working on the  data research questions and goals clear and do not tend to chose the Census Data for tracting the Census values, instead I have limited data with respect to years 2013,2014  and also eliminated the FIPS value.

2. Additionally, I have filled the missing data values for CityName with 'NA' - _Not Applicable_ value and PopulationCount with 'Unknown' as those columns with the blank or unknown datavalue are not considered for any sort of data analysis and doesn't provide much detail or clarity on visualization. Instead, naming them appropriately as NA or Unknown helps in rethinking in data collection ar analysis steps.

3. Also I have deleted the irrevelant or unnecessary column and double-checked for data duplicacies and their existence and ensure their validity with respect to the data evaluation. This also involved redefining and understanding the end-goals in the data cleaning thereby I have deleted the unstandardized data.

## Step-by-step Description of Data Cleaning Process for Replication

Below are the sequence of steps followed in cleaning the data:

As part of cleaning, I have used R script and that helped in cleaning the data with respect to missing values, data anomalies, unstandardized values and entiry matching etc.

1. To get the current working directory:
**getwd()**

2. To set the working directory to the desired location:
**setwd("C:/Users/sriram/Downloads")**

3. Loading the desired files to the data frame "data":
**data<-read.csv("500CitiesLocalDataSetForBetterHealth_CleanedExcel.csv", header = T , na.strings = c("", "NA"))**

4. To view the loaded data drame:
**view(data)**

5. To removed the unwanted columns from the loaded data frame and making a new data frame:
**clean_data<-subset(data, select = -c(6,8,11,12,13,18,19,20))**

6. To view statistics relating the data:
**summary(data)**

7. Changing the "NA" values in "PopulationCount" Column to "Unknown" :
**clean_data[["PopulationCount"]][is.na(clean_data[["PopulationCount"]])] <- "Unknown"**

8. To view the top 6 rows of our working dataframe:
**head(clean_data)**

9. To view the entire dataframe:
**View(clean_data)**

10. To print the required table with set of arguments listed aboove for clean data:
**write.csv(clean_data, "500CitiesLocalDatasetForBetterHealth_CleanedExcelv2.csv")**

   
## Contributor
 Venkata Naga Sai Sriram Akella

