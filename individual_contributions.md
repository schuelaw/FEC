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
	* FEC:

	  Committee | Earnings (USD, millions)
          ----------|-------------------------
	  C00401224 ActBlue | 2251.685
	  C00694323 WinRed  | 1750.385
	  C00728154 MIKE BLOOMBERG 2020, INC.| 1089.290
	  C00703975 BIDEN FOR PRESIDENT| 520.8530
	  C00744946 BIDEN VICTORY FUND | 503.1774
	  C00571703 SENATE LEADERSHIP FUND  | 410.9035
	  C00618389 TRUMP VICTORY | 367.7576
	  C00552851 HOUSE FREEDOM FUND | 355.5769
	  C00618371 TRUMP MAKE AMERICA GREAT AGAIN COMMITTEE| 344.8636
	  C00711614 TOM STEYER 2020 | 319.4558
	  C00484642 SMP | 260.2297
	  C00580100 MAKE AMERICA GREAT AGAIN PAC | 250.3264
	  C00003418 REPUBLICAN NATIONAL COMMITTEE  | 245.2835
	  C00027466 NRSC | 169.6495
	  C00042366 DSCC | 162.2674

	* WinRed:

	  Committee                                                                              |Earnings (USD, millions)
	  ---------------------------------------------------------------------------------------|------------------------
	  Earmarked for TRUMP MAKE AMERICA GREAT AGAIN COMMITTEE (C00618371)                     |      103.825 
	  Refund of Earmarked Contribution                                                       |      -38.9842 
	  Earmarked for DONALD J. TRUMP FOR PRESIDENT, INC. (C00580100)                          |      33.0368 
	  Earmarked for GEORGIANS FOR KELLY LOEFFLER (C00729608)                                 |      32.1226 
	  Earmarked for PERDUE FOR SENATE (C00547570)                                            |      29.3174 
	  Earmarked for NRSC (C00027466)                                                         |      24.7305 
	  Earmarked for REPUBLICAN NATIONAL COMMITTEE (C00003418)                                |      16.7951 
	  Earmarked for NRCC (C00075820)                                                         |      14.5478 
	  Earmarked for SENATE GEORGIA BATTLEGROUND FUND (C00736967)                             |      12.7943 
	  Earmarked for MCCONNELL SENATE COMMITTEE (C00193342)                                   |      6.48096 
	  Earmarked for ELISE FOR CONGRESS (C00547893)                                           |      2.37567 
	  Earmarked for NATIONAL VICTORY ACTION FUND (C00760124)                                 |      2.10694 
	  Earmarked for KEVIN MCCARTHY FOR CONGRESS (C00420935)                                  |      1.30704 
