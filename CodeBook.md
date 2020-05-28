File `<run_analysis.R>` creates tidy dataset requested by Coursera Programming Assignment for Module 3 in the Data Science Specialization, following the next steps:

1. Dowload dataset
Dataset downloaded and extracted as folder named UCI HAR Dataset

2. Assign each data to variables 
`<features>` <- `<features.txt>` contains 561 observations, 2 variables 
`<activities>` <- `<activity_labels.txt>` contains 6 observations, 2 variables
`<subject_test>` <- `<test/subject_test.txt>` contains 2,947 observations, 1 variable
`<X_test>` <- `<test/X_test.txt>` contains 2,947 observations 561 variables 
`<Y_test>` <- `<test/y_test.txt>` contains 2,947 observations, 1 variable
`<subject_train>` <- `<test/subject_train.txt>` contains 7,352 observations, 1 variable
`<X_train>` <- `<test/X_train.txt>` contains 7,352 observations, 561 variables 
`<Y_train>` <- `<test/y_train.txt>` contains 7,352 observations, 1 variable

3. Merge the training and the test sets to create one data set 
`<X>`       10,299 observations, 561 variables created by merging `<X_train>` & `<X_test>` using rbind() function
`<Y>`       10,299 observations, 1 variable created by merging `<Y_train>` & `<Y-test>` using rbind() function
`<Subject>` 10,299 observations, 1 variable created by merging `<subject_train>` and `<subject_test>` using rbind() function
`<Merged>`  10,299 observations, 563 variables is created by merging `<Subject>`, `<X>` & `<Y>` using cbind() function

4. Extracts only the measurements on the mean and standard deviation for each measurement
`<Tidy>`    created by subsetting `<Merged>`, selecting columns: `<subject>`, `<code>`, and measurements on the `<mean>` and standard deviation (`<std>`) for each measurement

5. Uses descriptive activity names to name the activities in the data set
Numbers in `<code>` column of `<Tidy>` replaced with corresponding activity taken from second column of the `<activities>` variable

6. Appropriately labels the data set with descriptive variable names 
`<code>` variable in `<Tidy>` renamed to `<activities>`
All `<Acc>` in variables names replaced by `<Accelerometer>` 
All `<Gyro>` in variable names replaced by `<Gyroscope>` 
All `<BodyBody>` in variable names replaced by `<Body>` 
All `<Mag>` variable names replaced by `<Magnitude>`
All `<start>` with character `<t>` in variable names replaced by `<Time>`
All start with character `<f>` replaced by `<Frequency>`
All `<tBody>` in variable names replaced by `<TimeBody>`
All `<-mean()>` in variable names replaced by `<Mean>` 
All `<-std()>` in variable names replaced by `<STD>`
All `<-freq()>` in variable names replaced by `<Frequency>`
All `<angle>` in variable names replaced by `<Angle>` 
All `<gravity>` in variable names replaced by `<Gravity>`

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
`<TDS>`     180 observations & 88 variables created summarizing `<Tidy>` taking the means of each variable for each activity and subject, after grouped by subject & activity
Export `<TDS>` into `<TidyDataSet.txt>` file
