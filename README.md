
Welcome to the transportDataManchester repo
===========================================

<!-- README.md is generated from README.Rmd. Please edit that file -->
This is a package to ease the access and analysis of open transport data in Manchester. It comes pre-installed with some datasets and automatically installs some useful software for visualising spatial data on your computer.

Pre-requisites
--------------

Recent versions of R (which can be downloaded [here](https://www.r-project.org/)) and [RStudio](https://www.rstudio.com/products/rstudio/download/).

This is free software that works on Linux, Mac and Windows.

It is suggested you get up-to-speed with RStudio, for example with reference to this tutorial: <https://github.com/Robinlovelace/Creating-maps-in-R> (Lovelace et al. 2014)

Installation
------------

Open RStudio and enter the following, to install the 'devtools' package:

``` r
install.packages("devtools")
```

Then you can install this package:

``` r
devtools::install_github("robinlovelace/transportDataManchester")
```

Load it as follows:

``` r
library(transportDataManchester)
```

Using the package
-----------------

The package comes with a number of datasets pre-installed. To see them try:

``` r
data(package = "transportDataManchester")
```

To plot the cycle path data, for example, try the following:

``` r
library("tmap") # load mapping package
data("cycle_routes")
osm_tiles = read_osm(bb(cycle_routes))
cycle_routes$`Year opened` = as.character(cycle_routes$OpeningYea)
qtm(osm_tiles) +
  tm_shape(cycle_routes) +
  tm_lines(col = "Year opened", palette = "Spectral")
```

![](README-cycle_route_map-1.png)

Further data resources
----------------------

There are many open data resources available, in addition to the `cycle_routes` dataset included in the package:

Cycle data
----------

-   Data from the Propensity to Cycle Tool: <http://www.pct.bike/>

-   Cycle routes (this is where the `cycle_routes` dataset pre-installed in this package is from): <https://data.gov.uk/dataset/gm-cycle-routes>

-   Cycle hubs: <https://data.gov.uk/dataset/gm-cycle-hubs>

-   Cycle lockers: <https://data.gov.uk/dataset/gm-cycle-lockers>

-   Cycle parking: <https://data.gov.uk/dataset/gm-cycle-parking>

-   Bike shops: <https://data.gov.uk/dataset/cycle-shops>

### Other TfGM data

-   GM Traffic Signal Locations : <https://data.gov.uk/dataset/traffic-signal-locations>

-   Greater Manchester Road Casualty Statistics: <https://data.gov.uk/dataset/greater-manchester-road-casualty-statistics>

-   Metrolink Stops and Rail Stations: <https://data.gov.uk/dataset/metrolink-and-rail-stations>

-   GM Public Transport Schedule – GTFS: <https://data.gov.uk/dataset/public-transport-schedules-gtfs>

-   Car Parks - <http://developer.tfgm.com/> (requires registration) (also, note that this will be replaced by a new live system soon but the concept will be the same so can be used on a Proof of Concept basis)

### External data - Air Quality

-   Air Quality Management Areas - <https://uk-air.defra.gov.uk/aqma/maps>

-   Great Air Manchester - <http://www.greatairmanchester.org.uk/GreatAir/default.aspx>

-   Air Quality England - <http://www.airqualityengland.co.uk/>

References
----------

Lovelace, R., & Cheshire, J. (2014). Introduction to visualising spatial data in R.
