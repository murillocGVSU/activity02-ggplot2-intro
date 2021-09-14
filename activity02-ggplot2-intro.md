Activity 2.1
================
Cleyde Murillo Jr

## Data and packages

``` r
library(palmerpenguins)
penguins
```

    ## # A tibble: 344 x 8
    ##    species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
    ##    <fct>   <fct>              <dbl>         <dbl>             <int>       <int>
    ##  1 Adelie  Torgersen           39.1          18.7               181        3750
    ##  2 Adelie  Torgersen           39.5          17.4               186        3800
    ##  3 Adelie  Torgersen           40.3          18                 195        3250
    ##  4 Adelie  Torgersen           NA            NA                  NA          NA
    ##  5 Adelie  Torgersen           36.7          19.3               193        3450
    ##  6 Adelie  Torgersen           39.3          20.6               190        3650
    ##  7 Adelie  Torgersen           38.9          17.8               181        3625
    ##  8 Adelie  Torgersen           39.2          19.6               195        4675
    ##  9 Adelie  Torgersen           34.1          18.1               193        3475
    ## 10 Adelie  Torgersen           42            20.2               190        4250
    ## # … with 334 more rows, and 2 more variables: sex <fct>, year <int>

``` r
library(ggplot2)
```

``` r
ggplot(data = penguins, mapping = aes(x = flipper_length_mm, y = species)) +
  geom_boxplot()
```

    ## Warning: Removed 2 rows containing non-finite values (stat_boxplot).

![](activity02-ggplot2-intro_files/figure-gfm/boxplots-no-color-1.png)<!-- -->

``` r
ggplot(data = penguins, mapping = aes(x = flipper_length_mm, y = species, fill = species)) +
  geom_boxplot()
```

    ## Warning: Removed 2 rows containing non-finite values (stat_boxplot).

![](activity02-ggplot2-intro_files/figure-gfm/boxplot-colors-1.png)<!-- -->

Now, comment on what you notice from these boxplots.

**The Gentoo species of penguin has the highest median flipper length.
Whereas the Adelie species has the smallest flipper length on average**:

``` r
ggplot(data = penguins, mapping = aes(x = flipper_length_mm, y = species, color = species )) +
  geom_jitter()
```

    ## Warning: Removed 2 rows containing missing values (geom_point).

![](activity02-ggplot2-intro_files/figure-gfm/jitterplot-1.png)<!-- -->

Comment on the strengths of the boxplot compared to the jitterplot and
vice versa. That is, what can you easily determine by looking at the
boxplot? What about the jitterplot?

**The scatter plot shows each penguin on the individual level much more
efficiently. We are able to see each groups scatter as opposed as to the
box plot where it is limited by group metrics.**:

Knit, stage, commit (with a meaningful commit message),and push
everything in your **Git** pane to your GitHub repo. Then, go to GitHub
and compare/contrast your `activity02-ggplot2-intro.Rmd` and
`activity02-ggplot2-intro.md` files. Which is easier to read? Which
looks more professional?

**The knitted file looks much more presentable in a report like
format.**:

Now, wouldn’t it be nice if we could combine these two plots so that we
get the benefits of both!?! That is, how can we overlay the jitterplot
over the boxplot? Try doing the following in the code chunk below with
my *hint*:

-   Re-create the boxplot with color that you did above, then
-   *Add* another geometry layer for the jitterplot.

Play around with doing the jitterplot laid over the boxplot and the
boxplot laid over the jitterplot. Which do you prefer? Why?

**Response**:

This is getting us closer to one of my favorite plots - the raincloud
plot. We are not quite ready to create this plot, but we will get there
eventually!

![raincloud plot](img/raincloud-plot.png)

Suppose that you wanted to only color the points in your combined plot,
but not the individual boxplots - you want the boxplots to be the
default white coloring. In the code chunk below, explore different
methods to try to create this plot. A hint, all `geom_*` have a
`mapping` argument.

In the above code chunk, continue to play around with having the
aesthetics mapped in the different layers. For example, how does having
all of them mapped in the `ggplot` call compared to having these instead
mapped in the `geom_boxplot` layer? Comment on what you notice.

**Response**:

Knit, stage, commit (with a meaningful commit message),and push
everything in your **Git** pane to your GitHub repo. Go to GitHub and
verify that your `activity02-ggplot2-intro.Rmd` file appears as you
intended it to.

### Exploration

Below is a histogram with a smoothed density (think proportion) area
curve behind it. I had to do a “trick” in my histogram layer to put both
of these plots on the same y-axis scale, but we will ignore that for the
time being. There appear to be two noticeable peaks in the distributions
of bill lengths: one around 39 mm and one around 46 mm.

![histogram and density plot](img/histogram-density.png)

Create graphs to explore the relationship between `bill_length_mm` and
each of `species`, `sex`, and `island` (you should have three total
graphs). Using these three graphs to discuss which of these three
categorical variables seems to be contributing more to these two peaks
and explain your reasoning.

**Response**:

Knit, stage, commit (with a meaningful commit message),and push
everything in your **Git** pane to your GitHub repo. Go to GitHub and
verify that your `activity02-ggplot2-intro.Rmd` file appears as you
intended it to.

### Scatterplots

You created some scatterplots in Preparation 3. Here we continue
exploring scatterplots using `{ggplot2}`.

In the code chunk below, create a scatterplot for the relationship
between `flipper_length_mm` and `body_mass_g`.

Describe any patterns that you notice.

**Response**:

Recreate your scatterplot in the code chunk below; however, *map*
`species` to the `color` and `shape` aesthetics.

Describe any patterns that you notice.

**Response**:

The previous plot looked great except even in this rather small dataset
(n = 344), there might are a number of points overlapping. In the R code
chunk below, *set* the values (instead of mapping a variable to an
aesthetic) of `size` (using some value larger than zero) and `alpha`
(using some value between 0 and 1) to make your previous plot more
effective.

Discuss the decisions you made to help your plot be easier to read.

**Response**:

Knit, stage, commit (with a meaningful commit message),and push
everything in your **Git** pane to your GitHub repo. Go to GitHub and
verify that your `activity02-ggplot2-intro.Rmd` file appears as you
intended it to.

You can now go back to the `README` file.
