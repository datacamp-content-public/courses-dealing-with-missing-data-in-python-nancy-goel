---
title: Insert title here
key: 0c5f8c88ecf599b36dbbe2e97361d32c
video_link:
  mp3: https://assets.datacamp.com/production/repositories/4322/datasets/7ed08013ad71509d0a754b1f80099823da5d3a7f/Recorder-007%20(online-audio-converter.com).mp3

---
## Forward and Backward Filling

```yaml
type: "TitleSlide"
key: "2f8ff34a78"
```

`@lower_third`

name: Nancy Goel
title: Data Analyst


`@script`
In the last set of exercises, you worked on marking and removing rows with missing data. Now let's move towards a more realistic problem where forward and backward filling of missing data come handy.


---
## Fillna() method

```yaml
type: "FullSlide"
key: "740519e836"
```

`@part1`
- is used when data in considerable amount of rows is missing.
{{0}}
- forward fill and backward fill are attributes of this method.
{{1}}

```Python
In [0]: Import pandas as pd
In [1]: state_data = pd.read_csv('state-population1.csv')
In [2]: state_data.shape
Out[2]: (2544, 4) 
```{{2}}

```Python
In [3]: state_data.isnull().sum()
Out[3]: state/region      0
        ages              0
        year            628
        population      146
        dtype: int64

```{{3}}


`@script`
Before moving directly to the concepts of forward fill and backward fill, you will learn about fillna method. This method is used when a considerable amount of data in rows is missing in your dataset. Forward fill and backward fill are the two attributes of this method. Now, take a look at the following dummy dataset and note the total number of rows. Next check for the missing values as learnt in the previous chapter. Here we have 628 instances null in year column and 146 instances null in the population column which makes up around 30% of the total data.


---
## Fillna() method

```yaml
type: "FullSlide"
key: "05b779ca89"
```

`@part1`
```Python

In [0]: Import pandas as pd
In [1]: state_data = pd.read_csv('state-population.csv')
In [2]: state_data.shape
Out[2]: (2544, 4) 
In [3]: state_data.isnull().sum()
Out[3]: state/region      0
        ages              0
        year            628
        population      146
        dtype: int64
```{{0}}
```Python
In [4]: state_data.fillna(0)
```{{1}}
```Python
In [5]: state_data.isnull().sum()
Out[5]: state/region    0
        ages            0
        year            0
        population      0
        dtype: int64
```{{2}}

-  you can also substitute missing values with mean or median of the total values.{{3}}


`@script`
Since 30% is a considerable amount, you can't simply drop all the rows with missing data. In such scenarios, you will use fillna method and substitute null values with an appropriate value. Let's replace all the null values with 0 here and check for the results. We have successfully got rid of our missing values. You can experiment and replace your null values with an appropriate value. For an instance, if your dataset contains employee data, and salaries for some of the employees is missing. You can replace the null value of an associate's salary with another associate's salary figure, which would make more sense than replacing with zero in such scenario. You can also substitute missing values with mean or median of the total values as appropriate.


---
## Forward and Backward Fill

```yaml
type: "FullSlide"
key: "c895a2a285"
code_zoom: 123
```

`@part1`
- Forward Fill: Filling null values with value in the **previous** rows.{{0}}
- Backward Fill: Filling null values with value in the **following **rows.{{1}}

![](https://assets.datacamp.com/production/repositories/4322/datasets/a0ff1e7c84bd5aa0adf4291062c01d033e3ecf57/Screenshot.png) {{2}}


`@script`
You have other attributes in the fillna method, which could be used to fill the columns with missing values. One of which is forward fill attribute. When you fill the null values with the value in the previous row of the same column, then this is called forward filling. Another is backward fill attribute. When you fill the null values with the value in the following row of the same column, then this is known to be as backward filling. Let's consider the following test data. Here you have missing values in the columns A and B.


---
## Forward Fill

```yaml
type: "FullSlide"
key: "9f03f228c5"
code_zoom: 140
```

`@part1`
```python
In [0]: import pandas as pd
In [1]: df = pd.read_csv('test.csv')
In [2]: data = df.fillna(method='ffill')
``` {{0}}

![](https://assets.datacamp.com/production/repositories/4322/datasets/be3829a5e756be5b8eef0d33a50d0582f5ce3a75/Screen%20Shot%202018-12-25%20at%202.42.02%20PM.png){{1}}


`@script`
Here you try both forward and backward fill, one by one. First is forward fill. You will use method = ffill in single quotes to implement this attribute. As you see, row with indices 1 and 5 are filled with previous row values.


---
## Backward Fill

```yaml
type: "FullSlide"
key: "5b00ec1695"
```

`@part1`
```python
In [0]: import pandas as pd
In [1]: df = pd.read_csv('test.csv')
In [2]: data = df.fillna(method='bfill')
``` {{0}}

![](https://assets.datacamp.com/production/repositories/4322/datasets/ecc31f631f0c536fe49548b9b971924db5adf588/Screen%20Shot%202018-12-25%20at%203.06.36%20PM.png){{1}}


`@script`
Next is backward fill. You will use method = bfill in single quotes to implement this attribute. As you see, row with indices 1 and 5 are filled with following row values.


---
## Forward and Backward Fill

```yaml
type: "FullSlide"
key: "8677e6d2f8"
```

`@part1`
- if a previous value is not available during a forward fill, or backward fill the NA value remains.{{0}}

![](https://assets.datacamp.com/production/repositories/4322/datasets/35e7a324a88d459a3d5f54d3553d1ed713884e81/Screen%20Shot%202018-12-25%20at%203.15.18%20PM.png){{1}}


`@script`
Now,What if you don't have any data in the previous row for forward fill and following row for backward fill. Look at this table. In such a scenario, use of forward and backward fill separately won't serve the purpose.


---
## Forward and Backward Fill

```yaml
type: "FullSlide"
key: "7949b94929"
```

`@part1`
```Python
In [1]: data = df.fillna(method='ffill').fillna(method='bfill')
```{{0}}
![](https://assets.datacamp.com/production/repositories/4322/datasets/84f1973d2ade7ad02cd2468302231338fee93a8e/Screen%20Shot%202018-12-25%20at%203.17.56%20PM.png){{1}}


`@script`
So, you would use both forward and backward fill attributes as shown in the code. And you get the right output.


---
## Summary

```yaml
type: "FullSlide"
key: "69de38fc1f"
```

`@part1`
Fillna() method
- Importance of this method
- Discrete values,Mean and Median
- Forward Fill
- Backward Fill


`@script`
Here's what we have covered so far.


---
## Let's try out this method!

```yaml
type: "FinalSlide"
key: "2d76ebda8c"
```

`@script`
Now, it's your turn to get your hands dirty with the code. Let's try out this method with all its attributes.

