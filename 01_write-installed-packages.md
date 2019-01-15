01\_write-installed-packages.R
================
jenny
Mon Jan 14 23:45:08 2019

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────── tidyverse 1.2.1 ──

    ## ✔ ggplot2 3.1.0          ✔ purrr   0.2.5     
    ## ✔ tibble  2.0.0          ✔ dplyr   0.8.0.9000
    ## ✔ tidyr   0.8.2          ✔ stringr 1.3.1     
    ## ✔ readr   1.3.1          ✔ forcats 0.3.0

    ## ── Conflicts ───────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(here)
```

    ## here() starts at /Users/jenny/tmp/sassy-hamster

``` r
ipt <- installed.packages() %>%
  as_tibble() %>%
  select(Package, LibPath, Version, Priority, Built) %>%
  write_csv(path = here("data", "installed-packages.csv"))

ipt
```

    ## # A tibble: 428 x 5
    ##    Package    LibPath                          Version Priority Built
    ##    <chr>      <chr>                            <chr>   <chr>    <chr>
    ##  1 abind      /Users/jenny/resources/R/library 1.4-5   <NA>     3.5.0
    ##  2 acepack    /Users/jenny/resources/R/library 1.4.1   <NA>     3.5.0
    ##  3 AER        /Users/jenny/resources/R/library 1.2-5   <NA>     3.5.0
    ##  4 akima      /Users/jenny/resources/R/library 0.6-2   <NA>     3.5.0
    ##  5 anytime    /Users/jenny/resources/R/library 0.3.2   <NA>     3.5.0
    ##  6 assertthat /Users/jenny/resources/R/library 0.2.0   <NA>     3.5.0
    ##  7 AUC        /Users/jenny/resources/R/library 0.3.0   <NA>     3.5.0
    ##  8 audio      /Users/jenny/resources/R/library 0.1-5.1 <NA>     3.5.0
    ##  9 backports  /Users/jenny/resources/R/library 1.1.3   <NA>     3.5.0
    ## 10 base64enc  /Users/jenny/resources/R/library 0.1-3   <NA>     3.5.0
    ## # … with 418 more rows
