Aluminum Data
================
Anna Letcher Hartman
2023-

- <a href="#grading-rubric" id="toc-grading-rubric">Grading Rubric</a>
  - <a href="#individual" id="toc-individual">Individual</a>
  - <a href="#due-date" id="toc-due-date">Due Date</a>
- <a href="#loading-and-wrangle" id="toc-loading-and-wrangle">Loading and
  Wrangle</a>
  - <a
    href="#q1-tidy-df_stang-to-produce-df_stang_long-you-should-have-column-names-thick-alloy-angle-e-nu-make-sure-the-angle-variable-is-of-correct-type-filter-out-any-invalid-values"
    id="toc-q1-tidy-df_stang-to-produce-df_stang_long-you-should-have-column-names-thick-alloy-angle-e-nu-make-sure-the-angle-variable-is-of-correct-type-filter-out-any-invalid-values"><strong>q1</strong>
    Tidy <code>df_stang</code> to produce <code>df_stang_long</code>. You
    should have column names <code>thick, alloy, angle, E, nu</code>. Make
    sure the <code>angle</code> variable is of correct type. Filter out any
    invalid values.</a>
- <a href="#eda" id="toc-eda">EDA</a>
  - <a href="#initial-checks" id="toc-initial-checks">Initial checks</a>
    - <a
      href="#q2-perform-a-basic-eda-on-the-aluminum-data-without-visualization-use-your-analysis-to-answer-the-questions-under-observations-below-in-addition-add-your-own-specific-question-that-youd-like-to-answer-about-the-datayoull-answer-it-below-in-q3"
      id="toc-q2-perform-a-basic-eda-on-the-aluminum-data-without-visualization-use-your-analysis-to-answer-the-questions-under-observations-below-in-addition-add-your-own-specific-question-that-youd-like-to-answer-about-the-datayoull-answer-it-below-in-q3"><strong>q2</strong>
      Perform a basic EDA on the aluminum data <em>without visualization</em>.
      Use your analysis to answer the questions under <em>observations</em>
      below. In addition, add your own <em>specific</em> question that you’d
      like to answer about the data—you’ll answer it below in q3.</a>
  - <a href="#visualize" id="toc-visualize">Visualize</a>
    - <a
      href="#q3-create-a-visualization-to-investigate-your-question-from-q2-above-can-you-find-an-answer-to-your-question-using-the-dataset-would-you-need-additional-information-to-answer-your-question"
      id="toc-q3-create-a-visualization-to-investigate-your-question-from-q2-above-can-you-find-an-answer-to-your-question-using-the-dataset-would-you-need-additional-information-to-answer-your-question"><strong>q3</strong>
      Create a visualization to investigate your question from q2 above. Can
      you find an answer to your question using the dataset? Would you need
      additional information to answer your question?</a>
    - <a href="#q4-consider-the-following-statement"
      id="toc-q4-consider-the-following-statement"><strong>q4</strong>
      Consider the following statement:</a>
- <a href="#references" id="toc-references">References</a>

*Purpose*: When designing structures such as bridges, boats, and planes,
the design team needs data about *material properties*. Often when we
engineers first learn about material properties through coursework, we
talk about abstract ideas and look up values in tables without ever
looking at the data that gave rise to published properties. In this
challenge you’ll study an aluminum alloy dataset: Studying these data
will give you a better sense of the challenges underlying published
material values.

In this challenge, you will load a real dataset, wrangle it into tidy
form, and perform EDA to learn more about the data.

<!-- include-rubric -->

# Grading Rubric

<!-- -------------------------------------------------- -->

Unlike exercises, **challenges will be graded**. The following rubrics
define how you will be graded, both on an individual and team basis.

## Individual

<!-- ------------------------- -->

