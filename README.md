# Using-Big-Data-Mining-Method-on-Online-News-from-GDELT-to-Understand-the-Russo-Ukrainian-War

The Russo-Ukrainian War has existed since 2014. Global news outlets have continued to report on the re-escalation in early 2022 as Russia invaded Ukraine. However, the intervening years was given less attention by source documents even if the war did not stop between 2015 and 2021, leading journalists to call it the "forgotten war." In this report, we use a novel application of itemset mining to surface frequent event patterns among geopolitical events concurrent to the Russo-Ukrainian War. By using big data available from news sources, we aim to identify trends in global sentiment and extract frequently occurring geopolitical events between Russia, Ukraine, and other major players, to further understand the Russo-Ukrainian tensions in the intervening years.

## Methods

We used the Global Database of Events, Language and Tone (GDELT) dataset available at the AWS Registry of Open Data and Google BigQuery. Limiting the scope to years 2013 to 2022 only, we accessed the dataset by initializing the necessary instances and machines on Google Cloud Platform and AWS and connecting to the appropriate bucket. We then converted the RDD into Spark DataFrames for convenient manipulation and preprocessing. The resulting file was saved in Parquet format, where relevant tables and results were filtered and processed using Spark SQL and Spark ML's FPGrowth library. A minimum support of 0.001 and a confidence of 0.3 were used to generate the frequent itemsets and its corresponding association rules. Python 3 was used to generate selected visualizations.

## Results

Salient results from our analysis include the following:

- Frequently mentioned actors are mostly Presidents from major superpowers, such as the UK, the US, China, Russia, and Ukraine. Neither then-US President Donald Trump nor Ukrainian President Volodymyr Zelenskyy are included in the list of frequently mentioned actors.

- The average tone of documents about Western world leaders is far more negative than that of their Eastern counterparts. 

- Highly mentioned events in the Russo-Ukrainian War are related to escalation events. However, the years 2015 to 2021 yielded very limited attention from source documents even if the war continued in these years.

- Ukraine appears to be more prone to destabilization than Russia. This could be due to the latter's geopolitical and economic power. Towards early March 2022, however, it appeared that recent sanctions have negatively impacted Russia much more than Ukraine.

- In mining the frequently occurring events and association rules, we saw no indication of Russia's interest in annexation of Crimea before the war. However, when it started in 2014, it was only the US who actively sanctioned and imposed embargoes on Russia. There was a period of relative silence from 2015 to 2021, and global attention increased at the re-escalation in 2022 given the invasion by and economic sanctions against Russia.

## Conclusion and Recommendations

We described the global sentiment and mined for frequently occurring events concurrent to the Russo-Ukrainian War and its corresponding association rules. We suggest conducting further research to validate our findings against the historical context pre-2013. Future research may extend our report by sequence-aware pattern mining to fully understand the nuances between the dynamics of actors, including repeating and/or sequential patterns of certain actors.
