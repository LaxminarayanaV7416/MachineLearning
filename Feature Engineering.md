```Python
#Packages used 
# Pandas
# Numpy
# Scikit-Learn
# Feature-Engine
```

#### What is a variable?
* Variable is a characteristic of amount or quantity that can be measured or counted.

#### Variable Characteristics
* Missing Data
* cardinality - one to one relation, one to many relation (joining of tables)
* Frequency of labels
* Distriutions
* Outliers
* feature magnitude

#### Missing Data Imputation 
* Mean, Median and mode imputation
* Random Sample Imputation
* Arbitrary value Imputation
* Missing Indicator
* Regression
* MICE (Multi Imputation by Chained Equations)
  
#### Categorical Encoding
* One hot Encoding
* Ordinal Encoding
* Count / Frequency Encoding
* Mean / Target Encoding
* Weight of Evidence
* Rare Label Encoding
* Hashing
  
#### Variable Transformation
* Logarithmic
* Reciprocal
* Exponential
* Power
* Yeo- Johnson
* Box - Cox

#### Discretisation
* Equal Width
* Equal Frequncy
* Fixed Interval
* Discretisation with Decision Trees
* Discretisation with Clustering

#### Outliers
* identification of outliers
* Removal of outliers
* Capping
* Winsorisation

#### Dates
* Extract Years, Months , Weeks , Days , etc.,
* Capture Elapsed Time
* Work with Time Zones

#### Feature Scaling
* Standardisation
* MinMaxScaling
* Robust Scaling
* Maximum Absolute Scaling
* Mean Normalisation
* Scaling to unit Length - Vector Norm
* Construct Pipelines (Semi Automated Machine Learning methodlogy)

#### Types of Variables
* There are totally two kinds of varibles they are:
  * Numerical Variables
    * Discrete Variables
      * This kinda varibales are usually whole numbers.
      * eg Items purchased from supermarket, No of kids, etc .,
    * Continous Variables
      * This varibles are real numbers in nature that can take any value between a specified range.
      * eg marked scored in exam, age , height, etc ., 
  * Categorical Variables 
    * Ordinal Variables
      * the possible variables are always in order.
      * eg rank secured, rating / feedback stars, etc .,
    * Nominal Varibales
      * the possible nomenclature of amount or quantity which do not have any possible value, it is used to represent the amount or quantity qualitatively.
      * for eg Names of person, country names, Postcodes, etc ., 
    * Date Time Varibales
      * A Speical type of categorical varibles which take date and time as inputs for measurement or count. Correct preprocessing is needed to get valuable information from dataset.
      * eg Date of Birth, Time of loan application, etc .,
  * Mixed Types of varible
    * variables that contains both numerical and categorical varibles is known as mixed type of varibles.
    * eg Cabin number , ticket number, Registration number in university , etc .,
  
#### Missing Data and Imputation techniques
* **Complete Case Analysis** 
  * Complete Case Analysis (CCA) also called as listwise deleteion of cases, involves discarding observations where any values are missing, it works for both categorical and numerical varibles. Complete case analysis means literally analysing only those instances or observations for which these information in all of varibles (X).
  *  CCA says to discard the case from dataset if any of the varible is missing (Though not advisable, because this may discard the most important cases from dataset which are actually used to determine solution for  the whole problem).
  *  CCA is the easiest and fastest method to remove missing values (if and onluy if the missing instances are very low adn negligible to size of dataset we have) , although noyt advised when missing insatances are more and dataset is so small.
  *  We can see other approaches like Imputation, etc .,
  *  We can also talk the variable distribution with respect to target variable and see the difference how it will change the distribution when CCA is used for every variable which have higher correlation, eg in case of titanic dataset we can see the age over ticket price whcih clearly says when CCA used the price is dropped drastically from $500 to 300$ in first place, and more over it will result in lost of more than 70% of data in case of titanic dataset.
*  **Mean and Median Imputation**
   *  