# Financial Times
# Excess mortality during the Covid-19 pandemic

This repository contains excess mortality data for the period covering the 2020 Covid-19 pandemic. The data has been gathered from [national, regional or municipal agencies](#sources) that collect death registrations and publish official mortality statistics. These original data were reshaped into a standardised format by Financial Times journalists to allow cross-national comparisons, and have been used to inform the [FT’s reporting on the pandemic](#stories).

The repository contains the excess mortality data for all known jurisdictions which publish all-cause mortality data meeting the following criteria:

* daily, weekly or monthly level of granularity
* includes equivalent historical data for at least one full year before 2020, and preferably at least five years (2015-2019)
* includes data up to at least April 1, 2020

Most countries publish mortality data with a longer periodicity (typically quarterly or even annually), a longer publication lag time, or both. This sort of data is not suitable for ongoing analysis during an epidemic and is therefore not included here.

## Data

All of the data can be found in the file [data/ft_excess_deaths.csv](https://github.com/Financial-Times/coronavirus-excess-mortality-data/blob/master/data/ft_excess_deaths.csv).

## Data definitions

For each jurisdiction and each weekly or monthly period, the data contains the following fields:

* `country`: the country to which the data applies
* `region`: where applicable, the subnational or administrative region. This duplicated `country` for national-level data
* `period`: the period for which the data is collected. This can be “week” or “month”; data reported daily has been aggregated into weeks
* `year`: the year within which the period ends. The is the same as the year element of the `date` field.
* `month`: the month within which the period ends. This is the same as the month element of the `date` field.
* `week`: week number is either taken exactly from countries’ own data, or is calculated using the following method: for countries reporting daily data, we take the most recent run of seven days in the data to be the most recent week, and then aggregate each prior seven-day run into a new week, with any trailing period fewer than seven days at start of January clipped off
* `date`: the date at which the week ends
* `deaths`: historical daily, weekly or monthly numbers of all-cause deaths for as far back as we have been able to obtain this data
* `expected_deaths`: the median value of this data for the equivalent period in years from 2015 to 2019
* `excess_deaths`: difference between `deaths` and `expected deaths` (negative values indiciate fewer deaths than the recent historical average)
* `excess_deaths_pct`: `excess_deaths` as a percentage of `expected_deaths`

## Stories

"Excess mortality" refers to the difference between deaths from all causes during the pandemic and the historic seasonal average. For many of the jurisdictions shown here, this figure is higher than the official Covid-19 fatalities that are published by national governments each day. While not all of these deaths are necessarily attributable to the disease, it does leave a number of unexplained deaths that suggests that the official figures of deaths attributed may significant undercounts of the pandemic's impact.

The data published here were used to inform the following Financial Times stories and graphics:

* Ongoing: [Coronavirus tracked: the latest figures as countries fight to contain the pandemic](https://www.ft.com/content/a26fbf7e-48f8-11ea-aeb3-955839e06441)
* June 2, 2020: [UK excess deaths during pandemic reach 62,000](https://www.ft.com/content/3c53ab12-d859-4ceb-b262-f6a0221ca129)
* June 2, 2020: [Scotland’s coronavirus record flattered by contrasts with south](https://www.ft.com/content/a3fe315f-610a-4086-a6bc-a466a7f33aa1)
* May 28, 2020: [UK suffers highest death rate from coronavirus](https://www.ft.com/content/6b4c784e-c259-4ca4-9a82-648ffde71bf0)
* May 19, 2020: [UK deaths since virus struck almost 55,000 above average, says ONS](https://www.ft.com/content/f6a11fcd-0445-4643-9d3c-24d5fc0611da)
* May 11, 2020: [Russia's Covid death toll could be 70 per cent higher than official figure](https://www.ft.com/content/77cd2cba-b0e2-4022-a265-e0a9a7930bda)
* May 5, 2020: [Turkey's virus deaths may be 25 per cent higher than official figure](https://www.ft.com/content/80bb222c-b6eb-40ea-8014-563cbe9e0117)
* April 28, 2020: [Low Covid-19 death toll raises hopes Africa may be spared worst](https://www.ft.com/content/e9cf5ed0-a590-4bd6-8c00-b41d0c4ae6e0)
* April 26, 2020: [Global coronavirus death toll could be 60% higher than reported](https://www.ft.com/content/6bd88b7d-3386-4543-b2e9-0d5c6fac846c)
* April 22, 2020: [UK coronavirus deaths more than double official figure, according to FT study](https://www.ft.com/content/67e6a4ee-3d05-43bc-ba03-e239799fa6ab)

This data has also been used in the reporting news stories from other publications:

* *El País,* June 6 2020: [España es el país con el segundo mayor exceso de muertes durante la crisis del coronavirus](https://elpais.com/sociedad/2020-06-05/espana-es-el-pais-con-el-segundo-mayor-exceso-de-muertes-durante-la-crisis-del-coronavirus.html)

This data has been used in the the following academic publications:

* Dergiades, Theologos and Milas, Costas and Mossialos, Elias and Panagiotidis, Theodore, Effectiveness of Government Policies in Response to the COVID-19 Outbreak (May 15, 2020). Available at SSRN: [https://ssrn.com/abstract=3602004](https://ssrn.com/abstract=3602004) or [http://dx.doi.org/10.2139/ssrn.3602004](http://dx.doi.org/10.2139/ssrn.3602004)

## Sources

The data published here has been gathered and standardised from [official sources](sources.md). Full details can be found [here](sources.md).

## License and attribution

This software is published by the Financial Times under the [MIT license](https://opensource.org/licenses/MIT). 

The collected data in the `data` directory of this repository is available under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

If you use this data, you must attribute it to "Financial Times" as well as the relevant originating agency or agencies listed above. If it is published online, we would appreciate a link to our [Coronavirus tracker page](https://www.ft.com/content/a26fbf7e-48f8-11ea-aeb3-955839e06441), where this material first appeared.

Please let us know if you are using this data by contacting us at [coronavirus-data@ft.com](mailto:cornoavirus-data@ft.com). We may be interested in reporting on your work.

Please note that MIT licence includes only the software, and the Creative Commons licence includes only the data included in this repository. Neither cover any FT content created and made available using the software or data, which is copyright © The Financial Times Limited, all rights reserved. For more information about re-publishing FT content, please contact our [syndication department](https://enterprise.ft.com/en-gb/services/republishing/).

## Contributors

Work on this project is led by [John Burn-Murdoch](https://www.ft.com/stream/e191658e-c66a-45bc-9bad-343bdc4210b3) of the [FT Visual & Data Journalism team](https://www.ft.com/visual-and-data-journalism).

Additional contributors include [Chris Giles](https://www.ft.com/chris-giles), [Valentina Romei](https://www.ft.com/valentina-romei), [Henry Foy](https://www.ft.com/henry-foy) [David Pilling](https://www.ft.com/david-pilling), [Laura Pitel](https://www.ft.com/laura-pitel), [Martin Stabe](https://www.ft.com/martin-stabe) and [Aleksandra Wisniewska](https://www.ft.com/aleksandra-wisniewska).

To contact the team, please email [coronavirus-data@ft.com](mailto:cornoavirus-data@ft.com).

## Related projects

Similar work is being done by [The Economist](https://github.com/TheEconomist/covid-19-excess-deaths-tracker), the [New York Times](https://github.com/nytimes/covid-19-data/tree/master/excess-deaths), [Our World in Data](https://github.com/owid/covid-19-data/tree/master/public/data) and [Newsworthy](https://gitlab.com/newsworthy/jpp.2005.excess.deaths.data).

## How you can help

If you are aware of a jurisdiction not already [listed here](https://github.com/Financial-Times/coronavirus-excess-mortality-data/blob/master/sources.md) which publishes all-cause mortality data that meets the criteria set out above, please send us a link to the source of that data at [coronavirus-data@ft.com](mailto:cornoavirus-data@ft.com).

Alternatively, please submit a pull request to this repository adding the relevant information to the file [sources.md](https://github.com/Financial-Times/coronavirus-excess-mortality-data/blob/master/sources.md).