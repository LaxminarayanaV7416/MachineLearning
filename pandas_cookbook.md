### Lets begin our pandas Cookbook

```Python
import pandas as pd

pd.get_option('dispaly.max_rows')
pd.get_option('dispaly.max_columns')
pd.set_option('display.max_rows',100)
pd.set_option('display.max_columns',100)
pd.reset_option('display.max_rows')
pd.reset_option('display.max_columns')
pd.get_option('max_info_columns')
pd.get_option('max_info_rows')
```
#### visit Pandas documentation for better use of options as per requirement
#### Visit Pandas documentation for more information other than examples here

* lets talk to load data as dataframes from csv, excel and sql server

```Python 
import pandas as pd
from sqlalchemy import create_engine

# loading dataset from csv 
df = pd.read_csv('filename.csv',sep=',')
# NOTE : for more options use pandas documentation

#loading dataset from excel file
df = pd.read_excel('excel_filename.xlsx',sheet_name='name_of_sheet_or_index')

#loading data from sql server
engine = create_engine('sqlite:///sample.db')
df = pd.read_sql_query('SELECT * FROM table_name', engine)

df.head(5) # common for all to see first five rows of the data loaded!
```

* Now lets see how to do data wrangling using pandas

```Python
import pandas as pd

df = pd.read_csv('file_name.csv')

# firt step in data wrangling is to print the info and so that we can come to know waht all datatypes are there in the dataframe
df.info() #prints the info about dataframe

#now we have to describe the dataframe so taht we can see descriptive stats of the qualitative data(numerical data)
df.describe()  #prints the descriptive stats of the qualitative data


```
