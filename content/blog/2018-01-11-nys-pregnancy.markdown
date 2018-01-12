---
title: How many women in New York are pregnant right now?
author:
date: "2018-01-11"
slug: nys-pregnancy
draft: true
tags:
  - R
  - mapping
---

When I found out that J was pregnant, my first thought was OMG, I'm so excited to be a dad! My second(ish) thought was, I wonder how many other women in New York are also pregnant right now?

After a little googling, I found [this brief](https://www.cdc.gov/reproductivehealth/emergency/pdfs/PregnacyEstimatoBrochure508.pdf) from the CDC which details how to estimate the number of pregnant women in a geographic area. Bingo!

To calculate the number of pregnant women in a given area, you need to specify four parameters:

* Number of women of reproductive age [WRA] \(15 – 44 years old)
* Fertility rate (live births per 1,000 WRA)
* Abortion rate (induced abortions per 1,000 WRA)
* Fetal loss rate (fetal deaths per 1,000 WRA)





```r
library(tidyverse)
library(rvest)
library(sf)
library(tidycensus)
options(tigris_use_cache = TRUE)

ny_health <- "https://www.health.ny.gov/statistics/vital_statistics/2015/"

abort <- read_html(paste0(ny_health, "table21.htm"))
pop <- read_html(paste0(ny_health, "table01a.htm"))
birth <- read_html(paste0(ny_health, "table07.htm"))

read_nys_xml_table <- function(x) {
  html_nodes(x, "table") %>%
    html_table(fill = TRUE) %>%
    as.data.frame() %>%
    as_tibble() %>%
    slice(-(c(1:5, 11:12)))
}

abortion <- read_nys_xml_table(abort) %>%
  transmute(
    county = County,
    abortion_tot = as.integer(str_replace(Var.2, ",", ""))
    ) %>%
  filter(county != "Hamilton/Essex")
abortion
```

```
## # A tibble: 61 x 2
##    county      abortion_tot
##    <chr>              <int>
##  1 Bronx              14992
##  2 Kings              18026
##  3 New York           10294
##  4 Queens             13681
##  5 Richmond            1634
##  6 Albany              1139
##  7 Allegany              36
##  8 Broome               690
##  9 Cattaraugus           79
## 10 Cayuga               139
## # ... with 51 more rows
```