| Category    | Needs Improvement                                                                                                | Satisfactory                                                                                                               |
|-------------|------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| Effort      | Some task **q**’s left unattempted                                                                               | All task **q**’s attempted                                                                                                 |
| Observed    | Did not document observations, or observations incorrect                                                         | Documented correct observations based on analysis                                                                          |
| Supported   | Some observations not clearly supported by analysis                                                              | All observations clearly supported by analysis (table, graph, etc.)                                                        |
| Assessed    | Observations include claims not supported by the data, or reflect a level of certainty not warranted by the data | Observations are appropriately qualified by the quality & relevance of the data and (in)conclusiveness of the support      |
| Specified   | Uses the phrase “more data are necessary” without clarification                                                  | Any statement that “more data are necessary” specifies which *specific* data are needed to answer what *specific* question |
| Code Styled | Violations of the [style guide](https://style.tidyverse.org/) hinder readability                                 | Code sufficiently close to the [style guide](https://style.tidyverse.org/)                                                 |

## Due Date

<!-- ------------------------- -->

All the deliverables stated in the rubrics above are due **at midnight**
before the day of the class discussion of the challenge. See the
[Syllabus](https://docs.google.com/document/d/1qeP6DUS8Djq_A0HMllMqsSqX3a9dbcx1/edit?usp=sharing&ouid=110386251748498665069&rtpof=true&sd=true)
for more information.

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.2 ──
    ## ✔ ggplot2 3.4.0      ✔ purrr   1.0.1 
    ## ✔ tibble  3.1.8      ✔ dplyr   1.0.10
    ## ✔ tidyr   1.2.1      ✔ stringr 1.5.0 
    ## ✔ readr   2.1.3      ✔ forcats 0.5.2 
    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

*Background*: In 1946, scientists at the Bureau of Standards tested a
number of Aluminum plates to determine their
[elasticity](https://en.wikipedia.org/wiki/Elastic_modulus) and
[Poisson’s ratio](https://en.wikipedia.org/wiki/Poisson%27s_ratio).
These are key quantities used in the design of structural members, such
as aircraft skin under [buckling
loads](https://en.wikipedia.org/wiki/Buckling). These scientists tested
plats of various thicknesses, and at different angles with respect to
the [rolling](https://en.wikipedia.org/wiki/Rolling_(metalworking))
direction.

# Loading and Wrangle

<!-- -------------------------------------------------- -->

The `readr` package in the Tidyverse contains functions to load data
form many sources. The `read_csv()` function will help us load the data
for this challenge.

``` r
## NOTE: If you extracted all challenges to the same location,
## you shouldn't have to change this filename
filename <- "./data/stang.csv"

## Load the data
df_stang <- read_csv(filename)
```

    ## Rows: 9 Columns: 8
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (1): alloy
    ## dbl (7): thick, E_00, nu_00, E_45, nu_45, E_90, nu_90
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
df_stang
```

    ## # A tibble: 9 × 8
    ##   thick  E_00 nu_00  E_45  nu_45  E_90 nu_90 alloy  
    ##   <dbl> <dbl> <dbl> <dbl>  <dbl> <dbl> <dbl> <chr>  
    ## 1 0.022 10600 0.321 10700  0.329 10500 0.31  al_24st
    ## 2 0.022 10600 0.323 10500  0.331 10700 0.323 al_24st
    ## 3 0.032 10400 0.329 10400  0.318 10300 0.322 al_24st
    ## 4 0.032 10300 0.319 10500  0.326 10400 0.33  al_24st
    ## 5 0.064 10500 0.323 10400  0.331 10400 0.327 al_24st
    ## 6 0.064 10700 0.328 10500  0.328 10500 0.32  al_24st
    ## 7 0.081 10000 0.315 10000  0.32   9900 0.314 al_24st
    ## 8 0.081 10100 0.312  9900  0.312 10000 0.316 al_24st
    ## 9 0.081 10000 0.311    -1 -1      9900 0.314 al_24st

Note that these data are not tidy! The data in this form are convenient
for reporting in a table, but are not ideal for analysis.

### **q1** Tidy `df_stang` to produce `df_stang_long`. You should have column names `thick, alloy, angle, E, nu`. Make sure the `angle` variable is of correct type. Filter out any invalid values.

*Hint*: You can reshape in one `pivot` using the `".value"` special
value for `names_to`.

``` r
## TASK: Tidy `df_stang`
df_stang_long <-
  df_stang %>%
  pivot_longer(
    names_to = c(".value","angle"),
    names_sep = "_",
    names_transform = list('angle' = as.integer),
    cols = c(-thick, -alloy)
  ) %>% 
  filter(E > 0)
  


#%>%
  # mutate(angle = as.integer(angle))


df_stang_long
```

    ## # A tibble: 26 × 5
    ##    thick alloy   angle     E    nu
    ##    <dbl> <chr>   <int> <dbl> <dbl>
    ##  1 0.022 al_24st     0 10600 0.321
    ##  2 0.022 al_24st    45 10700 0.329
    ##  3 0.022 al_24st    90 10500 0.31 
    ##  4 0.022 al_24st     0 10600 0.323
    ##  5 0.022 al_24st    45 10500 0.331
    ##  6 0.022 al_24st    90 10700 0.323
    ##  7 0.032 al_24st     0 10400 0.329
    ##  8 0.032 al_24st    45 10400 0.318
    ##  9 0.032 al_24st    90 10300 0.322
    ## 10 0.032 al_24st     0 10300 0.319
    ## # … with 16 more rows

Use the following tests to check your work.

``` r
## NOTE: No need to change this
## Names
assertthat::assert_that(
              setequal(
                df_stang_long %>% names,
                c("thick", "alloy", "angle", "E", "nu")
              )
            )
```

    ## [1] TRUE

``` r
## Dimensions
assertthat::assert_that(all(dim(df_stang_long) == c(26, 5)))
```

    ## [1] TRUE

``` r
## Type
assertthat::assert_that(
              (df_stang_long %>% pull(angle) %>% typeof()) == "integer"
            )
```

    ## [1] TRUE

``` r
print("Very good!")
```

    ## [1] "Very good!"

# EDA

<!-- -------------------------------------------------- -->

## Initial checks

<!-- ------------------------- -->

### **q2** Perform a basic EDA on the aluminum data *without visualization*. Use your analysis to answer the questions under *observations* below. In addition, add your own *specific* question that you’d like to answer about the data—you’ll answer it below in q3.

``` r
##
glimpse(df_stang_long)
```

    ## Rows: 26
    ## Columns: 5
    ## $ thick <dbl> 0.022, 0.022, 0.022, 0.022, 0.022, 0.022, 0.032, 0.032, 0.032, 0…
    ## $ alloy <chr> "al_24st", "al_24st", "al_24st", "al_24st", "al_24st", "al_24st"…
    ## $ angle <int> 0, 45, 90, 0, 45, 90, 0, 45, 90, 0, 45, 90, 0, 45, 90, 0, 45, 90…
    ## $ E     <dbl> 10600, 10700, 10500, 10600, 10500, 10700, 10400, 10400, 10300, 1…
    ## $ nu    <dbl> 0.321, 0.329, 0.310, 0.323, 0.331, 0.323, 0.329, 0.318, 0.322, 0…

``` r
unique(df_stang_long$alloy)
```

    ## [1] "al_24st"

``` r
unique(df_stang_long$thick)
```

    ## [1] 0.022 0.032 0.064 0.081

``` r
unique(df_stang_long$E)
```

    ## [1] 10600 10700 10500 10400 10300 10000  9900 10100

``` r
unique(df_stang_long$nu)
```

    ##  [1] 0.321 0.329 0.310 0.323 0.331 0.318 0.322 0.319 0.326 0.330 0.327 0.328
    ## [13] 0.320 0.315 0.314 0.312 0.316 0.311

``` r
mean(df_stang_long$E)
```

    ## [1] 10334.62

``` r
sd(df_stang_long$E)
```

    ## [1] 268.2421

``` r
mean(df_stang_long$nu)
```

    ## [1] 0.3212308

``` r
sd(df_stang_long$nu)
```

    ## [1] 0.006742745

**Observations**:

- Is there “one true value” for the material properties of Aluminum?
  - no, all alloys will be different and even within the same alloy
    there is no way to garentea that you can perfectly reproduce the
    exact same combination every time
- How many aluminum alloys are in this dataset? How do you know?
  - one alloy, al_24st
- What angles were tested?
  - 0, 45 , 90 deg
- What thicknesses were tested?
  - 0.022, 0.032, 0.064, and 0.081 inches thick
- Are there more unique values of E or mu?
  - there are 18 unique values of mu and only 8 unique values of E
- Does E vary more with thickness or angle?

## Visualize

<!-- ------------------------- -->

### **q3** Create a visualization to investigate your question from q2 above. Can you find an answer to your question using the dataset? Would you need additional information to answer your question?

``` r
## TASK: Investigate your question from q1 here
df_stang_long %>%
  ggplot(aes(x = angle, y = E, color = as_factor(thick))) +
  geom_count()
```

![](c03-stang-assignment_files/figure-gfm/q3-task-1.png)<!-- -->

``` r
df_stang_long %>%
  ggplot(aes(x = thick, y = E, color = as_factor(angle))) +
  geom_count()
```

![](c03-stang-assignment_files/figure-gfm/q3-task-2.png)<!-- -->

``` r
df_stang_long %>%
  ggplot(aes(x = angle, y = E, group = as_factor(thick))) +
  geom_boxplot()
```

![](c03-stang-assignment_files/figure-gfm/q3-task-3.png)<!-- -->

``` r
df_stang_long %>%
  ggplot(aes(x = angle, y = E, group = angle, color = thick)) +
  geom_boxplot()
```

    ## Warning: The following aesthetics were dropped during statistical transformation: colour
    ## ℹ This can happen when ggplot fails to infer the correct grouping structure in
    ##   the data.
    ## ℹ Did you forget to specify a `group` aesthetic or to convert a numerical
    ##   variable into a factor?

![](c03-stang-assignment_files/figure-gfm/q3-task-4.png)<!-- -->

``` r
df_stang_long %>%
  ggplot(aes(x = E, group = thick, color = as_factor(thick))) +
  geom_density()
```

![](c03-stang-assignment_files/figure-gfm/q3-task-5.png)<!-- -->

``` r
df_stang_long %>%
  ggplot(aes(x = E, group = angle, color = as_factor(angle))) +
  geom_density()
```

![](c03-stang-assignment_files/figure-gfm/q3-task-6.png)<!-- -->

``` r
  #geom_dotplot(binwidth = 100)
# df_stang_long %>%
#   ggplot(aes(x = thick, y = E, color = angle)) +
#   geom_point()
```

**Observations**:

- from the box plots of E broken out by angle I would conclude that it
  is very unlikely that the angle effects the elasticity
- from the box plots and distribution of E broken out by thickens the
  elasticity of the 0.022”, 0.032”, and 0.064” samples does not appear
  to be dependent on their thickness. The elasticity of the 0.082” thick
  samples appear to be lower overall.
- given the graphs I made I don’t think I can conclusively say that E
  varies more with angle or thickness. I am also not sure that I could
  conclusively say that it varied with ether in any way. To more
  conclusively ansawr my question I would need to look more into the
  strange behavior of the 0.082” thick samples and I would need to take
  the covariance of the elasticity with angle and thickness.

### **q4** Consider the following statement:

“A material’s property (or material property) is an intensive property
of some material, i.e. a physical property that does not depend on the
amount of the material.”\[2\]

Note that the “amount of material” would vary with the thickness of a
tested plate. Does the following graph support or contradict the claim
that “elasticity `E` is an intensive material property.” Why or why not?
Is this evidence *conclusive* one way or another? Why or why not?

``` r
## NOTE: No need to change; run this chunk
df_stang_long %>%

  ggplot(aes(nu, E, color = as_factor(thick))) +
  geom_point(size = 3) +
  theme_minimal()
```

![](c03-stang-assignment_files/figure-gfm/q4-vis-1.png)<!-- -->

**Observations**:

- Does this graph support or contradict the claim above?
  - The evidence is not conclusive. The 0.081” thick samples appear to
    have overall lower E values than the other samples but when looking
    at the graph this does not hold true for any other thickness. All of
    the other thicknesses have overlapping values that would seem to
    support the initial claim.
  - The discrepancy between the 0.081” thick samples and the other
    samples could be due to experimental error.

# References

<!-- -------------------------------------------------- -->

\[1\] Stang, Greenspan, and Newman, “Poisson’s ratio of some structural
alloys for large strains” (1946) Journal of Research of the National
Bureau of Standards, (pdf
link)\[<https://nvlpubs.nist.gov/nistpubs/jres/37/jresv37n4p211_A1b.pdf>\]

\[2\] Wikipedia, *List of material properties*, accessed 2020-06-26,
(link)\[<https://en.wikipedia.org/wiki/List_of_materials_properties>\]
