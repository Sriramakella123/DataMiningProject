### =============================================================================
###This R Script divides the States' Health Data into 5 specific Regions and in 
###next step shall be used to correlate Health Outcomes to Preventive Measures
###Linear regression and correlation plots could be made based on that.
### =============================================================================

#Loading the Library
library(readr)

#Setting the Working Directory for the R Script
setwd('/Users/sriram/Downloads')

#Read the CSV file into a new data frame
categoryDistribution <- read.csv('500CitiesLocalDataSetForBetterHealth_CleanedExcelv2.csv')

#View the data frame
View(categoryDistribution)

#Rename Column to a meaningful name
colnames(categoryDistribution)[8] <- "Data_Value_in_percentage"

#Make the column Numeric to carry out aggregation functions
categoryDistribution$Data_Value_in_percentage <- as.numeric(categoryDistribution$Data_Value_in_percentage)
categoryDistribution$PopulationCount <- as.numeric(categoryDistribution$PopulationCount)

#Calculate the Actual Population Count Value from the Data Value Column and Population Column
categoryDistribution$ActualPopulation <- (categoryDistribution$Data_Value_in_percentage*categoryDistribution$PopulationCount*0.01)

#Insert a new Column named Region and categorize states into different Regions ("South", "West", "Midwest", "Northeast", "USA")
categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Connecticut","Maine",
                                                                  "Massachusetts", "New Hampshire", 
                                                                  "Rhode Island", "Vermont")] <- "New England"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("New Jersey", "New York", 
                                                                  "Pennsylvania")] <- "Middle Atlantic"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Illinois", "Indiana", 
                                                                  "Michigan", "Ohio", 
                                                                  "Wisconsin")] <- "East North Central"


categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Iowa", 
                                                                  "Kansas", "Minnesota", 
                                                                  "Missouri", "Nebraska", 
                                                                  "North Dakota", "South Dakota")] <- "West North Central"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Delaware", "Florida", 
                                                                  "Georgia", "Maryland", 
                                                                  "North Carolina", "South Carolina", 
                                                                  "Virginia", "District of Columbia", 
                                                                  "West Virginia")] <- "South Atlantic"


categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Alabama", "Kentucky",
                                                                  "Mississippi", "Tennessee")] <- "East South Central"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Arkansas", 
                                                                  "Louisiana", "Oklahoma", "Texas")] <- "West South Central"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Arizona", "Colorado", "Idaho", 
                                                                  "Montana", "Nevada", "New Mexico", 
                                                                  "Utah", "Wyoming")] <- "Mountain"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("Alaska", 
                                                                  "California", "Hawaii", "Oregon", 
                                                                  "Washington")] <- "Pacific"

categoryDistribution$Region[categoryDistribution$StateDesc %in% c("United States")] <- "USA"
