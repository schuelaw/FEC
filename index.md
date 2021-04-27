## Federal Election Commission (FEC)

Its mission statement as given on the [commission website](https://www.fec.gov/) is: *The FEC was
created to promote confidence and participation in the democratic process.*

### FEC Data

As part of that mission, the FEC collects data about contributions to all candidates in federal elections. Here we explore the FEC data on individual contributions to Joe Biden and Donald Trump during the two year period from Jan 1, 2019 through Dec 31, 2020. That data is available for download from the FEC's [bulk data page](https://www.fec.gov/data/browse-data/?tab=bulk-data).

The "[Contributions by individuals 2019-2020](https://www.fec.gov/files/bulk-downloads/2020/indiv20.zip)" is the primary data source for the analyses presented here.

### Challenges with FEC Data

There are several challenges to overcome when working with this data. We summarize them here.

* The uncompressed individual contributions dataset is around 18Gb. We use python with pandas to process this dataset, but it must be done in chunks as our available computing power is not capable of loading the entire dataset at once.

* The individual contributions are linked to "Committee IDs". One must refer to the separate "Candidate-committee linkages" dataset to link Committee IDs to Candidate IDs. Then, one must refer to the "Candidate Master" to link candidate names to Candidate IDs. Through this chain, we were able to identify individual contributions to Biden and Trump.

* The [WinRed](https://winred.com/) problem. WinRed is a centralized fundraising aggregator for Republican candidates nationwide. Individual contributors can go to the WinRed site and donate to any Republican candidate. WinRed then transfers those donations to the designated candidate's official committee. 

  When it reports to the FEC, WinRed doesn't disaggregate the individual contributions so they appear as several multi-million dollar contributions. 

  Fortunately, for this project, the non-profit, investigative journalism organization, [ProPublica](https://www.propublica.org/), has mined WinRed's public reports and disaggregated those contributions back to individual donors. The disaggregated data is by state, so some work is necessary to download and merge the data into a single national dataset like the FEC data. (get [ProPublica year-end WinRed data](https://projects.propublica.org/itemizer/committee/C00694323/2020))

* Multiple Committee IDs in the FEC are associated with both Biden and Trump. To determine which Committee IDs are associated with which candidate, we found a list of the top funded Committee IDs and looked at the Committee Names to determine whether they supported Biden or Trump.




