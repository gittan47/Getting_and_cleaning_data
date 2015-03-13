##CodeBook: Assignment Getting and Cleaning Data
Coursera course: Getting and Cleaning Data March 08, 2015

Data Set: Human Activity Recognition Using Smartphones

Data set for project: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

derived from the original data set: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Citation: Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. Human Activity Recognition on Smartphones using a Multiclass Hardware-Friendly Support Vector Machine. International Workshop of Ambient Assisted Living (IWAAL 2012). Vitoria-Gasteiz, Spain. Dec 2012

Assignment Objective:
To create one R script called run_analysis.R that does the following. 
Merges the training and the test sets to create one data set.
Extracts only the measurements on the mean and standard deviation for each measurement. 
Uses descriptive activity names to name the activities in the data set
Appropriately labels the data set with descriptive variable names. 
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

Once downloaded and unzipped, sourcing and running the run_analyis.R script in the same working directory as the unzipped raw data set will produce the tidy data set required by the assignment.

run_analysis.R assumes the data set is in the working directory and the file structure is unalterted.

See also the README.txt and the features_info.txt files in the UCI HAR Dataset folders for details on the original data and variables.

Original Data Used

This analysis is restricted to use of the data in the following files:

'features.txt': List of all features.

'activity_labels.txt': Links the class labels with their activity name.

'train/X_train.txt': Training set.

'train/y_train.txt': Training labels.

'test/X_test.txt': Test set.

'test/y_test.txt': Test labels.

The Inertial Signals data is not used.

Notes on the original data:
Features are normalized and bounded within [-1,1].
Each feature vector is a row on the text file.
For more information about the original dataset contact: activityrecognition@smartlab.ws

Original Variables

This analysis is limited to the mean() and std() variables related to the 20 time domain signals and 13 frequency domain signals derrived from the raw accelerometer and gyroscope data. There are 66 total original variables used for this analysis. In the following list -XYZ represents three axial signals: -X, -Y, -Z.

20 time domain signals:
tBodyAcc-XYZ
tGravityAcc-XYZ
tBodyAccJerk-XYZ
tBodyGyro-XYZ
tBodyGyroJerk-XYZ
tBodyAccMag
tGravityAccMag
tBodyAccJerkMag
tBodyGyroMag
tBodyGyroJerkMag
and 13 frequency domain signals:

fBodyAcc-XYZ
fBodyAccJerk-XYZ
fBodyGyro-XYZ
fBodyAccMag
fBodyAccJerkMag
fBodyGyroMag
fBodyGyroJerkMag
The complete list of original variables calculated for each of the 33 signals is as follows. However, as mentioned above, only the mean() and std() variables are used for this analysis.

The complete set of variables that were estimated from these signals are:

mean(): Mean value
std(): Standard deviation
mad(): Median absolute deviation 
max(): Largest value in array
min(): Smallest value in array
sma(): Signal magnitude area
energy(): Energy measure. Sum of the squares divided by the number of values. 
iqr(): Interquartile range 
entropy(): Signal entropy
arCoeff(): Autorregresion coefficients with Burg order equal to 4
correlation(): correlation coefficient between two signals
maxInds(): index of the frequency component with largest magnitude
meanFreq(): Weighted average of the frequency components to obtain a mean frequency
skewness(): skewness of the frequency domain signal 
kurtosis(): kurtosis of the frequency domain signal 
bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
angle(): Angle between to vectors.
Finally, these variables were were calculated for multiple observations of 30 volunteer subjects performing 6 activities. Those activities are: WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING

The Tidy Data Set Variables

The output of run_analysis.R is a 180 x 68 data.frame. The variables are as follows:

activity: Factor w/6 levels "LAYING", "SITTING", "STANDING", "WALKING", "WALKING_DOWNSTAIRS", "WALKING_UPSTAIRS" 
representing the 6 activities in which subjects enagaged to generate the observational data

subject: int 1:30
representing the 30 subjects that participated in the trials generating the observational data. One row of data is generated for each of the 6 x 30 combinations of activites and subjects.

For each activity/subject combination, averages of all observations for each of the mean() and std() time and frequency domain signals are calculated. The resulting variables are:

tBodyAcc-mean()-X
tBodyAcc-mean()-Y
tBodyAcc-mean()-Z
tBodyAcc-std()-X
tBodyAcc-std()-Y
tBodyAcc-std()-Z
tGravityAcc-mean()-X
tGravityAcc-mean()-Y
tGravityAcc-mean()-Z
tGravityAcc-std()-X
tGravityAcc-std()-Y
tGravityAcc-std()-Z
tBodyAccJerk-mean()-X
tBodyAccJerk-mean()-Y
tBodyAccJerk-mean()-Z
tBodyAccJerk-std()-X
tBodyAccJerk-std()-Y
tBodyAccJerk-std()-Z
tBodyGyro-mean()-X
tBodyGyro-mean()-Y
tBodyGyro-mean()-Z
tBodyGyro-std()-X
tBodyGyro-std()-Y
tBodyGyro-std()-Z
tBodyGyroJerk-mean()-X
tBodyGyroJerk-mean()-Y
tBodyGyroJerk-mean()-Z
tBodyGyroJerk-std()-X
tBodyGyroJerk-std()-Y
tBodyGyroJerk-std()-Z
tBodyAccMag-mean()
tBodyAccMag-std()
tGravityAccMag-mean()
tGravityAccMag-std()
tBodyAccJerkMag-mean()
tBodyAccJerkMag-std()
tBodyGyroMag-mean()

All are numeric variables, each the average of all observations of the original UCI HAR variables for the given activity and subject. Since each observation is normalized to a range of [-1,1], so too the 66 signal variables of the Tidy Data Set fall within the range [-1,1].


