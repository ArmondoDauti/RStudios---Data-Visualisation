# RStudios---Data-Visualisation
This project demonstrates my ability to handle a complete data analysis workflow using R and RStudio — from importing a raw CSV file, cleaning and exploring the data, to producing clear visualisations using ggplot2.

Rather than providing instructions to reproduce the work, this README explains the steps I personally executed to achieve the analysis shown.

📁 Dataset

I worked with a dataset named MoviesRatingRottenTomato.csv containing 74 films.
It included the following key variables:

Column	Description
Film	Movie title
Genre	Genre (Comedy, Drama, Action, etc.)
Lead.Studio	Production or distribution studio
Audience.Score	Audience rating percentage
Rotten.Tomatoes	Critics’ ratings from Rotten Tomatoes
Profitability	Profitability ratio
Worldwide.Gross	Total worldwide gross (in millions)
Year	Year of release
⚙️ My Workflow

Here’s the process I followed, with the exact R code used at each stage:


🧩 1. Setting Up the Environment

I first set my working directory in RStudio to the folder containing the dataset:

setwd("C:/Users/MyName/Documents/movie_project")


I confirmed this with:

getwd()


📥 2. Importing the Dataset

I loaded the CSV file into R as a data frame and opened it in RStudio’s data viewer:

df <- read.csv("MoviesRatingRottenTomato.csv")
View(df)


🧐 3. Exploring the Data Structure

I checked the internal structure and types of each column:

str(df)


I also generated descriptive statistics to understand the data distribution:

summary(df)


This gave me insights into numeric ranges (e.g. Profitability, Rotten.Tomatoes) and categorical distributions (e.g. Genre, Lead.Studio).


🧹 4. Cleaning the Data

To ensure clean input for visualisation and analysis, I removed rows containing missing values:

df <- na.omit(df)


This gave me a complete dataset without gaps, which is crucial for generating accurate plots.


📦 5. Loading Libraries

I used the ggplot2 package to create all my visualisations.
If not already installed, it can be installed with install.packages("ggplot2"), and then I loaded it:

library(ggplot2)


📊 6. Visualising Trends

With clean data prepared, I explored patterns visually.

Bar Chart — Number of Movies Released Per Year

ggplot(df, aes(x = Year)) +
  geom_bar()


This plot clearly showed which years had the highest number of film releases in the dataset.

Scatter Plot — Rotten Tomatoes Scores by Lead Studio

ggplot(df, aes(x = Lead.Studio, y = Rotten.Tomatoes)) +
  geom_point() +
  scale_y_continuous(labels = scales::comma) +
  coord_cartesian(ylim = c(0, 110)) +
  theme(axis.text.x = element_text(angle = 90))


This plot helped me see how critics’ scores varied across different production studios.


📌 Outcome

Through these steps, I successfully:

Imported and structured the dataset

Cleaned and prepared the data

Explored it through descriptive statistics

Produced clear visual insights using ggplot2

This project demonstrates my ability to independently execute an entire data analysis workflow in R — from raw CSV to insight-driven visualisations — while maintaining clean, reproducible code.
