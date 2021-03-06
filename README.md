What Happens in Vegas: Predicting Hotel Ratings From Hotel and User Data
================
Arun Marria, Bronwyn Baillie, and Manish Joshi
2020-01-24 (updated: 2020-02-08)

Demo of a data analysis project for DSCI 522 (Data Science workflows); a
course in the Master of Data Science program at the University of
British Columbia.

## About

In this project, we build a linear regression model that uses data
collected from TripAdvisor user reviews of Las Vegas hotels to predict
what kind of user ratings can be expected for a hotel. Exploratory data
analysis was performed in R on only a portion of our data reserved for
training. In our preliminary EDA, we checked the effect of different
user and hotel specific features against user ratings, and it became
apparent that most features did not have much impact on the hotel
ratings. However, upon further analysis throughout our project we
discovered that some features, such as the presence of a swimming pool,
free wifi, and user continent, did have an effect on hotel ratings.

The Dataset chosen for the research project is the “Las Vegas Strip
Dataset” which is collated information about customer feedback on 21
Hotels located in the Las Vegas Strip. The data is extracted from
popular, respected and well-regarded travel portal “TripAdvisor”. -Moro,
S., Rita, P., & Coelho, J. (2017). Stripping customers’ feedback on
hotels through data mining: The case of Las Vegas Strip. Tourism
Management Perspectives, 23, 41-52. It was sourced from the UCI machine
learning repositories, and can be found
[here](https://archive.ics.uci.edu/ml/datasets/Las+Vegas+Strip). Each
row in the data set represents information about one user review, and
contains variables such as the name of the hotel, amenities present in
the hotel such as a swimming pool, spa, or wifi, imformation about the
reviewer like the number of reviews they’ve given and the number of
years they’ve been a member, all along with the user’s rating for the
hotel.

## Report

The final report can be found [here](docs/Vegas_strip_data_report.md)

## Usage:

There are two suggested ways to run this analysis:

### 1\. Using Docker

*note - the instructions in this section also depends on running this in
a unix shell (e.g., terminal or Git Bash)*

1.  Install [Docker](https://www.docker.com/get-started)
2.  Download/clone this repository
3.  Use the command line to navigate to the root of this
    downloaded/cloned repo
4.  Type the
    following:

<!-- end list -->

    docker run --rm -v /$(pwd):/home/rstudio/vegas_predictor  arunmarria/milestone4_vegas_dataset:latest make -C /home/rstudio/vegas_predictor all

To reset the repo to a clean state, with no intermediate or results
files, run the following command at the command line/terminal from the
root directory of this
    project:

    docker run --rm -v /$(pwd):/home/rstudio/vegas_predictor  arunmarria/milestone4_vegas_dataset:latest make -C /home/rstudio/vegas_predictor clean

### 2\. Without using Docker

To replicate the analysis, clone this GitHub repository, install the
[dependencies](#dependencies) listed below, and run the following
command at the command line/terminal from the root directory of this
project:

    make all

To reset the repo to a clean state, with no intermediate or results
files, run the following command at the command line/terminal from the
root directory of this project:

    make clean

Find the dependency graph below for different scripts in makefile. Click
on image for detailed view.

![](img/graph.png)

## Dependencies

  - Python 3.7.3 and Python packages:
      - numpy==1.16.4
      - altair==3.2.0
      - selenium==3.141.0
      - sklearn==0.22.1
      - docopt==0.6.1
      - pandas==0.24.2
      - feather-format==0.4.0
  - R version 3.6.1 and R packages:
      - knitr==1.26
      - feather==0.3.5
      - tidyverse==1.3
      - caret==6.0-85
      - ggridges==0.5.2
      - ggthemes==4.2.0
      - ggplot2==3.2.1
      - readr==1.3.1
      - ggally==1.4.0
      - repr==1.0.2
      - gridextra==2.3
      - reticulate==1.14

# References

Moro, S., Rita, P., & Coelho, J. (2017). Stripping customers’ feedback
on hotels through data mining: The case of Las Vegas Strip. Tourism
Management Perspectives, 23, 41-52. “UCI Machine Learning Repository.”
University of California, Irvine, School of Information; Computer
Sciences. <http://archive.ics.uci.edu/ml>.
