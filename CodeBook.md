The following describe the script project code
## set working directory
setwd(“/Users/justyuuu/Desktop/data science/getting and cleaning data”)
## library packages
library(data.table)
library(reshape2)
library(dplyr)
## variables
### 1 the training and the test sets to create one data set.trainData <- cbind(train.subject, train.y, train.x)
testData <- cbind(test.subject, test.y, test.x)
fullData <- rbind(trainData, testData)
### 2  Extract only the measurements on the mean and standard deviation for each measurement. 
featureName <- read.table("./data/UCI HAR Dataset/features.txt", stringsAsFactors = FALSE)[,2]
### 3  Uses descriptive activity names to name the activities in the data set
activityName <- read.table("./data/UCI HAR Dataset/activity_labels.txt")
### 5 From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
write.table(groupData, "./data/MeanData.txt", row.names = FALSE)
