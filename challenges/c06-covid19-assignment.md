COVID-19
================
Anna Letcher Hartman
2023-3-19

- <a href="#grading-rubric" id="toc-grading-rubric">Grading Rubric</a>
  - <a href="#individual" id="toc-individual">Individual</a>
  - <a href="#due-date" id="toc-due-date">Due Date</a>
- <a href="#the-big-picture" id="toc-the-big-picture">The Big Picture</a>
- <a href="#get-the-data" id="toc-get-the-data">Get the Data</a>
  - <a href="#navigating-the-census-bureau"
    id="toc-navigating-the-census-bureau">Navigating the Census Bureau</a>
    - <a
      href="#q1-load-table-b01003-into-the-following-tibble-make-sure-the-column-names-are-id-geographic-area-name-estimatetotal-margin-of-errortotal"
      id="toc-q1-load-table-b01003-into-the-following-tibble-make-sure-the-column-names-are-id-geographic-area-name-estimatetotal-margin-of-errortotal"><strong>q1</strong>
      Load Table <code>B01003</code> into the following tibble. Make sure the
      column names are
      <code>id, Geographic Area Name, Estimate!!Total, Margin of Error!!Total</code>.</a>
  - <a href="#automated-download-of-nyt-data"
    id="toc-automated-download-of-nyt-data">Automated Download of NYT
    Data</a>
    - <a
      href="#q2-visit-the-nyt-github-repo-and-find-the-url-for-the-raw-us-county-level-data-assign-that-url-as-a-string-to-the-variable-below"
      id="toc-q2-visit-the-nyt-github-repo-and-find-the-url-for-the-raw-us-county-level-data-assign-that-url-as-a-string-to-the-variable-below"><strong>q2</strong>
      Visit the NYT GitHub repo and find the URL for the <strong>raw</strong>
      US County-level data. Assign that URL as a string to the variable
      below.</a>
- <a href="#join-the-data" id="toc-join-the-data">Join the Data</a>
  - <a href="#q3-process-the-id-column-of-df_pop-to-create-a-fips-column"
    id="toc-q3-process-the-id-column-of-df_pop-to-create-a-fips-column"><strong>q3</strong>
    Process the <code>id</code> column of <code>df_pop</code> to create a
    <code>fips</code> column.</a>
  - <a
    href="#q4-join-df_covid-with-df_q3-by-the-fips-column-use-the-proper-type-of-join-to-preserve-only-the-rows-in-df_covid"
    id="toc-q4-join-df_covid-with-df_q3-by-the-fips-column-use-the-proper-type-of-join-to-preserve-only-the-rows-in-df_covid"><strong>q4</strong>
    Join <code>df_covid</code> with <code>df_q3</code> by the
    <code>fips</code> column. Use the proper type of join to preserve
    <em>only</em> the rows in <code>df_covid</code>.</a>
- <a href="#analyze" id="toc-analyze">Analyze</a>
  - <a href="#normalize" id="toc-normalize">Normalize</a>
    - <a
      href="#q5-use-the-population-estimates-in-df_data-to-normalize-cases-and-deaths-to-produce-per-100000-counts-3-store-these-values-in-the-columns-cases_per100k-and-deaths_per100k"
      id="toc-q5-use-the-population-estimates-in-df_data-to-normalize-cases-and-deaths-to-produce-per-100000-counts-3-store-these-values-in-the-columns-cases_per100k-and-deaths_per100k"><strong>q5</strong>
      Use the <code>population</code> estimates in <code>df_data</code> to
      normalize <code>cases</code> and <code>deaths</code> to produce per
      100,000 counts [3]. Store these values in the columns
      <code>cases_per100k</code> and <code>deaths_per100k</code>.</a>
  - <a href="#guided-eda" id="toc-guided-eda">Guided EDA</a>
    - <a
      href="#q6-compute-the-mean-and-standard-deviation-for-cases_per100k-and-deaths_per100k"
      id="toc-q6-compute-the-mean-and-standard-deviation-for-cases_per100k-and-deaths_per100k"><strong>q6</strong>
      Compute the mean and standard deviation for <code>cases_per100k</code>
      and <code>deaths_per100k</code>.</a>
    - <a
      href="#q7-find-the-top-10-counties-in-terms-of-cases_per100k-and-the-top-10-in-terms-of-deaths_per100k-report-the-population-of-each-county-along-with-the-per-100000-counts-compare-the-counts-against-the-mean-values-you-found-in-q6-note-any-observations"
      id="toc-q7-find-the-top-10-counties-in-terms-of-cases_per100k-and-the-top-10-in-terms-of-deaths_per100k-report-the-population-of-each-county-along-with-the-per-100000-counts-compare-the-counts-against-the-mean-values-you-found-in-q6-note-any-observations"><strong>q7</strong>
      Find the top 10 counties in terms of <code>cases_per100k</code>, and the
      top 10 in terms of <code>deaths_per100k</code>. Report the population of
      each county along with the per-100,000 counts. Compare the counts
      against the mean values you found in q6. Note any observations.</a>
  - <a href="#self-directed-eda" id="toc-self-directed-eda">Self-directed
    EDA</a>
    - <a
      href="#q8-drive-your-own-ship-youve-just-put-together-a-very-rich-dataset-you-now-get-to-explore-pick-your-own-direction-and-generate-at-least-one-punchline-figure-to-document-an-interesting-finding-i-give-a-couple-tips--ideas-below"
      id="toc-q8-drive-your-own-ship-youve-just-put-together-a-very-rich-dataset-you-now-get-to-explore-pick-your-own-direction-and-generate-at-least-one-punchline-figure-to-document-an-interesting-finding-i-give-a-couple-tips--ideas-below"><strong>q8</strong>
      Drive your own ship: You’ve just put together a very rich dataset; you
      now get to explore! Pick your own direction and generate at least one
      punchline figure to document an interesting finding. I give a couple
      tips &amp; ideas below:</a>
    - <a href="#ideas" id="toc-ideas">Ideas</a>
    - <a href="#aside-some-visualization-tricks"
      id="toc-aside-some-visualization-tricks">Aside: Some visualization
      tricks</a>
    - <a href="#geographic-exceptions"
      id="toc-geographic-exceptions">Geographic exceptions</a>
