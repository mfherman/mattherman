+++
title = "Projects"
+++

## Westchester Covid-19 Tracking

I built a [website that tracks the state of the Covid-19 in Westchester County, NY](https://westchester-covid.mattherman.info/) and the surrounding metropolitan area. It augments and improves upon various dashboards created by New York State and Westchester County by pulling in data from multiple sources and displaying them in an easy to understand format with additional context. The site includes maps, charts, and tables highlighting cases, testing, and fatality trends by county; per capita case counts and trends at the municipal-level; racial disparities in Covid-19 deaths and cases; cases in schools and nursing homes; and hospital capacity. It is automatically updated a couple times a day as new data is released by New York State and Westchester County.

The site is built using the [Distill framework for R Markdown](https://rstudio.github.io/distill/). All data collection and aggregation is done using R. Source code for downloading and aggregating the data as well as building the website is available on [GitHub](https://github.com/mfherman/westchester-covid).  

## `nycgeo`: An R package to get spatial data and census estimates for NYC

The [`nycgeo` package](https://nycgeo.mattherman.info) <a href = "https://nycgeo.mattherman.info"><img class="special-img-class" src="/img/nycgeo.png" width = "152px" align ="right"/></a>contains spatial data files for various geographic and administrative boundaries in New York City as well as tools for working with NYC geographic data. Data is in the [`sf` (simple features)](https://r-spatial.github.io/sf/) format and includes boundaries for boroughs (counties), public use microdata areas (PUMAs), community districts (CDs), neighborhood tabulation areas (NTAs), census tracts, and census blocks. In the future, more boundaries will be added, such as city council districts, school districts, and police precincts.

Additionally, selected demographic, social, and economic estimates from the U.S. Census Bureau American Community Survey can be added to the geographic boundaries in `nycgeo`, allowing for contextualization and easy choropleth mapping. Finally, `nycgeo` makes it simple to access a subset of spatial data in a particular geographic area, such as all census tracts in Brooklyn and Queens.

`nycgeo` is hosted on GitHub and can be downloaded here: https://github.com/mfherman/nycgeo.

## Predicting shelter entry using natural language processing of homebase case notes

In collaboration with the [Center for Innovation through Data Intelligence](http://www1.nyc.gov/site/cidi/about/about.page) and the NYC Department of Homeless Services, this project used Natural Language Processing of homelessness prevention case notes to predict an individual's risk of shelter entry. Specifically, the study investigated the ways unstructured case notes can be used to learn more about individuals using Homebase homelessness prevention services in New York City. Are there words, phrases, or topics that occur more frequently in the unstructured case notes of individuals who enter shelter after using Homebase services as compared to those who do not? And can a predictive model that assesses the probability of shelter entry based on structured data be improved by incorporating insights from unstructured case notes?

## The subway as fourth place: anomie, flânerie and the "crush of persons"

As part of research practicum course at Hunter in Fall 2016, we conceived and conducted a mixed methods research project to assess social behavior and interaction on the New York City subway. We collected more than 4,000 detailed observations of passenger behavior as well as in-depth "subway diaries" from eighteen research participants. Using logistic regression, we modeled the factors that influence how passengers direct their gaze and configure their bodies while riding the subway. The diaries helped us interpret and understand the observations.

The results of the study have been published in the peer-reviewed journal, [Applied Mobilties](/pdf/subway.pdf). The research was also covered by the [Daily News](http://www.nydailynews.com/new-york/nyc-subways-plagued-disorderly-exits-manspreading-study-article-1.2626553) and [CBS New York](http://newyork.cbslocal.com/2016/05/05/hunter-college-subway-study/).