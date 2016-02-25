# Codebook for the tidy Data Set 

## Data

The raw data can be found at 

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Unzipped this contains two folders of data - one for testing, one for training. Each of these folders has a sub folder with raw data as well as 3 files contain aggregated data: 

* subject of sample.
* X values of sample.
* Y value of sample.

These 3 files are in sequence with each other. That is row 1 of the subject file corresponds with row 1 of the X and Y files etc.

In the root folder there is some reference data:

* activity labels - WALKING, RUNNING etc.
* feature labels - names of the X values
* feature info - description of the X values.

## Process and Transformation
The requirement was to 
1. Merge test and training sets
2. Select only the features which contained mean() or std() in the feature name
3. Use descriptive activity names
4. Use describle variable lables
5. Reduce to tidy, aggregated set with means of each feature by Subject and Activity.

TH


## Transformation 

## Running the code