- <a href="#notes" id="toc-notes">Notes</a>

*Purpose*: In this challenge, you’ll learn how to navigate the U.S.
Census Bureau website, programmatically download data from the internet,
and perform a county-level population-weighted analysis of current
COVID-19 trends. This will give you the base for a very deep
investigation of COVID-19, which we’ll build upon for Project 1.

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

*Background*:
[COVID-19](https://en.wikipedia.org/wiki/Coronavirus_disease_2019) is
the disease caused by the virus SARS-CoV-2. In 2020 it became a global
pandemic, leading to huge loss of life and tremendous disruption to
society. The New York Times (as of writing) publishes up-to-date data on
the progression of the pandemic across the United States—we will study
these data in this challenge.

*Optional Readings*: I’ve found this [ProPublica
piece](https://www.propublica.org/article/how-to-understand-covid-19-numbers)
on “How to understand COVID-19 numbers” to be very informative!

# The Big Picture

<!-- -------------------------------------------------- -->

We’re about to go through *a lot* of weird steps, so let’s first fix the
big picture firmly in mind:

We want to study COVID-19 in terms of data: both case counts (number of
infections) and deaths. We’re going to do a county-level analysis in
order to get a high-resolution view of the pandemic. Since US counties
can vary widely in terms of their population, we’ll need population
estimates in order to compute infection rates (think back to the
`Titanic` challenge).

That’s the high-level view; now let’s dig into the details.

# Get the Data

<!-- -------------------------------------------------- -->

1.  County-level population estimates (Census Bureau)
2.  County-level COVID-19 counts (New York Times)

## Navigating the Census Bureau

<!-- ------------------------- -->

**Steps**: Our objective is to find the 2018 American Community
Survey\[1\] (ACS) Total Population estimates, disaggregated by counties.
To check your results, this is Table `B01003`.

1.  Go to [data.census.gov](data.census.gov).
2.  Scroll down and click `View Tables`.
3.  Apply filters to find the ACS **Total Population** estimates,
    disaggregated by counties. I used the filters:

- `Topics > Populations and People > Counts, Estimates, and Projections > Population Total`
- `Geography > County > All counties in United States`

5.  Select the **Total Population** table and click the `Download`
    button to download the data; make sure to select the 2018 5-year
    estimates.
6.  Unzip and move the data to your `challenges/data` folder.

- Note that the data will have a crazy-long filename like
  `ACSDT5Y2018.B01003_data_with_overlays_2020-07-26T094857.csv`. That’s
  because metadata is stored in the filename, such as the year of the
  estimate (`Y2018`) and my access date (`2020-07-26`). **Your filename
  will vary based on when you download the data**, so make sure to copy
  the filename that corresponds to what you downloaded!

### **q1** Load Table `B01003` into the following tibble. Make sure the column names are `id, Geographic Area Name, Estimate!!Total, Margin of Error!!Total`.

*Hint*: You will need to use the `skip` keyword when loading these data!

``` r
## TASK: Load the census bureau data with the following tibble name.
filenamePop <- "data/ACSDT5Y2018.B01003-Data.csv" 
columnNamesPop <- c(
  "Geography",
  "Geographic Area Name",
  "Estimate!!Total",
  "Annotation of Estimate!!Total",
  "Margin of Error!!Total",
  "Annotation of Margin of Error!!Total"
  )

df_pop <- read_csv(
  filenamePop,
  skip = 2,
  col_names = columnNamesPop

  #   # "Geography"                             = "text",
  #   # "Geographic Area Name"                  = "text",
  #   # "Estimate!!Total"                       = "numeric",
  #   # "Annotation of Estimate!!Total"         = "text",
  #   # "Margin of Error!!Total"                = "numeric",
  #   # "Annotation of Margin of Error!!Total"  = "text"
  # )
)
```

    ## Rows: 3220 Columns: 6
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr (5): Geography, Geographic Area Name, Annotation of Estimate!!Total, Mar...
    ## dbl (1): Estimate!!Total
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
glimpse(df_pop)
```

    ## Rows: 3,220
    ## Columns: 6
    ## $ Geography                              <chr> "0500000US01001", "0500000US010…
    ## $ `Geographic Area Name`                 <chr> "Autauga County, Alabama", "Bal…
    ## $ `Estimate!!Total`                      <dbl> 55200, 208107, 25782, 22527, 57…
    ## $ `Annotation of Estimate!!Total`        <chr> "null", "null", "null", "null",…
    ## $ `Margin of Error!!Total`               <chr> "*****", "*****", "*****", "***…
    ## $ `Annotation of Margin of Error!!Total` <chr> "*****", "*****", "*****", "***…

``` r
df_pop
```

    ## # A tibble: 3,220 × 6
    ##    Geography      `Geographic Area Name`   Estimate!!T…¹ Annot…² Margi…³ Annot…⁴
    ##    <chr>          <chr>                            <dbl> <chr>   <chr>   <chr>  
    ##  1 0500000US01001 Autauga County, Alabama          55200 null    *****   *****  
    ##  2 0500000US01003 Baldwin County, Alabama         208107 null    *****   *****  
    ##  3 0500000US01005 Barbour County, Alabama          25782 null    *****   *****  
    ##  4 0500000US01007 Bibb County, Alabama             22527 null    *****   *****  
    ##  5 0500000US01009 Blount County, Alabama           57645 null    *****   *****  
    ##  6 0500000US01011 Bullock County, Alabama          10352 null    *****   *****  
    ##  7 0500000US01013 Butler County, Alabama           20025 null    *****   *****  
    ##  8 0500000US01015 Calhoun County, Alabama         115098 null    *****   *****  
    ##  9 0500000US01017 Chambers County, Alabama         33826 null    *****   *****  
    ## 10 0500000US01019 Cherokee County, Alabama         25853 null    *****   *****  
    ## # … with 3,210 more rows, and abbreviated variable names ¹​`Estimate!!Total`,
    ## #   ²​`Annotation of Estimate!!Total`, ³​`Margin of Error!!Total`,
    ## #   ⁴​`Annotation of Margin of Error!!Total`

*Note*: You can find information on 1-year, 3-year, and 5-year estimates
[here](https://www.census.gov/programs-surveys/acs/guidance/estimates.html).
The punchline is that 5-year estimates are more reliable but less
current.

## Automated Download of NYT Data

<!-- ------------------------- -->

ACS 5-year estimates don’t change all that often, but the COVID-19 data
are changing rapidly. To that end, it would be nice to be able to
*programmatically* download the most recent data for analysis; that way
we can update our analysis whenever we want simply by re-running our
notebook. This next problem will have you set up such a pipeline.

The New York Times is publishing up-to-date data on COVID-19 on
[GitHub](https://github.com/nytimes/covid-19-data).

### **q2** Visit the NYT [GitHub](https://github.com/nytimes/covid-19-data) repo and find the URL for the **raw** US County-level data. Assign that URL as a string to the variable below.

``` r
## TASK: Find the URL for the NYT covid-19 county-level data
url_counties <- "https://raw.githubusercontent.com/nytimes/covid-19-data/master/us-counties.csv"
```

Once you have the url, the following code will download a local copy of
the data, then load the data into R.

``` r
## NOTE: No need to change this; just execute
## Set the filename of the data to download
filename_nyt <- "./data/nyt_counties.csv"

## Download the data locally
curl::curl_download(
        url_counties,
        destfile = filename_nyt
      )

## Loads the downloaded csv
df_covid <- read_csv(filename_nyt)
```

    ## Rows: 2502832 Columns: 6
    ## ── Column specification ────────────────────────────────────────────────────────
    ## Delimiter: ","
    ## chr  (3): county, state, fips
    ## dbl  (2): cases, deaths
    ## date (1): date
    ## 
    ## ℹ Use `spec()` to retrieve the full column specification for this data.
    ## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.

``` r
df_covid
```

    ## # A tibble: 2,502,832 × 6
    ##    date       county      state      fips  cases deaths
    ##    <date>     <chr>       <chr>      <chr> <dbl>  <dbl>
    ##  1 2020-01-21 Snohomish   Washington 53061     1      0
    ##  2 2020-01-22 Snohomish   Washington 53061     1      0
    ##  3 2020-01-23 Snohomish   Washington 53061     1      0
    ##  4 2020-01-24 Cook        Illinois   17031     1      0
    ##  5 2020-01-24 Snohomish   Washington 53061     1      0
    ##  6 2020-01-25 Orange      California 06059     1      0
    ##  7 2020-01-25 Cook        Illinois   17031     1      0
    ##  8 2020-01-25 Snohomish   Washington 53061     1      0
    ##  9 2020-01-26 Maricopa    Arizona    04013     1      0
    ## 10 2020-01-26 Los Angeles California 06037     1      0
    ## # … with 2,502,822 more rows

You can now re-run the chunk above (or the entire notebook) to pull the
most recent version of the data. Thus you can periodically re-run this
notebook to check in on the pandemic as it evolves.

*Note*: You should feel free to copy-paste the code above for your own
future projects!

# Join the Data

<!-- -------------------------------------------------- -->

To get a sense of our task, let’s take a glimpse at our two data
sources.

``` r
## NOTE: No need to change this; just execute
df_pop %>% glimpse
```

    ## Rows: 3,220
    ## Columns: 6
    ## $ Geography                              <chr> "0500000US01001", "0500000US010…
    ## $ `Geographic Area Name`                 <chr> "Autauga County, Alabama", "Bal…
    ## $ `Estimate!!Total`                      <dbl> 55200, 208107, 25782, 22527, 57…
    ## $ `Annotation of Estimate!!Total`        <chr> "null", "null", "null", "null",…
    ## $ `Margin of Error!!Total`               <chr> "*****", "*****", "*****", "***…
    ## $ `Annotation of Margin of Error!!Total` <chr> "*****", "*****", "*****", "***…

``` r
df_covid %>% glimpse
```

    ## Rows: 2,502,832
    ## Columns: 6
    ## $ date   <date> 2020-01-21, 2020-01-22, 2020-01-23, 2020-01-24, 2020-01-24, 20…
    ## $ county <chr> "Snohomish", "Snohomish", "Snohomish", "Cook", "Snohomish", "Or…
    ## $ state  <chr> "Washington", "Washington", "Washington", "Illinois", "Washingt…
    ## $ fips   <chr> "53061", "53061", "53061", "17031", "53061", "06059", "17031", …
    ## $ cases  <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, …
    ## $ deaths <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, …

To join these datasets, we’ll need to use [FIPS county
codes](https://en.wikipedia.org/wiki/FIPS_county_code).\[2\] The last
`5` digits of the `id` column in `df_pop` is the FIPS county code, while
the NYT data `df_covid` already contains the `fips`.

### **q3** Process the `id` column of `df_pop` to create a `fips` column.

``` r
## TASK: Create a `fips` column by extracting the county code
df_q3 <- 
  df_pop %>% 
  separate(
    col = Geography,
    into = c("Geography", "fips"),
    sep = -5
  )

df_q3  
```

    ## # A tibble: 3,220 × 7
    ##    Geography fips  `Geographic Area Name`   Estimate!!…¹ Annot…² Margi…³ Annot…⁴
    ##    <chr>     <chr> <chr>                           <dbl> <chr>   <chr>   <chr>  
    ##  1 0500000US 01001 Autauga County, Alabama         55200 null    *****   *****  
    ##  2 0500000US 01003 Baldwin County, Alabama        208107 null    *****   *****  
    ##  3 0500000US 01005 Barbour County, Alabama         25782 null    *****   *****  
    ##  4 0500000US 01007 Bibb County, Alabama            22527 null    *****   *****  
    ##  5 0500000US 01009 Blount County, Alabama          57645 null    *****   *****  
    ##  6 0500000US 01011 Bullock County, Alabama         10352 null    *****   *****  
    ##  7 0500000US 01013 Butler County, Alabama          20025 null    *****   *****  
    ##  8 0500000US 01015 Calhoun County, Alabama        115098 null    *****   *****  
    ##  9 0500000US 01017 Chambers County, Alabama        33826 null    *****   *****  
    ## 10 0500000US 01019 Cherokee County, Alabama        25853 null    *****   *****  
    ## # … with 3,210 more rows, and abbreviated variable names ¹​`Estimate!!Total`,
    ## #   ²​`Annotation of Estimate!!Total`, ³​`Margin of Error!!Total`,
    ## #   ⁴​`Annotation of Margin of Error!!Total`

Use the following test to check your answer.

``` r
## NOTE: No need to change this
## Check known county
assertthat::assert_that(
              (df_q3 %>%
              filter(str_detect(`Geographic Area Name`, "Autauga County")) %>%
              pull(fips)) == "01001"
            )
```

    ## [1] TRUE

``` r
print("Very good!")
```

    ## [1] "Very good!"

### **q4** Join `df_covid` with `df_q3` by the `fips` column. Use the proper type of join to preserve *only* the rows in `df_covid`.

``` r
## TASK: Join df_covid and df_q3 by fips.
df_q4 <- 
  df_covid %>% 
  left_join(df_q3, by = "fips")
df_q4
```

    ## # A tibble: 2,502,832 × 12
    ##    date       county    state fips  cases deaths Geogr…¹ Geogr…² Estim…³ Annot…⁴
    ##    <date>     <chr>     <chr> <chr> <dbl>  <dbl> <chr>   <chr>     <dbl> <chr>  
    ##  1 2020-01-21 Snohomish Wash… 53061     1      0 050000… Snohom…  7.87e5 null   
    ##  2 2020-01-22 Snohomish Wash… 53061     1      0 050000… Snohom…  7.87e5 null   
    ##  3 2020-01-23 Snohomish Wash… 53061     1      0 050000… Snohom…  7.87e5 null   
    ##  4 2020-01-24 Cook      Illi… 17031     1      0 050000… Cook C…  5.22e6 null   
    ##  5 2020-01-24 Snohomish Wash… 53061     1      0 050000… Snohom…  7.87e5 null   
    ##  6 2020-01-25 Orange    Cali… 06059     1      0 050000… Orange…  3.16e6 null   
    ##  7 2020-01-25 Cook      Illi… 17031     1      0 050000… Cook C…  5.22e6 null   
    ##  8 2020-01-25 Snohomish Wash… 53061     1      0 050000… Snohom…  7.87e5 null   
    ##  9 2020-01-26 Maricopa  Ariz… 04013     1      0 050000… Marico…  4.25e6 null   
    ## 10 2020-01-26 Los Ange… Cali… 06037     1      0 050000… Los An…  1.01e7 null   
    ## # … with 2,502,822 more rows, 2 more variables: `Margin of Error!!Total` <chr>,
    ## #   `Annotation of Margin of Error!!Total` <chr>, and abbreviated variable
    ## #   names ¹​Geography, ²​`Geographic Area Name`, ³​`Estimate!!Total`,
    ## #   ⁴​`Annotation of Estimate!!Total`

For convenience, I down-select some columns and produce more convenient
column names.

``` r
## NOTE: No need to change; run this to produce a more convenient tibble
df_data <-
  df_q4 %>%
  dplyr::select(
    date,
    county,
    state,
    fips,
    cases,
    deaths,
    population = `Estimate!!Total`
  )

df_data
```

    ## # A tibble: 2,502,832 × 7
    ##    date       county      state      fips  cases deaths population
    ##    <date>     <chr>       <chr>      <chr> <dbl>  <dbl>      <dbl>
    ##  1 2020-01-21 Snohomish   Washington 53061     1      0     786620
    ##  2 2020-01-22 Snohomish   Washington 53061     1      0     786620
    ##  3 2020-01-23 Snohomish   Washington 53061     1      0     786620
    ##  4 2020-01-24 Cook        Illinois   17031     1      0    5223719
    ##  5 2020-01-24 Snohomish   Washington 53061     1      0     786620
    ##  6 2020-01-25 Orange      California 06059     1      0    3164182
    ##  7 2020-01-25 Cook        Illinois   17031     1      0    5223719
    ##  8 2020-01-25 Snohomish   Washington 53061     1      0     786620
    ##  9 2020-01-26 Maricopa    Arizona    04013     1      0    4253913
    ## 10 2020-01-26 Los Angeles California 06037     1      0   10098052
    ## # … with 2,502,822 more rows

# Analyze

<!-- -------------------------------------------------- -->

Now that we’ve done the hard work of loading and wrangling the data, we
can finally start our analysis. Our first step will be to produce county
population-normalized cases and death counts. Then we will explore the
data.

## Normalize

<!-- ------------------------- -->

### **q5** Use the `population` estimates in `df_data` to normalize `cases` and `deaths` to produce per 100,000 counts \[3\]. Store these values in the columns `cases_per100k` and `deaths_per100k`.

``` r
## TASK: Normalize cases and deaths
df_normalized <-
  df_data %>% 
  mutate(
    cases_per100k = cases / population * 100000, 
    deaths_per100k = deaths / population * 100000
    )
df_normalized
```

    ## # A tibble: 2,502,832 × 9
    ##    date       county      state      fips  cases deaths popula…¹ cases…² death…³
    ##    <date>     <chr>       <chr>      <chr> <dbl>  <dbl>    <dbl>   <dbl>   <dbl>
    ##  1 2020-01-21 Snohomish   Washington 53061     1      0   786620 0.127         0
    ##  2 2020-01-22 Snohomish   Washington 53061     1      0   786620 0.127         0
    ##  3 2020-01-23 Snohomish   Washington 53061     1      0   786620 0.127         0
    ##  4 2020-01-24 Cook        Illinois   17031     1      0  5223719 0.0191        0
    ##  5 2020-01-24 Snohomish   Washington 53061     1      0   786620 0.127         0
    ##  6 2020-01-25 Orange      California 06059     1      0  3164182 0.0316        0
    ##  7 2020-01-25 Cook        Illinois   17031     1      0  5223719 0.0191        0
    ##  8 2020-01-25 Snohomish   Washington 53061     1      0   786620 0.127         0
    ##  9 2020-01-26 Maricopa    Arizona    04013     1      0  4253913 0.0235        0
    ## 10 2020-01-26 Los Angeles California 06037     1      0 10098052 0.00990       0
    ## # … with 2,502,822 more rows, and abbreviated variable names ¹​population,
    ## #   ²​cases_per100k, ³​deaths_per100k

You may use the following test to check your work.

``` r
## NOTE: No need to change this
## Check known county data
if (any(df_normalized %>% pull(date) %>% str_detect(., "2020-01-21"))) {
  assertthat::assert_that(TRUE)
} else {
  print(str_c(
    "Date 2020-01-21 not found; did you download the historical data (correct),",
    "or just the most recent data (incorrect)?",
    sep = " "
  ))
  assertthat::assert_that(FALSE)
}
```

    ## [1] TRUE

``` r
assertthat::assert_that(
              abs(df_normalized %>%
               filter(
                 str_detect(county, "Snohomish"),
                 date == "2020-01-21"
               ) %>%
              pull(cases_per100k) - 0.127) < 1e-3
            )
```

    ## [1] TRUE

``` r
assertthat::assert_that(
              abs(df_normalized %>%
               filter(
                 str_detect(county, "Snohomish"),
                 date == "2020-01-21"
               ) %>%
              pull(deaths_per100k) - 0) < 1e-3
            )
```

    ## [1] TRUE

``` r
print("Excellent!")
```

    ## [1] "Excellent!"

## Guided EDA

<!-- ------------------------- -->

Before turning you loose, let’s complete a couple guided EDA tasks.

### **q6** Compute the mean and standard deviation for `cases_per100k` and `deaths_per100k`.

``` r
## TASK: Compute mean and sd for cases_per100k and deaths_per100k
# df_normalized %>%
#   summarise(
#     mean_cases_per100k = mean(cases_per100k, na.rm    
# = TRUE ), 
#     sd_cases_per100k = sd(cases_per100k, na.rm    
# = TRUE ), 
#     mean_deaths_per100k = mean(deaths_per100k, na.rm  
# = TRUE ), 
#     sd_deaths_per100k = sd(deaths_per100k, na.rm  
# = TRUE )
#     )

mean_cases_per100k = mean(df_normalized$cases_per100k, na.rm    
= TRUE) 
sd_cases_per100k = sd(df_normalized$cases_per100k, na.rm    
= TRUE)
mean_deaths_per100k = mean(df_normalized$deaths_per100k, na.rm  
= TRUE) 
sd_deaths_per100k = sd(df_normalized$deaths_per100k, na.rm  
= TRUE)

mean_cases_per100k  
```

    ## [1] 9974.675

``` r
sd_cases_per100k
```

    ## [1] 8448.659

``` r
mean_deaths_per100k 
```

    ## [1] 174.3095

``` r
sd_deaths_per100k
```

    ## [1] 158.9641

### **q7** Find the top 10 counties in terms of `cases_per100k`, and the top 10 in terms of `deaths_per100k`. Report the population of each county along with the per-100,000 counts. Compare the counts against the mean values you found in q6. Note any observations.

``` r
## TASK: Find the top 10 max cases_per100k counties; report populations as well
top10_cases_per100k <-
  df_normalized %>%
  group_by(county) %>% 
  summarise(
    max_cases_per100k = max(cases_per100k)
    ) %>% 
  filter(dense_rank(desc(max_cases_per100k)) <= 10) %>% 
  arrange(desc(max_cases_per100k)) %>% 
  left_join(
    x= ., 
    y = subset(df_normalized, select = c("cases_per100k", "population", "state")),
    by = c(max_cases_per100k = "cases_per100k")
    ) %>% 
   unique()

## TASK: Find the top 10 deaths_per100k counties; report populations as well
top10_deaths_per100k <-
  df_normalized %>% 
  group_by(county) %>% 
  summarise(
    max_deaths_per100k = max(deaths_per100k)
    ) %>% 
  filter(dense_rank(desc(max_deaths_per100k)) <= 10) %>% 
  arrange(desc(max_deaths_per100k)) %>% 
  left_join(
    x= ., 
    y = subset(df_normalized, select = c("deaths_per100k", "population", "state")),
    by = c(max_deaths_per100k = "deaths_per100k")
    ) %>% 
   unique()

# is there a cleaner way to do this?
top10_cases_per100k
```

    ## # A tibble: 10 × 4
    ##    county                   max_cases_per100k population state       
    ##    <chr>                                <dbl>      <dbl> <chr>       
    ##  1 Loving                             192157.        102 Texas       
    ##  2 Chattahoochee                       69527.      10767 Georgia     
    ##  3 Nome Census Area                    62922.       9925 Alaska      
    ##  4 Northwest Arctic Borough            62542.       7734 Alaska      
    ##  5 Crowley                             59449.       5630 Colorado    
    ##  6 Bethel Census Area                  57439.      18040 Alaska      
    ##  7 Dewey                               54317.       5779 South Dakota
    ##  8 Dimmit                              54019.      10663 Texas       
    ##  9 Jim Hogg                            50133.       5282 Texas       
    ## 10 Kusilvak Census Area                49817.       8198 Alaska

``` r
# mean_cases_per100k = 9974.675 
top10_deaths_per100k
```

    ## # A tibble: 10 × 4
    ##    county            max_deaths_per100k population state       
    ##    <chr>                          <dbl>      <dbl> <chr>       
    ##  1 McMullen                       1360.        662 Texas       
    ##  2 Galax city                     1175.       6638 Virginia    
    ##  3 Motley                         1125.       1156 Texas       
    ##  4 Hancock                        1054.       8535 Georgia     
    ##  5 Emporia city                   1022.       5381 Virginia    
    ##  6 Towns                          1016.      11417 Georgia     
    ##  7 Jerauld                         986.       2029 South Dakota
    ##  8 Loving                          980.        102 Texas       
    ##  9 Robertson                       980.       2143 Kentucky    
    ## 10 Martinsville city               946.      13101 Virginia

``` r
# mean_deaths_per100k  = 174.3095
mean(df_normalized$population, na.rm = TRUE )
```

    ## [1] 101992.2

**Observations**:

- Loving Texas has the highest cases per 100,000 people over all at
  192,156.86. Most likely because the number of cases is higher than the
  estimated total population in 2018.
- Despite Loving Texas being an extreme outlire, the mean cases per
  100,000, 9,974.675, is still much lower than the top ten counties. The
  next highest is after Loving isChattahoochee, Georgia, with 69,527.26
  cases per 100,000.
- All counties in the top 10 cases per 100,000 people had a population
  of less than 19,000. All counties in the top 10 deaths per 100,000
  people had a population of less than 14,000. These populations are
  very small compared to the mean population of df_normalized,
  101,992.2.
- Loving Texas is the only county that appears in the top 10 cases and
  deaths per 100,000 people.
- McMullen Texas has the highest deaths per 100000 people, 1359.5, but a
  very small population, 662.
- Martinsville city Virginia has the highest population of the top ten
  counties for deaths at just over 13 thousand with around 946.5 deaths
  per 100,000 people.
- the mean is once agin much lower than the highest deaths per 100000
  people.

## Self-directed EDA

<!-- ------------------------- -->

### **q8** Drive your own ship: You’ve just put together a very rich dataset; you now get to explore! Pick your own direction and generate at least one punchline figure to document an interesting finding. I give a couple tips & ideas below:

### Ideas

<!-- ------------------------- -->

- Look for outliers.
- Try web searching for news stories in some of the outlier counties.
- Investigate relationships between county population and counts.
- Do a deep-dive on counties that are important to you (e.g. where you
  or your family live).
- Fix the *geographic exceptions* noted below to study New York City.
- Your own idea!

**DO YOUR OWN ANALYSIS HERE**

``` r
#"deaths_per100k", "population", "state"
df_normalized %>%
  filter(county == "Lehigh") %>%

  ggplot(
    aes(date, cases_per100k)
  ) +
  geom_line() +
  geom_line(mapping = aes(date, deaths_per100k)) +
  scale_y_log10(labels = scales::label_number_si()) +
  #scale_color_discrete(name = "County") +
  theme_minimal() +
  labs(
    x = "Date",
    y = "Cases (per 100,000 persons)"
  )
```

    ## Warning: `label_number_si()` was deprecated in scales 1.2.0.
    ## ℹ Please use the `scale_cut` argument of `label_number()` instead.

    ## Warning: Transformation introduced infinite values in continuous y-axis

![](c06-covid19-assignment_files/figure-gfm/unnamed-chunk-1-1.png)<!-- -->

``` r
bycounty_deaths_per100k <-
  df_normalized %>% 
  group_by(county) %>% 
  summarise(
    max_deaths_per100k = max(deaths_per100k), population = ave(population)
    ) %>% 
  unique()
```

    ## `summarise()` has grouped output by 'county'. You can override using the
    ## `.groups` argument.

``` r
bycounty_deaths_per100k %>% 
  ggplot(
    aes(population, max_deaths_per100k)
  ) +
  geom_point() +
  scale_y_log10(labels = scales::label_number_si()) +
  scale_x_log10(labels = scales::label_number_si()) +
  theme_minimal() +
  labs(
    x = "Population",
    y = "Cases (per 100,000 persons)"
  )
```

    ## Warning: Transformation introduced infinite values in continuous y-axis

    ## Warning: Removed 91 rows containing missing values (`geom_point()`).

![](c06-covid19-assignment_files/figure-gfm/unnamed-chunk-2-1.png)<!-- -->

``` r
top10_deaths_per100k %>% 
  ggplot(
    aes(population, max_deaths_per100k, color = fct_reorder2(county, population, max_deaths_per100k))
  ) +
  geom_point() +
  scale_y_log10(labels = scales::label_number_si()) +
  scale_color_discrete(name = "County") +
  theme_minimal() +
  labs(
    x = "Population",
    y = "Cases (per 100,000 persons)"
  )
```

![](c06-covid19-assignment_files/figure-gfm/unnamed-chunk-2-2.png)<!-- -->

``` r
bycounty_deaths_per100k
```

    ## # A tibble: 1,932 × 3
    ## # Groups:   county [1,932]
    ##    county    max_deaths_per100k population
    ##    <chr>                  <dbl>      <dbl>
    ##  1 Abbeville              284.      24657 
    ##  2 Acadia                 470.      62568 
    ##  3 Accomack               324.      32742 
    ##  4 Ada                    229.     446052 
    ##  5 Adair                  716.      18423.
    ##  6 Adams                  531.      72056.
    ##  7 Addison                 48.7     36939 
    ##  8 Adjuntas                NA       18181 
    ##  9 Aguada                  NA       38643 
    ## 10 Aguadilla               NA       54166 
    ## # … with 1,922 more rows

I wildly missmanaged my time and this is terrible

### Aside: Some visualization tricks

<!-- ------------------------- -->

These data get a little busy, so it’s helpful to know a few `ggplot`
tricks to help with the visualization. Here’s an example focused on
Massachusetts.

``` r
## NOTE: No need to change this; just an example
df_normalized %>%
  filter(state == "Massachusetts") %>%

  ggplot(
    aes(date, cases_per100k, color = fct_reorder2(county, date, cases_per100k))
  ) +
  geom_line() +
  scale_y_log10(labels = scales::label_number_si()) +
  scale_color_discrete(name = "County") +
  theme_minimal() +
  labs(
    x = "Date",
    y = "Cases (per 100,000 persons)"
  )
```

    ## Warning: Removed 789 rows containing missing values (`geom_line()`).

![](c06-covid19-assignment_files/figure-gfm/ma-example-1.png)<!-- -->

*Tricks*:

- I use `fct_reorder2` to *re-order* the color labels such that the
  color in the legend on the right is ordered the same as the vertical
  order of rightmost points on the curves. This makes it easier to
  reference the legend.
- I manually set the `name` of the color scale in order to avoid
  reporting the `fct_reorder2` call.
- I use `scales::label_number_si` to make the vertical labels more
  readable.
- I use `theme_minimal()` to clean up the theme a bit.
- I use `labs()` to give manual labels.

### Geographic exceptions

<!-- ------------------------- -->

The NYT repo documents some [geographic
exceptions](https://github.com/nytimes/covid-19-data#geographic-exceptions);
the data for New York, Kings, Queens, Bronx and Richmond counties are
consolidated under “New York City” *without* a fips code. Thus the
normalized counts in `df_normalized` are `NA`. To fix this, you would
need to merge the population data from the New York City counties, and
manually normalize the data.

# Notes

<!-- -------------------------------------------------- -->

\[1\] The census used to have many, many questions, but the ACS was
created in 2010 to remove some questions and shorten the census. You can
learn more in [this wonderful visual
history](https://pudding.cool/2020/03/census-history/) of the census.

\[2\] FIPS stands for [Federal Information Processing
Standards](https://en.wikipedia.org/wiki/Federal_Information_Processing_Standards);
these are computer standards issued by NIST for things such as
government data.

\[3\] Demographers often report statistics not in percentages (per 100
people), but rather in per 100,000 persons. This is [not always the
case](https://stats.stackexchange.com/questions/12810/why-do-demographers-give-rates-per-100-000-people)
though!
