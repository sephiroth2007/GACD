Code Book
=========

This is a code book that describes the variables, data, and any
transformations or work that you performed to clean up the data.

Raw data collection
===================

Collection

Raw data are obtained from UCI Machine Learning repository:
<http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones>.

Raw Data transformation
=======================

The raw data sets are processed with the script run\_analysis.R script
to create a tidy data set.

Merge training and test sets Test and training data, subject ids and
activity ids are merged to obtain a single data set. Variables are
labelled with the names assigned by original collectors.

Extract mean and standard deviation variables Keep only the values of
estimated mean and standard deviation .

Get descriptive activity names A new column is added to intermediate
data set with the activity description.

Get label variables appropriately Labels given from the original
collectors were changed to get valid/more descriptive R names

Create a tidy data set From the intermediate data set is created a final
tidy data set where numeric variables are averaged for each activity and
each subject.

Introduction
============

The script run\_analysis.Rperforms the 5 steps described in the course
project's definition.

First, all the similar data is merged using the rbind() function. By
similar, we address those files having the same number of columns and
referring to the same entities. Then, only those columns with the mean
and standard deviation measures are taken from the whole dataset. After
extracting these columns, they are given the correct names, taken from
features.txt. As activity data is addressed with values 1:6, we take the
activity names and IDs from activity\_labels.txt and they are
substituted in the dataset. On the whole dataset, those columns with
vague column names are corrected. Finally, we generate a new dataset
with all the average measures for each subject and activity type (30
subjects \* 6 activities = 180 rows). The output file is called
averages\_data.txt, and uploaded to this repository.

Variables
=========

x\_train, y\_train, x\_test, y\_test, subject\_train and subject\_test
contain the data from the downloaded files. x\_data, y\_data and
subject\_data merge the previous datasets to further analysis. features
contains the correct names for the x\_data dataset, which are applied to
the column names stored in mean\_and\_std\_features, a numeric vector
used to extract the desired data. A similar approach is taken with
activity names through the activities variable. all\_data merges
x\_data, y\_data and subject\_data in a big dataset. Finally,
averages\_data contains the relevant averages which will be later stored
in a .txt file. ddply() from the plyr package is used to apply
colMeans() and ease the development.
