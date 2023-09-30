# Project Code Book

## run_analysis.R Script Description

The `run_analysis.R` script performs the data preparation followed by the five essential steps outlined in the course project's definition.

### Download the dataset

- The dataset is downloaded and extracted into a folder named "UCI HAR Dataset."

### Assign data to variables

- `features <- features.txt`: Contains 561 rows and 2 columns, describing features derived from accelerometer and gyroscope signals.
- `activities <- activity_labels.txt`: Contains 6 rows and 2 columns, listing activities and their corresponding codes.
- `subject_test <- test/subject_test.txt`: Holds test data from 9/30 volunteer test subjects.
- `x_test <- test/X_test.txt`: Stores recorded features test data.
- `y_test <- test/y_test.txt`: Stores test data activity code labels.
- `subject_train <- test/subject_train.txt`: Contains training data from 21/30 volunteer subjects.
- `x_train <- test/X_train.txt`: Holds recorded features training data.
- `y_train <- test/y_train.txt`: Stores training data activity code labels.

### Merge training and test sets

- `X (10299 rows, 561 columns)`: Created by merging `x_train` and `x_test` using the `rbind()` function.
- `Y (10299 rows, 1 column)`: Created by merging `y_train` and `y_test` using the `rbind()` function.
- `Subject (10299 rows, 1 column)`: Created by merging `subject_train` and `subject_test` using the `rbind()` function.
- `Merged_Data (10299 rows, 563 columns)`: Created by merging `Subject`, `Y`, and `X` using the `cbind()` function.

### Extract mean and standard deviation measurements

- `TidyData (10299 rows, 88 columns)`: Subsets `Merged_Data`, selecting only columns related to subject, activity code, and measurements on the mean and standard deviation.

### Use descriptive activity names

- Numbers in the code column of `TidyData` are replaced with corresponding activity names from the `activities` variable.

### Appropriately label the dataset

- The code column in `TidyData` is renamed to "activities."
- Column names with "Acc" are replaced with "Accelerometer," "Gyro" with "Gyroscope," "BodyBody" with "Body," "Mag" with "Magnitude," "f" at the start with "Frequency," and "t" at the start with "Time."

### Create a second, independent tidy dataset with averages

- `FinalData (180 rows, 88 columns)`: Created by summarizing `TidyData` to calculate the means of each variable for each activity and subject after grouping by subject and activity.
- `FinalData` is then exported to a file named "FinalData.txt."
