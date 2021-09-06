### __7 Ways to handle Missing data : __

- __Deleting Rows with missing values__

Missing values can be handled by deleting the rows or columns having null values. If columns have more than half of the rows as null then the entire column can be dropped. The rows which are having one or more columns values as null can also be dropped.

1. Pros :A model trained with the removal of all missing values creates a robust model.
2. Cons : 
Loss of a lot of information. \
Works poorly if the percentage of missing values is excessive in comparison to the complete dataset.

- __Impute missing values with Mean/Median:__
Columns in the dataset which are having numeric continuous values can be replaced with the mean, median, or mode of remaining values in the column. This method can prevent the loss of data compared to the earlier method. Replacing the above two approximations (mean, median) is a statistical approach to handle the missing values.
The missing values are replaced by the mean value in the above example, in the same way, it can be replaced by the median value.

1. Pros: 
- Prevent data loss which results in deletion of rows or columns \
- Works well with a small dataset and is easy to implement.
2. Cons:
- Works only with numerical continuous variables.
- Can cause data leakage
- Do not factor the covariance between features. 

- __Imputation method for categorical columns:__
When missing values is from categorical columns (string or numerical) then the missing values can be replaced with the most frequent category. If the number of missing values is very large then it can be replaced with a new category.

![image](https://user-images.githubusercontent.com/51910127/132217016-18088b27-e796-47c6-81ee-130fbef5735c.png)

- __Other Imputation Methods:__
Depending on the nature of the data or data type, some other imputation methods may be more appropriate to impute missing values.
For example, for the data variable having longitudinal behavior, it might make sense to use the last valid observation to fill the missing value. This is known as the Last observation carried forward (LOCF) method.

For the time-series dataset variable, it makes sense to use the interpolation of the variable before and after a timestamp for a missing value.

- __Using Algorithms that support missing values:__
All the machine learning algorithms don’t support missing values but some ML algorithms are robust to missing values in the dataset. The k-NN algorithm can ignore a column from a distance measure when a value is missing. Naive Bayes can also support missing values when making a prediction. These algorithms can be used when the dataset contains null or missing values.
The sklearn implementations of naive Bayes and k-Nearest Neighbors in Python do not support the presence of the missing values.
Another algorithm that can be used here is RandomForest that works well on non-linear and categorical data. It adapts to the data structure taking into consideration the high variance or the bias, producing better results on large datasets.
![image](https://user-images.githubusercontent.com/51910127/132217223-27e038f5-5934-40cb-929b-630b2286a353.png)

- __Prediction of missing values:__
In the earlier methods to handle missing values, we do not use the correlation advantage of the variable containing the missing value and other variables. Using the other features which don’t have nulls can be used to predict missing values.
The regression or classification model can be used for the prediction of missing values depending on the nature (categorical or continuous) of the feature having missing value.
![image](https://user-images.githubusercontent.com/51910127/132217300-2a3a959a-8e12-4664-a21b-a985d07caa5d.png)
![image](https://user-images.githubusercontent.com/51910127/132217347-b9c3f82b-bcf7-47cb-983b-6150a36ce07d.png)

_ __Imputation using Deep Learning Library — Datawig__

This method works very well with categorical, continuous, and non-numerical features. Datawig is a library that learns ML models using Deep Neural Networks to impute missing values in the datagram.
Install datawig library,
pip3 install datawig
Datawig can take a data frame and fit an imputation model for each column with missing values, with all other columns as inputs.

![image](https://user-images.githubusercontent.com/51910127/132217469-4091c579-f11f-49e3-8240-fd55206e364b.png)
