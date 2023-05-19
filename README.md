# pandas_demo
For pandas demonstration

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/jscheah/pandas_demo/main?labpath=introduction_to_pandas.ipynb)

```python
import pandas as pd

data = {'Name': ['John', 'Jane', 'Alice'],
        'Age': [25, 30, 28],
        'Salary': [50000, 60000, 55000]}

df = pd.DataFrame(data)

memory_usage = df.memory_usage(deep=True).sum()
print("Memory usage of the DataFrame:", memory_usage, "bytes")

```



The memory usage estimation provided by Pandas' `info()` method is based on the data types of the columns in the DataFrame. It calculates the memory required for storing the column data and any additional overhead required by Pandas to manage the DataFrame.

Here are some general guidelines for estimating memory usage based on data types:

- Numeric data types (e.g., int, float): The memory usage depends on the size of the data type. For example, an int64 column will use 8 bytes per element, and a float64 column will use 8 bytes per element.

- Boolean data type (bool): The memory usage for boolean columns is estimated as 1 byte per 8 elements. Each boolean element occupies a single bit, but Pandas rounds it up to the nearest byte for efficiency.

- String data type (object): The memory usage for string columns is estimated based on the actual content of the strings. It calculates the total memory required for storing the strings, including the string lengths and any additional overhead for managing the strings.

Keep in mind that these estimates are based on the assumption that the data types accurately represent the actual data in the DataFrame. If the data types are not optimized or if there are missing values, the memory usage estimate may not be entirely precise.

Additionally, the memory usage estimation may not account for certain optimizations or compression techniques used by Pandas, such as string interning or category data types. These techniques can reduce the memory usage compared to the naive estimates based solely on data types.

For a more precise measurement, you can use the `memory_usage()` method with the `deep=True` argument, as shown in the previous examples. This will provide the actual memory usage by recursively examining the contents of the DataFrame, but it requires creating the DataFrame and accessing its data.

## Combining DataFrames
Merge vs Join vs Concatenate

## Aggregation

## Merge
Pandas merge vs sql join
