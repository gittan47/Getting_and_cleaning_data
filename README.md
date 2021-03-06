## Getting_and_cleaning_data
Course_March-15
In this repo is a file called run_analysis.R with the code for the assignment in the course.
##Purpose
The purpose is to demonstrate how to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. There is also a code book that describes the variables, the data, and any transformations or work that are performed to clean up the data called CodeBook.md. Also included is this README.md in the repo as my script.
##Contents
Here are the data for the project that can be downloaded and unzipped by the package "downloader":

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

The R script called run_analysis.R does the following: 
* Merges the training and the test sets to create one data set.
* Extracts only the measurements on the mean and standard deviation for each measurement. 
* Uses descriptive activity names to name the activities in the data set
* Appropriately labels the data set with descriptive variable names. 
* From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

What you find in this repository is: 
* CodeBook.md: information about raw and tidy data set 
* README.md: this file
* run_analysis.R: R script to transform raw data set in a tidy one
