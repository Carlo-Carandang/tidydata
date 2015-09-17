# Creating a Tidy Dataset from the Human Activity Recognition Using Smartphones Dataset

## Overview

The [processing script](./run\_analysis.r) combines the experimental data 
collected and segregated into training and testing datasets before extracting 
only those variables which measure mean or standard deviation for each of the 
target activities. For each experimental subject and activity performed by the 
subject, the mean of each measurement of interest is calculated and stored 
within the final [tidy dataset](./tidydata.txt).

The [tidy dataset](./tidydata.txt) can be retrieved within R with the following 
command:

    tidydata <- read.table(tidydata.txt, header = TRUE)

The [tidy dataset](./tidydata.txt) produced by the run\_analysis.R script is a 
subset of the data contained in the Human Activity Recognition Using Smartphones
Data Set provided by the University of California at Irvine,  Center for Machine
Learning and Intelligent Systems. The [codebook](./CodeBook.md) describes each 
of the variables, values, and units in the tidy data set. A wide-format was 
chosen for the structure of the tidy dataset utilsing a strategy which promotes 
the following definition of tidy data.

    - an observation should be stored on an unique row
    - a variable or measure or characteristic of an observation should be stored
    in its own column

The resultant tidy dataset is comprised of 180 rows (observations) and 68 
columns (variables). The raw dataset is structured as 10299 rows and 563 
columns.

### run_analysis.r Walk-through

Before attempting to execute the [script](./run\_analysis.r) a narrative of the 
data processing highlights the major selection and transformation operations 
undertaken between raw data and tidy data.

**Synopsis**

0. Obtain the Human Activity Recognition Using Smartphones Data
    1. Fetch the activity monitoring data from the Getting and Cleaning Data 
    fileshare on Amazon Web Services
    2. Extract the archive contents to the current working subdirectory
1. Merge the training dataset and the testing dataset
    1. Read the activity labels and features to be applied to the training and 
    testing datasets
    2. Read the activity, subject, and measurement values for each of the 
    training and testing datasets
    3. Combine column-wise the subjects, activities, and measurements after 
    row-wise merging the training and testing components in a row-wise
2. Extract only the measurements on the mean and standard deviation for each 
measurement
    1. Associate variable names with each column of the combined dataset in 
    preparation to extract only the measurements of interest
3. Make descriptive activity names for each activitiy
    1. Remove underscores from the existing activity names before converting 
    them to lowercase and making these the descriptive activity names
4. Label the data set with descriptive variable names
    1. Normalise the variable names
    2. Handle unique single-characters before converting all variable names to 
    lowercase
    3. Handle unambiguous substitutions using a two-pass approach
5.  Creates a second, independent tidy dataset with the computed average (mean) 
of each variable for each activity and each subject
    1. Create a tidy dataset for subsequent analysis
    2. Compute the mean for each subject and each activity
    3. Save tidy dataset to file
    4. Clean-up the environment

*Note:* The run_analysis.r script requires installation of the reshape2 package 
for R.

**Variable Naming Normalisation Rules**

    - lowercase variable names
    - domain format: [t|f]
       f: Fast Fournier Transform
       t: time
    - subdomain: (t) t[body[accelerometer|gyroscope]|gravityaccelerometer], 
                 (f) fbodyaccelerometer
       f: Fast Fourier Transform
       t: time
    - axis designator format: [x|y|z]axis
    - axis statistic format: [x|y|z]axis[mean|std]

After reviewing the [codebook](./CodeBook.md) continue with the instructions to 
download the raw data, extract the archived data, transform the raw data into 
tidy data, and create an independenent tidy data file containing the mean of 
each measure for each subject-activity combination. These steps are handled by 
each section of the script.

To execute run\_analysis.R make the current working directory the subdirectory 
containing the run_analysis.R script, this README.md file, and the CodeBook.md 
file. The raw data will be automatically downloaded and extracted if it does not
already exist the in current working directory. The final dataset adheres to the
tidy data principles and is stored in wide-format.

```
> setwd("file_system_path_name/tidydata")
> source("./run_analysis.r")
```
