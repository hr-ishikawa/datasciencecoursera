## Code Book

### Data Source

The data is collected from the accelerometers from the smartphone and gyroscope under the activity specified below.

- 'features_info.txt': Shows information about the variables used on the feature vector.
- 'features.txt': List of all features.
- 'activity_labels.txt': Links the class labels with their activity name.
- 'train/X_train.txt': Training set.
- 'train/y_train.txt': Training labels.
- 'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 
- 'test/X_test.txt': Test set.
- 'test/y_test.txt': Test labels.
- 'test/subject_test.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30. 

The labels of activity
1. WALKING
2. WALKING_UPSTAIRS
3. WALKING_DOWNSTAIRS
4. SITTING
5. STANDING
6. LAYING

### Step 1. Read Data and Merge them
1. Read train and test data files
- X_train.txt
- X_test.txt
- y_train.txt
- y_test.txt
2. Merge them to process in later at once
3. Name "ds1" to the marged data

### Step 2. Extract mean and standard deviation from the columns of measurement
1. Read features file (features.txt) and set to vector
2. Extract the strings contains "mean" and "std" from the vector and set to the vector named "extract"
3. Extract the columns form dataframe "ds1" by the vecter "extract" added TRUE as last element (that is for Activity labels)

### Step 3. Set the labels to the activities
1. Read activity_labels file (activity_labels.txt) and create the dataframe to relate activity labels and names
2. Join dataframe "ds1" and activity by label to map the activity labels to names
3. Drop the activity label column

### Step 4. Set features to the columns of data set
1. Set features to columns' name of the dataframe ds1
2. Write the dataframe "ds1" to DataSet1.csv

### Step 5.  Summarize by mean for Subject and Activity
1. Read subject files
- subject_train.txt
- subject_test.txt
2. Add subject column maned subid to "ds1"  and names "ds2"
2. Group the dataframe "ds2" by subject and activity
3. Summarize each columns to get mean
4. Write the dataframe "ds2" to DataSet2.csv