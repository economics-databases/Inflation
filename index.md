## Inflation, consumer prices (annual %)

* Inflation as measured by the consumer price index reflects the annual percentage change in the cost to the average consumer of acquiring a basket of goods and services that may be fixed or changed at specified intervals, such as yearly. The Laspeyres formula is generally used.

* Periodicity: Annual

* Source: [World Bank](https://data.worldbank.org)

     [CSV](https://github.com/economics-databases/Inflation/blob/gh-pages/CPI_PCT_A.csv)


### R CODE

*Installed Packages*

```{r}
install.packages("wbstats")
install.packages("WDI")
library(wbstats)
new_wb_cache <- wbcache() 
library(WDI)
new_wdi_cache <- WDIcache() 
```

*Inflation, consumer prices (annual %) DATA QUERY*

```{r}
CPI_PCT_A<-WDI(indicator = c("FP.CPI.TOTL.ZG"))
names(CPI_PCT_A)[1] <- "ISO"
names(CPI_PCT_A)[2] <- "COUNTRY"
names(CPI_PCT_A)[3] <- "VALUE"
names(CPI_PCT_A)[4] <- "YEAR"
write.csv(CPI_PCT_A,file="CPI_PCT_A.csv")
```

*In order to have a time series for one country only, the following R code allows you to select a sub-section of the main table*

- *zzz* represents the ISO code of the country for which you want to have a unique table

```{r}
country_dataset <- CPI_PCT_A[ which(CPI_PCT_A$ISO=='zzz'),]
```


