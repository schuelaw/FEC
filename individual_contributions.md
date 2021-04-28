### Individual Contributions

#### Data Preparation
There are three kinds of individual contributions in the data: Biden,
Trump, and other. To classify each contribution, we take the following
steps.

* `Extract CMTE\_ID` and `TRANSACTION\_AMT` from the full dataset. The
  `TRANSACTION\_AMT` is of mixed type so we convert it to numeric using the
  `.to_numeric()` pandas function with `errors='coerce'` which substitutes
  `NaN` for column data that is not able to be converted to a numerical
  value, e.g. strings. Noting that there were few `NaN` values, we dropped
  these records. (How many?)

* We group the 

