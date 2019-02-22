# ML_project

In this project we explored data about pipes transporting water throughout the city of Atlanta.  The goal was to be able to identify key factors which contribute to a pipe breaking as well as to train a model capable of predicting whether or not a pipe should be broken given the available information.  In doing so we hoped to be able to identify those pipes which our model predicts are most at risk of breaking despite currently being unbroken.

The data is stored in Pipe_data.csv and definitions for column names is stored in Pipe_data_metadata.xlsx.

We began the ETL process in DataCleaning.ipynb using Pandas.  This code has since been cleaned, trimmed, and more heavily commented in the ETL block of code in Analysis.ipynb.

Once we got into the analysis, we realized that our models were behaving strangely.  Since there were so few broken pipes in our data our models were taking the "smart" strategy of simply predicting that every pipe is unbroken.  This is hardly useful to us however, so we opted to undersample the unbroken pipes so that during the training phase we had just as many broken as unbroken pipes which gave us a much more natural result.

We tried a number of different models including Logistic Regression, Neural Networks and Random Forests.  We decided on using random forests in the end as its results were slightly better than the other models but most importantly that it was able to return a value related to how important each feature was in the decision making process.  Finally, with a model selected we used cross-validation so as to get a prediction value for each data point while it was at the time in the testing data rather than the traning data.  Using these values we were finally able to make our predictions as to which pipes are most at risk of breaking and we can make our recommendation that these pipes be inspected and have preventative repairs performed.

Additional data exploration was done in Tableau and can be found in the folder marked as such.
