# Peer-graded Assignment: Getting and Cleaning Data Course Project

This repository, submitted for the Getting and Cleaning Data course project, provides instructions for analyzing the Human Activity Recognition dataset.

Dataset: [Human Activity Recognition Using Smartphones](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

Files:

- CodeBook.md: This code book details the variables, data, and any transformations or data cleaning processes I performed.
- run_analysis.R: This script performs data preparation and follows the five steps outlined in the project's definition:
  - Merging the training and test sets to create a single dataset.
  - Extracting only the measurements related to mean and standard deviation for each measurement.
  - Assigning descriptive activity names to the activities in the dataset.
  - Appropriately labeling the dataset with clear variable names.
  - Creating a second independent tidy dataset from the dataset obtained in step 4, containing the average of each variable for each activity and subject.
- FinalData.txt: This file contains the exported final dataset after completing all the aforementioned steps.
