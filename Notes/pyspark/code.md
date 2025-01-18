```python
# Import your libraries
import pyspark
import pyspark.sql.functions as F
# Start writing code

# To validate your solution, convert your final pySpark df to a pandas df
google_salaries.groupBy(F.col("education")).agg(F.avg(F.col("salary"))												.alias("average_salary")).toPandas()

```