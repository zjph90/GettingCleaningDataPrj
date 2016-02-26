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

## Requirements

1. Merge test and training sets
2. Select only the features which contained mean() or std() in the feature name
3. Use descriptive activity names
4. Use describle variable lables
5. Reduce to tidy, aggregated set with means of each feature by Subject and Activity.

## Transformation 
The feature list was loaded and filtered, using *grep*, to keep only the features which contained the string *mean()* or *std()*.

The feature names of interest were made more presentable by removing the brackets using *gsub*.

It was important to note that subject, X and Y data were in sequence so that the first row in the subject file corresponded to the first row in the X file and the first row in the Y file etc. For this reason the binding across subject, X and Y data was peformed within each of the *train* and *test* sets before merging these together.

The *subject* data, *Y* values and *X* values (filtered just for the columns of interest) were combined using *cbind*.

The *test* and *test* data were then merged using *rbind*

Finally, to average the values for each variable by Subject and Activity it was decide to first *melt* the data into long, "skinny" form: 

> Subject, Activity, variable, value

The *reshape2* function *dcast* was then used to cross-tabulate this data getting a *mean* value for each variable for each combination of Subject and Activity. 

This resultant "tidy" dataset was writtent to *tidy_data.txt*

## Running the code
**Assumption:** The dataset has been downloaded and unzipped into the current folder.  
Run simply with: -

> source(run_analysis.R)

This will result in the creation of the file *tidy_data.txt* in the current folder. This will contain the tidy data output for Objective 5.
