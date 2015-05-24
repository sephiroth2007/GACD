Introduction
============

This repository contains my work for the course project for the Coursera
course "Getting and Cleaning data", part of the Data Science
specialization. What follows first are my notes on the original data.

About the script and the tidy dataset
=====================================

I created a script called run\_analysis.R which will merge the test and
training sets together. Prerequisites for this script:

the UCI HAR Dataset must be extracted and.. the UCI HAR Dataset must be
available in a directory called "UCI HAR Dataset"

The code takes for granted all the data is present in the same folder,
un-compressed and without names altered.

CodeBook.md describes the variables, the data, and any transformations
or work that was performed to clean up the data.

run\_analysis.R contains all the code to perform the analyses described
in the 5 steps. They can be launched in RStudio by just importing the
file.

The output of the 5th step is called averages\_data.txt, and uploaded in
the course project's form.

Processing steps
================

First, unzip the data from
<https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip>
and rename the folder with "data". Make sure the folder "UCI HAR
Dataset" and the run\_analysis.R script are both in the current working
directory. Second, use source("run\_analysis.R") command in RStudio.
Third, you will find two output files are generated in the current
working directory: merged\_data.txt: it contains a data frame called
all\_data with 10299*68 dimension. averages\_data.txt: it contains a
data frame called result with 180*68 dimension. Finally, use data \<-
read.table("averages\_data.txt") command in RStudio to read the file.
Since we are required to get the average of each variable for each
activity and each subject, and there are 6 activities in total and 30
subjects in total, we have 180 rows with all combinations for each of
the 66 features.
