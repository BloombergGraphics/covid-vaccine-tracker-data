# Bloomberg Covid-19 Vaccine Tracker Open Data

## Terms of Use

By downloading the Dataset, you agree that you will attribute the Dataset and any use of the Dataset to Bloomberg. You may use the Dataset for personal or internal business purposes, and may make limited use of the Dataset in connection with the provision of other services to clients; provided that you may not monetize the Dataset or otherwise make commercial use of the Dataset where the Dataset constitutes all, or substantially all, of the commercial offering. The Dataset is provided “as-is” and without any express or implied warranties.

## Dataset Description

[The Bloomberg Covid-19 Vaccine Tracker](https://www.bloomberg.com/graphics/covid-vaccine-tracker-global-distribution/) covers all U.S. states and territories as well as a growing number of countries internationally, on a daily basis. Vaccination data is gathered from government websites, official statements and Bloomberg interviews. In the U.S., when local governments and the Centers for Disease Control and Prevention report different totals for the same jurisdiction, Bloomberg uses the higher number (unless there is a data quality concern). It may take several days for counts to be reported to databases. We don’t report data from third-party sources, except in a few rare cases such as state-affiliated media.

## Updating

The latest raw data will be pushed to this repository once a day.

The file [UPDATED.txt](data/UPDATED.txt) indicates the time at which the data was last acquired from our data store.

## Data Dictionary

These comma-separated values (CSV) files are available for download, with the following data fields.

[current-global.csv](data/current-global.csv) – Snapshot of the latest global update to the Bloomberg Covid-19 Vaccine Tracker

* `id`: ISO 3166-1 alpha-3 country code (full list available [here](https://unstats.un.org/unsd/tradekb/knowledgebase/country-code)). Subdivisions are also standard ISO codes (ISO 3166-2 alpha-2 or alpha-3), unless otherwise specified. London’s (GBR-LON) is a non-standard code.
* `population`: 2019 national population figure from the International Monetary Fund [October 2020 World Economic Outlook](https://www.imf.org/en/Publications/WEO/weo-database/2020/October).
* `name`: Jurisdiction name in Bloomberg style.
* `dosesAdministered`: Cumulative number of vaccine doses administered.
* `peopleVaccinated`: Cumulative number of people who’ve received at least one dose.
* `completedVaccination`: Cumulative number of people who’ve been fully vaccinated (note: the first-approved vaccines require two doses for full vaccination or “series completion”, later vaccines may require only one dose).

[current-usa.csv](data/current-usa.csv) – Snapshot of the latest U.S. update to the Bloomberg Covid-19 Vaccine Tracker

* `id`: Postal abbreviations for states, territories and vaccination jurisdictions (full list available [here](https://faq.usps.com/s/article/What-are-the-USPS-abbreviations-for-U-S-states-and-territories)). Cities and federal entities are given non-standard identifiers, e.g. “new-york-city”.
* `population`: Population estimates as of July 1, 2019 from the [U.S. Census](https://www.census.gov/data/tables/time-series/demo/popest/2010s-state-total.html) for the U.S. and Puerto Rico. 2018 U.S. Census Bureau estimates and estimates from the CIA Factbook are used for other U.S. territories and Micronesia, Palau and the Marshall Islands.
* `name`: State, territory, city or vaccination jurisdiction name.
* `dosesAdministered`: Cumulative number of doses administered. This is the administration data published on our website. It includes the most up-to-date figures drawn from the CDC and from state-run dashboards—whichever value is higher. 
* `peopleVaccinated`: Cumulative number of people who’ve received at least one dose. (Note: if higher than the CDC number, state-reported data is used.)
* `completedVaccination`: Cumulative number of people who’ve been fully vaccinated. (Notes: if higher than the CDC number, state-reported data is used, and the first-approved vaccines require two doses for full vaccination or “series completion”.)
* `cdcDosesDistributed`: Cumulative number of vaccine doses delivered, according to the CDC.
* `cdcDosesAdministered`: Cumulative number of doses administered, as reported by the CDC. (Note: CDC data is delayed for some states. For the most up-to-date data, use `dosesAdministered`)
* `stateReportedDosesAdministered`: Cumulative number of doses administered, as reported by states. (Note: we do not collect this figure for every state; for the most comprehensive data, use `dosesAdministered`.)

[historical-global-doses-administered.csv](data/historical-global-doses-administered.csv) – Cumulative number of doses administered by country

* `id`: ISO 3166-1 alpha-3 country code (full list available [here](https://unstats.un.org/unsd/tradekb/knowledgebase/country-code)). Subdivisions are also standard ISO codes (ISO 3166-2 alpha-2 or alpha-3), unless otherwise specified. London’s (GBR-LON) is a non-standard code.
* `date`: Date on which new datapoint was recorded by Bloomberg. (Note: all areas are checked daily, but depending on when the source is updated it may have been recorded with a day or more of lag.)
* `value`: total number of doses administered (e.g. `dosesAdministered`) as recorded on that date.

[historical-usa-doses-administered.csv](data/historical-usa-doses-administered.csv) – Cumulative number of doses administered by U.S. states, territories or other vaccination jurisdictions

* `id`: Postal abbreviations for states, territories and vaccination jurisdictions (full list available [here](https://faq.usps.com/s/article/What-are-the-USPS-abbreviations-for-U-S-states-and-territories)). Cities and federal entities are given non-standard identifiers, e.g. “new-york-city”.
* `date`: Date on which new datapoint was recorded by Bloomberg. (Note: all areas are checked daily, but depending on when the source is updated it may have been recorded with a day or more of lag.)
* `value`: Total number of doses administered (e.g. `dosesAdministered`) as recorded on that date

## Country Notes

* Brazil: Data covers most but not all states, as explained in this [blog post](https://www.bloomberg.com/news/live-blog/2021-01-21/methodology-and-analysis-for-the-covid-19-vaccine-tracker#6012F60FB2240001).
* Canada: National figures are calculated as the sum of province and territory level data, rather than directly reported.
* Russia: Only reports the number of people who have received at least one dose; it doesn’t break down the total number of doses administered, which would be higher.
* U.K.: National figures are calculated as the sum of country-level data, rather than directly reported. Crown dependencies and British Overseas Territories are excluded from U.K.’s total.
* U.S.: National figures are calculated as the sum of states, the District of Columbia, territories, federal agencies and the Pacific Island nations that are covered by the U.S. vaccination drive (Marshall Islands, Micronesia, Palau), rather than directly reported.
