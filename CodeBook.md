File `<run_analysis.R>` creates tidy dataset requested by Coursera Programming Assignment for Module 3 in the Data Science Specialization, following the next steps: :nerd_face:

1. Dowload dataset
Dataset downloaded and extracted as folder named UCI HAR Dataset

2. Assign each data to variables 
`<x_train>` <- `<train/X_train.txt>` contains 7,352 observations, 561 variables
`<Y_train>` <- `<train/y_train.txt>` contains 7,352 observations, 1 variable
`<subject_train>` <- `<train/subject_train.txt>` contains 7,352 observations, 1 variable
`<x_test>` <- `<test/X_test.txt>` contains 2,947 observations 561 variables 
`<y_test>` <- `<test/y_test.txt>` contains 2,947 observations, 1 variable
`<subject_test>` <- `<test/subject_test.txt>` contains 2,947 observations, 1 variable
`<features>` <- `<features.txt>` contains 561 observations, 2 variables 
`<activity_lables>` <- `<activity_labels.txt>` contains 6 observations, 2 variables

3. Merge the training and the test sets to create one data set 
`<mrg_train>` 7,352 observations & 563 variables created by merging `<y_train>`, `<subject_train>` and `<x_train>` using cbind() function 
`<mrg_test>` 2,947 observations & 563 variables created by merging `<y_test>`, `<subject_test>` and `<x_test>` using cbind() function 
`<setAllInOne>` 10,299 observations & 563 variables created by merging `<mrg_train>` and `<mrg_test>` using rbind() function

4. Extracts only the measurements on the mean and standard deviation for each measurement
`<colNames>` extracts colnames of `<setAllinOne>`
`<mean_and_std>` pattern match of text "activityId", "subjectId", "mean.." & "std.." in colnames of `<setAllinOne>`
`<setForMeanAndStd>` extracts only the mean and standard deviation values requested

5. Uses descriptive activity names to name the activities in the data set
`<setWithActivityNames>` merges previous extracted mean and std deviation

6. Appropriately labels the data set with descriptive variable names 
Performed in previous steps

7. From the data set in step 4, creates a second, independent tidy data set with 
`<secTidySet>` performs requested calculations for mean and standard deviation 
`<secTidySet.txt>` file with tidy data
