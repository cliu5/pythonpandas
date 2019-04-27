# Python Pandas

### History
![Wes McKinney](https://avatars1.githubusercontent.com/u/329591?s=400&v=4)

Python panda was created by Wes McKinney! He was
* Born in Akron, Ohio
* Went to MIT then to New York to study finance at AQR Capital Management
* Realized biggest problems came from formulating data rather than gathering it
* Wanted a program that could analyze and work with data for people who are not expert in computer scientists
* In 2008, McKinney began working on a “Python Data Analysis Library” that used that used “panel data” 
* Dropped out of graduate school to work on Pandas
* Currently works full-time on Panda at Two Sigma 
> **pan**el **da**ta = pandas

### What is Python Panda?
* Open source python library (ie Requests, MatPlotLib, NumPy, Flask)
* It’s purpose is to provide easily accessible and high performance data structures to use in Python
* Python data structures (lists, strings, arrays, dicts) are good for data munging & preparation but not good for analysis & modeling
  * Munging: transforming and wrapping data

### Code Demo
```markdown
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt

# pandas will read from the courses csv file and build a dataframe around it
df = pd.read_csv('courses.csv')
# BUT WHATS IN THE DATAFRAME?!
print(df)

courses = pd.DataFrame(columns=['Code', 'Mark', 'Id'])
print (courses)

# dataframe.iterrows() iterates over the DataFrame as (index, Series) pairs
for (row, series) in df.iterrows():
    code = series[0]
    mark = series[1]
    id = series[2]
    courses.loc[row] = [code, mark, id]
print (courses)

systems = courses[courses.Code == 'systems']
systems.plot.bar(x='Mark')
systems.plot.bar(x='Code')
systems.plot.bar(x='Id')

print(systems)
plt.show()

```
