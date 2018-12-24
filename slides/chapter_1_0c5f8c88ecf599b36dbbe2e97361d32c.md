---
title: Insert title here
key: 0c5f8c88ecf599b36dbbe2e97361d32c

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



---
## Fillna() method

```yaml
type: "TwoRows"
key: "b581267353"
```

`@part1`
- is used when data in considerable amount of rows is missing.


`@part2`
```Python
>> Import pandas as pd
>> 
```


`@script`



---
## Forward and Backward Fill

```yaml
type: "TwoRowsTwoColumns"
key: "8cdf1116c1"
```

`@part1`
- if a previous value is not available during a forward fill, or backward fill the NA value remains.


`@part2`
|Date|A|B|
|---|---|---|
|01-01-2017|||
|01-01-2017 |||
|01-01-2017 |0.18127718|-0.178835737|
|01-01-2017 | 0.186923018 |-0.183260853|
| 01-01-2017 | | |
| 01-01-2017 | | |


`@part3`
hello


`@part4`
he


`@script`
You just learned Forward and Backward fill. But what if you don't have any data in the previous row for forward fill and following row for backward fill. Look at this table. If data appears something like this. In such a scenario, you would use both forward and backward fill attributes as shown in the code.


---
## Let's try out this method!

```yaml
type: "FinalSlide"
key: "2d76ebda8c"
```

`@script`
Now, it's your turn to get your hands dirty with the code. Let's try out this method.

