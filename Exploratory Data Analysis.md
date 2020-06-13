## Lets Learn Exploratory Data Analysis (EDA)

***
Reference Links
* [Link-1 @Anlaytics_Vidhya](https://www.analyticsvidhya.com/blog/2020/04/beginners-guide-exploratory-data-analysis-text-data/ "Beginners Guide")
* [Link-2 @Analytics_Vidhya](https://www.analyticsvidhya.com/blog/2016/01/guide-data-exploration/ "Comprehensive Guide")
* [Link-3 @Medium](https://medium.com/analytics-vidhya/a-z-exploratory-data-analysis-3fb5e388168e "Medioker Guide")
* [Link-4 @Machinelearningmastery-ChiSquare](https://machinelearningmastery.com/chi-squared-test-for-machine-learning/ "Chi Square test")
* [Link-5 @Medium Feature Engineering](https://towardsdatascience.com/feature-engineering-for-machine-learning-3a5e293a5114 "Feature Engineering")
* [Link-6 @Analytics-Vidhya Outlier detection using PyOD](https://www.analyticsvidhya.com/blog/2019/02/outlier-detection-python-pyod/ "Using Library PyOD for outlier detecttion")
* [Link-7 @Medium Outlier Detection](https://medium.com/@swethalakshmanan14/outlier-detection-and-treatment-a-beginners-guide-c44af0699754 "Beginners Guide")
* [Link-8 @Medium Removal of Outliers](https://towardsdatascience.com/ways-to-detect-and-remove-the-outliers-404d16608dba "Simplest of all fo outliers detection!")
* [Link-9 @Medium Feature Selection](https://towardsdatascience.com/the-5-feature-selection-algorithms-every-data-scientist-need-to-know-3a6b566efd2 "Feature Selection")
* [Link-10 @Elite Datascience Feature Engineering](https://elitedatascience.com/feature-engineering "Feature Engineering guuide")
* [Link-11 @Udemy Feature Engineering](https://www.udemy.com/course/feature-engineering-for-machine-learning/ "As a reference for subject in Feature Engineering")
* [Link-12 @Udemy EDA with pandas](https://www.udemy.com/course/exploratory-data-analysis-with-pandas-and-python-3x/ "Udemy Course just for reference")
* [Link-13 @Udemy Featrure Selection](https://www.udemy.com/course/feature-selection-for-machine-learning/ "Just for reference")
* [Link-14 @Feature Selection Free Course](https://www.learningcrux.com/course/feature-engineering-for-machine-learning "Use this course its all basics")
***
**Kaggle Guidance Links**
* [Link-1 @Complete guide](https://www.kaggle.com/pavansanagapati/a-simple-tutorial-on-exploratory-data-analysis "Complete guide without code")
* [Link-2 @EDA with Pandas](https://www.kaggle.com/kashnitsky/topic-1-exploratory-data-analysis-with-pandas "EDA with Pandas")
* [Link-3 @EDA with Pandas 2](https://www.kaggle.com/ekami66/detailed-exploratory-data-analysis-with-python "EDA with Pandas")
* [Link-4 @Comprehensive Guide](https://www.kaggle.com/pmarcelino/comprehensive-data-exploration-with-python "Comprehensive Kaggle Guide for EDA")
* [Link-5 @EDA with Python](https://www.kaggle.com/fazilbtopal/exploratory-data-analysis-with-python "EDA with Python")
* [Link-6 @EDA with Visualization](https://www.kaggle.com/arthurtok/exploratory-data-analysis-visualisation "EDA along Visualization")
* [Link-7 @Feature Engineering Tutorials](https://www.kaggle.com/learn/feature-engineering "Feature Engineering from kaggle")
* [Link-8 @Feature Engineering on Titanic Dataset](https://www.kaggle.com/gunesevitan/titanic-advanced-feature-engineering-tutorial "Look the way he is solving the solution")
* 
***

#### 1. What is Exploratory Data Analysis (EDA)?
* Exploratory Data Analysis (EDA) is an approach/philosophy for data analysis that employs a variety of techniques (mostly graphical) from statistics to linear algebra by using simple plotting tools, to understand what our dataset is, before going to do actual machine learning or deep learning.
* we have many options of doing EDA easiest way is using 
    * Orange Data Mining tool
    * Python Packages (such as seaborn, matplotlib, pandas, etc.,) 
    * R Language Packages (ggplot2, etc.,)

##### Note - This whole document focuses on how to implement EDA in python Language !! As this data is concerned we are starting from scratch which implies its a Raw Data, we have to perform EDA and figure out traget varibles, figure out what kinda machine learning problem we are trying to address and what insigths we have drawn from data.

#### 2. Lets Begin our primary steps towards exploratory data analysis (Hand Shacking with Data)?
* The first step in EDA is to print the shape of the loaded data, and you expect the shape to be in two dimensional if not make them two dimensional using numpy reshape, (#No_of_rows, #No_of_columns/features) now the rows are the instances of the data on other hand columns indicate the number of features (Important to remember because it plays crucial role during applying algorithm [Images data is little different thats wholly an another discussion])
```Python
print(dataframe.shape) #eg output (2000,12) -> 2000 instances with 12 features 
```
* Now lets see what are the columns in the dataframe using pandas library (! use what ur language or tool supports) 
```python
print(dataframe.columns) # prints list of column names -> [column1, column2,....]
```
* with step we will have clear idea what are the column names and with these names we will look at sample data like below code.
```Python
dataframe.head(5) #prints first five rows of the data 
```
* lets also see what kinda of data we are dealing with for each column so that we can follow some techniques which makes us step ahead.
```Python
dataframe.info() #prints the information of every feature such as datatype, number of observations.
```

#### 3. What are the steps of EDA ? (process after Handshake!)
* lets see what are the steps in Exploratory data analysis, here are the steps in EDA : 
    1. Hypothesis Design (Understanding Problem Statement)
    2. Variable Identification
    3. Univariate Analysis
    4. Bi-variate Analysis
    5. Missing Values Detection
    6. Outlier Detection
    7. Feature Engineering
       * Missing values treatment
       * Outlier treatment
       * Feature transformation
         * Discretization Technique / Binning
         * Frequency Encoding / Binning
       * Feature creation
       * Feature Scaling
       * Dimensionality Reduction
    8. Feature Selection
    9. Pipeline Construction

##### Note - we will need to iterate over steps 5 – 9 multiple times before we come up with our refined model.
* **Step - 1 Hypothesis Design** :
As we hand shaken with the data now lets try to frame understand the what we are trying to solve (Business Problem or any real world problem), this will help us to proceed ahead with the data we have. if you didnt understand problem statement kindly reachout your superiors.
* **Step - 2 Variable identification** :
After understanding what is the problem statement it would be easy for us to determine what could be our target variable/variables (column/columns) and left of data would be our features for the model. most important in this step to identify the datatypes of the columns (all features and all targets), where we need to findout what kinda data we are dealing with and have to divide data into categorical and continuous data categories.
  * Now lets se what are different data categories, As there are two superior categories they are known as Quantitative Data / Continuous Data and Qualitative Data / Categorical Data (<- Included discrete data in categorical because they share same type of techniques in EDA).
  * Lets see some examples of the data categories : 
    * Categorical Data - feedback scale, sex, yes/no, True/False, Person Name, etc.,
    * Continuous Data - Age, Weight, Height, Exam Marks, etc.,
* **step - 3 Univariate Analysis** :
As in Above step we have differentited our data into different categories now, lets see how to use Univariate Analysis on different categories of data. in this univariate analysis we follow different techniques to transform the data into normality. lets see what techniques we can use for two categories of data.
    * Categorical Data - we need to design a frequency table (simply counting number of occurances or number of occurances percentage in each category and forming a table with this data) and we can visualize this data with bar chart or horizontal bar chart.
       * for Text data use this countplot for visualization
        ```Python
        df.describe(include=['object']) #which describes only text it contains count, unique, top, freq
        sns.countplot(x='species',data=iris_df) #to see the count plot basically its a bar chart
        ```  
    * Continuous Data - we need to understand the central tendency and spread of variable which are measured using metrics like Measure of central tendency -> (mean, median, mode, Min, Max), Measure of Dsipersion -> (standard deviation, IQR (Inter Quartile Range) Variance, Skewness and Kurtosis, Quartile, Range) and we can use Histogram (Measure of central tendency) for visulization.
      ```Python 
      sns.distplot(iris_df['sepal_length'],kde=True) #to see how well data is distributed basically it a histogram with kernal density estimator
      ```
      ```Python
      df.describe() #to print the dispersion metrics it displays min,max,mean,median,mode, count, quartiles.
      ```
      from continuous variables we can do some feature transformation such as in distplot if we found that the varible is not following normal distribution we can transform the data to log normal distribution or any other distribution refer statistics for betterment.
  * **Note** : Univariate analysis is different in context of NLP and Image Data.
* **step - 4 Bivariate Analysis** : 
As in above section we have seen the importance of univariate analysis, Now lets see the importance of bivariate analysis, bivariate analysis is super handy in finding out the relationship between two variables / columns, here in bivariate analysis we look for association or disassociation between variables / columns at a predefined significance level. we can perform bivariate analysis of three kinda combination of categorical and continuous data, where the combinations are (Categorical and Categorical) , (Categorical and Continuous) and (Continuous and Continuous) though different methods are used during different process, lets proceed with these combinations.
  * **Continuous and Continuous Data** : While we are dealing with the continuous and continuous variables we have to see the correlation between these two variables generally correlation lies between -1 to 1 where -1 indicates negative linear correlation (strongly correlated and significant) , 1 indicates positive linear correlation (strongly correlated and significant) and finally 0 indicates no correlation (not significant), but in real world not everything is perfectly correlated to 1 or -1 so we have believe which are closer to 1 or -1 are strongly correlated. for visualization we can use scatter plots from seaborn.
    ```Python
    sns.jointplot(x='column_name',y='column_name',data=dataframe) #here kind is scatter
    sns.regplot(x='column_name',y='column_name',data=dataframe) #regression plot to see the regression line fit
    sns.scatterplot(x='column_name',y='column_name',data=dataframe,hue='column_name') #pure scatterplot from seaborn have option to use hue and see species in different colors
    ```
  * **Categorical and Categorical Data** : finding relationship between two categorical variables have two different approached lets see one by one clearly -
    * Contingency Table / Two way Table - we can create a two way table where row of table represents count or count percentage of one variable and column of table represents count or count percentage another variable, by looking at this table we can analyse the relationship between the varibles, for visulazation purpose we can use the stacked bar chart which are handy and part of pandas dataframe
    ```Python
    dataframe.plot(kind='bar',stacked=True) #for stacked bar plot, use the dataframe of two way table
    ```
    * Chi-Square Test - as from above visualization if we cannot draw much intution so we can use chi-square test from our statistical toolbox, where we have to use above created contingency table for determination whether two variables are dependent or independent of each other. here are some tips for comparision of values you calculated, always use Alpha = 0.05 which implies level of significance is 95% or 0.95.
      * if statistic >= Critical value - significant, reject null hypothesis, dependent variables.
      * if statistic < Critical value - not significant, fail to reject null hypothesis, independent varibales.
      **OR**
      * if P-value <= Alpha - significant, reject null hypothesis, dependent variables.
      * if P-value > Alpha - not significant, fail to reject null hypothesis, independent varibales.
      Please follow below example implementation of Chi-Sqaure test
      ```Python
      from scipy.stats import chi2_contingency
      from scipy.stats import chi2
      table = pd.pivot_table(df) #use pivot_table from pandas to construct contingency table
      stat, p, dof, expected = chi2_contingency(table)
      # interpret test-statistic
      prob = 0.95
      critical = chi2.ppf(prob, dof)
      print('probability=%.3f, critical=%.3f, stat=%.3f' % (prob, critical, stat))
      if abs(stat) >= critical:
          print('Dependent (reject H0)')
      else:
          print('Independent (fail to reject H0)')
      # interpret p-value
      alpha = 1.0 - prob
      print('significance=%.3f, p=%.3f' % (alpha, p))
      if p <= alpha:
          print('Dependent (reject H0)')
      else:
          print('Independent (fail to reject H0)')
      ```
      we can either use Cramer’s V for Nominal Categorical Variable and Mantel-Haenszed Chi-Square for ordinal categorical variable if we feel chi-sqaure test doesnt justify the case.
  * **Categorical and Continuous Data** : finding dependency and independency between categorical and contionuous is quite easy than compared to all above tasks and these visualization plots are quite useful even in anamoly detection as well, lets talk about visualization first we can draw boxplot for each categorical variable over continous variable (use seaborn.boxplot) or even draw stacked embeded histogram with alpha channel to see overlap relation, if still didnt find and statistical significance we can perform Z-test, T-test or ANOVA.
    * Visualization - lets plot some graphs
    ```Python
    sns.boxplot(x='species',y='sepal_length',data=df) #for boxplot 
    #### (OR) ####
    #this method is little painful we have to write this for every category of categorical data 
    df[df['species']=='setosa']['sepal_length'].hist(alpha=0.5) #applying filter 1
    df[df['species']=='virginica']['sepal_length'].hist(alpha=0.5) #applying fitler 2
    df[df['species']=='versicolor']['sepal_length'].hist(alpha=0.5) #applying filter 3
    #### (OR) ####
    #for hue option in continous variable distribution kinda plot
    sns.FacetGrid(dataframe,hue='categorical_column',size=5).map(sns.distplot,'continuous_col')\
        .add_legend()
    """As we take the bin size smaller and smaller we are going towards the more and more accurate decisions"""
    ```
    * Statistical tests for dependency estimation - lets see all types of statistical significant tests
      * Z-Test/ T-Test:- Either test assess whether mean of two groups are statistically different from each other or not. if the probability of Z is small then the difference of two averages is more significant. The T-test is very similar to Z-test but it is used when number of observation for both categories is less than 30.
        ```Python
        #code snippet pending for these Z-test/T-test
        ```
      * ANOVA:- It assesses whether the average of more than two groups is statistically different.
        ```Python
        #code snippet pending for these ANNOVA
        ```
  * Bonus Visualization techniques for better feature selection - 
    * Plotting Correlation in heatmap - 
        ```Python
        sns.heatmap(df.corr(),annot=True,cmap="Blues") #heatmap with correlations annotated inside each box
        ```
    * Multivariate Analysis - Burp, this thing exsists but finally it does same thing what we are trying to do in bivariate continuous and continuous analysis, but here we are dealing whole dataframe's data.
        ```Python
        sns.pairplot(df,kind='reg') #to see all bivariate plots together(only cont vs cont variables)
        ```
* **Step - 5 Missing Value Detection** : Reason for detecting the missing plot is that it will effect the performance of the machine learning model, thus detectin gmissing values most important and addressing missing values are also important (but we will address this later in Feature Engineering section). we can detect missing values by simple count or count% of every feature, we can visualize this by bar plot or heatmap from seaborn. lets see some code snippets for detecting and visualizing missing data.
```Python
#first lets plot the count plot 
sns.barplot(dataframe.count().index,dataframe.count()) #easiest way to plot countplot
#now lets see the plot for missing data
print(dataframe.isnull().sum()) #print sum of missing data for every feature
print(dataframe.isnull().mean()) #print the percent of missing data for every feature
sns.heatmap(dataframe.isnull(),yticklabels=False,xticklabels=False) #heatmap shows where the missing plots are present
#### (OR) ####
sns.barplot(dataframe.isnull().sum(),dataframe.isnull().sum().index) #barplot to show missing plot quite handy!
```
* **Step - 6 Outlier Detection** : Outliers also play a major role for downfall of machine learning model performance. simply speaking outlier is an observation that appears far away and diverges from an overall pattern during visualization of data in a sample. there are two types of outliers they are univariate and multivariate outliers where univariate outliers are found when we look at single variable at a time, on other hand multi variate outliers are found in N-Dimensional space. now lets interpret how to detect outliers we can use Boxplot, Histogram and scatter plot for detection of outliers. lets understand what can be done to detect outliers during each visulaization technique.
  * Extreme Value Analysis : Using BoxPlot Any Value which is beyond range of -1.5*IQR to 1.5*IQR, where IQR means inter quartile range, for this method we can detect the extreme end and lower end and remove it. below code is simple use case for the detection, we will see how to remove or handle outliers in feature engineering.
    ```Python
    #lets write a simple function to detect outliers
    def outlier_detector(value):
        upper_value=10 #this is the value of qunatile(0.75)+(1.5*IQR)
        lower_value=0 #this is the value o qunatile(0.25)-(1.5*IQR)
        if value>upper_value: #if condition statisfies which means value is greater than extrame value
            print('Its and Outlier!!')
        elif value<lower_value: #if condition statisfies which means value is lesser than extrame value
            print('Its and Outlier!!')
        else: #no condition is satisfied so not an outlier
            print('Not an outlier!!')
    
    df[df['species']=='virginica']['sepal_length'].apply(outlier_detector) #prints for every value is an outlier or not
    #now lets print the percentages of the outliers
    #lets get the total number instances for particular class!
    total=df[df['species']=='virginica']['sepal_length'].shape[0]
    #code to get percentage of upper and lower outliers in data!
    upper_out=df[df['species']=='virginica'][df['sepal_length']>upper]['sepal_length'].shape[0]/total
    lower_out=df[df['species']=='virginica'][df['sepal_length']<lower]['sepal_length'].shape[0]/total
    print(f'Upper Bound outliers percentage is {upper_out}') #print the values
    print(f'Lower Bound outliers percentage is {lower_out}') #print the values

    #### (OR) ####
    sns.boxplot(x='species',y='sepal_length',data=df) #using box plot instead of calculating them.
    ```
  * We can use Scatter plot and histrograms for visualization for detection of outliers, here is the sample code.
    ```Python
    y=np.arange(0,df['sepal_length'].values.shape[0]) #creating empty y as like linear scale fro univariate visualization
    sns.regplot(df['sepal_length'].values,y,scatter=True) #plotting using regplot to fit the best fit line also

    #### (OR) ####
    sns.distplot(df['sepal_length'],kde=True) #plotting hstrograms with kernal density estimator for detecting outliers
    ```
  * Data points which are three or more standard deviation away from mean is considered as outilers, we can implement this by converting our data to Gaussian normal distribution using Z-Score. lets see how to implement this in python :
    ```Python
    from scipy.stats import zscore
    z=zscore(dataframe) #converts all data to respective zscore using formula x-mean/standard deviation
    #As per above point threshold is greater than three
    threshld=3
    print(np.where(z>threshold)) #filtering code
    ```
  * Using Capping methods any value which is out of 5th quartile and 95th quartile is treated as outliers or Top coding, Bottom coding where these coding techniques means, in case of top coding there is value set as top value where in reality these values are not reached for eg., human age of 200 yrs, height of 12 feet, etc., adn on other hand bottom values are set for eg., human age being negative, distance in negative, etc., coding handling we can give some parameters for every feature in the data and store there index and treat them as outliers and address it.
  * Outlier detection is merely a special case of the examination of data for influential data points and it also depends on the business understanding.
  * Bivariate and multivariate outliers are typically measured using either an index of influence or leverage, or distance. Popular indices such as Mahalanobis’ distance and Cook’s D are frequently used to detect outliers.
* **Step - 7 Feature Engineering** : 
