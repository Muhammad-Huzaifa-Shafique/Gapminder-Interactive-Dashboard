# Gapminder Interactive Dashboard

An interactive report built with **Quarto** and **R** that uses two animated charts to show how life expectancy and wealth changed around the world between 1952 and 2007. It was created as a Data Visualization course project.

## What this project shows

Understanding a dataset and explaining it clearly comes before any model. This report does that for 142 countries from 1952 to 2007, and it makes two choices that matter: it weights continent averages by population, and it puts income on a log scale.

| What an AI/ML team looks for | Where it shows up here |
|---|---|
| Looking at the data at two levels | One animation shows every country (income against life expectancy). The other summarizes continents. Together they show both the spread and the overall direction |
| Choosing the right summary | Continent averages are weighted by population. In 1952 the simple average for the Americas is 53.3 years, but the population-weighted figure is 60.2, because the United States alone holds about 46% of the continent's people (computed from `gapminder_dataset.csv`) |
| A scale that suits the data | Income per person is on a log scale, so a few very rich countries do not push everyone else into one corner |
| Plain-language communication | Each animation comes with the question it answers, an explanation of the result, a summary table, and a limitations section |
| Reproducible work | One Quarto file rebuilds the whole report, and the data is in the repository |

What it finds, using population-weighted life expectancy from 1952 to 2007: Asia gained the most, from 42.9 to 69.4 years (+26.5). Africa rose from 38.8 to 54.6 (+15.8) and is still the lowest. The gap between the highest and lowest continent narrowed from 30.4 years to 26.5 (Oceania and Africa in both years).

**Limits.** The data stops in 2007 and is sampled every five years. Each value is a country-level average, so it hides differences inside a country. Oceania has only two countries (Australia and New Zealand). The report shows that income and life expectancy move together, not that one causes the other.

**Next step.** Fit a simple model, for example life expectancy from log income, year and continent. Train it on 1952 to 1997 and test it on 2002 and 2007, so it is judged on years it has not seen.

## What you'll find in the report

1. **Animation 1: countries.** Each dot is a country, placed by income per person (GDP per capita, log scale) and life expectancy, colored by continent, and animated year by year. Hover over a dot to see that country's numbers.
2. **Animation 2: continents.** An animated bar chart of average life expectancy for each continent, weighted by population so that larger countries count for more.

Each animation comes with the question it answers, a plain-language explanation of the results, and a small summary table. The report ends with lessons learned and limitations.

## View the report

**Open it online:** [Animated Data with Gapminder](https://muhammad-huzaifa-shafique.github.io/Gapminder-Interactive-Dashboard/Animation_data.html). No download needed.

To view it offline instead, download or clone the repository and open **`Animation_data.html`** in your browser. Keep the `Animation_data_files/` folder next to it, because the page needs it to display the charts.

## About the data

`gapminder_dataset.csv` holds 1,704 rows: 142 countries, measured every five years from 1952 to 2007. It comes from [Gapminder](https://www.gapminder.org).

| Column | Meaning |
|---|---|
| `country` | Country name |
| `continent` | Africa, Americas, Asia, Europe, or Oceania |
| `year` | Year of the observation |
| `lifeExp` | Life expectancy at birth, in years |
| `pop` | Population |
| `gdpPercap` | GDP per person (per capita) |

## Rebuild the report yourself

1. Install [R](https://www.r-project.org) and [Quarto](https://quarto.org/docs/get-started/).
2. Open a terminal in this folder and run:

   ```bash
   quarto render Animation_data.qmd
   ```

The report installs any missing R packages it needs (`plotly`, `scales`, `knitr`) the first time it runs.

## Project files

| File or folder | What it is |
|---|---|
| `Animation_data.qmd` | The source of the report: text, R code, and both animations |
| `Animation_data.html` | The finished report, ready to open in a browser |
| `Animation_data_files/` | Support files the finished report needs (charts and styling) |
| `gapminder_dataset.csv` | The data |

## Author

Made by [Muhammad Huzaifa Shafique](https://github.com/Muhammad-Huzaifa-Shafique).
