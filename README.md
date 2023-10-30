EDAV Community Contribution:

# References and some remarks:

-   [**Blom 1958:**](https://gwern.net/doc/statistics/order/1958-blom-orderstatistics.pdf) Original paper discovering the 9th quantile type, i.e., $\frac{i-3/8}{n+1/4}$, and providing arguments about its efficacy (unbiased) for an underlying Normal distribution.
-   [**Hyndman and Fan, 1996:**](https://www.amherst.edu/media/view/129116/original/Sample+Quantiles.pdf) Original paper outlining the 9 types of quantile estimators used in packages (at the time and still today).
-   [**Ggplot2 qq_line source code**](https://github.com/tidyverse/ggplot2/blob/HEAD/R/stat-qq-line.R): The QQ-line is effectively generated in lines 78ff and we see that by default it is simply a line through the 25% and 75% sample quantile of the data.
-   [**Ggplot2 qq_geom source code**](https://github.com/tidyverse/ggplot2/blob/5a61e2e656d61469e5ae7e2ffa29fd755d9c1b71/R/stat-qq.R): In line 96, we see that the quantiles in ggplot's QQ-plot are chosen from the ppoints function (whose default type is 9).
-   Description of [**ppoint**](https://www.rdocumentation.org/packages/stats/versions/3.6.2/topics/ppoints) function. This is effectively a simplified version of the type selection, by providing an option to change the offset in $\frac{i-a}{n+1-2a}$ (this of course does not allow for specifying locally constant functions such as types 1,2 and 3).
-   Base R [**quantile**](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/quantile.html) functions and a short description of the types based on the Hyndman-Fan paper.
-   Base R [**qqnorm**](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/qqnorm.html) description; for qqline we can pick type and the quantiles through which the line is drawn, however, qqnorm uses by default type 9 and as far as I know, we cannot change to a different type.
