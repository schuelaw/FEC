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

* Find top earning committees in both the FEC and WinRed datasets.

	* WinRed:
	 +----------------------------------------------------------------------------------------+------------------+\n| memo_text                                                                              |           amount |\n+========================================================================================+==================+\n| Earmarked for TRUMP MAKE AMERICA GREAT AGAIN COMMITTEE (C00618371)                     |      1.03825e+08 |\n+----------------------------------------------------------------------------------------+------------------+\n| Refund of Earmarked Contribution                                                       |      3.89842e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for DONALD J. TRUMP FOR PRESIDENT, INC. (C00580100)                          |      3.30368e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for GEORGIANS FOR KELLY LOEFFLER (C00729608)                                 |      3.21226e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for PERDUE FOR SENATE (C00547570)                                            |      2.93174e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for NRSC (C00027466)                                                         |      2.47305e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for REPUBLICAN NATIONAL COMMITTEE (C00003418)                                |      1.67951e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for NRCC (C00075820)                                                         |      1.45478e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for SENATE GEORGIA BATTLEGROUND FUND (C00736967)                             |      1.27943e+07 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for MCCONNELL SENATE COMMITTEE (C00193342)                                   |      6.48096e+06 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for ELISE FOR CONGRESS (C00547893)                                           |      2.37567e+06 |\n+----------------------------------------------------------------------------------------+------------------+\n| Earmarked for NATIONAL VICTORY ACTION FUND (C00760124)                                 |      2.10694e+06 |\ 

