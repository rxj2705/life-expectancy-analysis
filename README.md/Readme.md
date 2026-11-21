# Life Expectancy Analysis (WHO data, 2000–2015)

Data cleaning, analysis and visualisation of life expectancy across 193 countries, using Python (Pandas and Matplotlib).

![Life expectancy trend](images/01_trend_by_status.png)

## Dataset
- **Source:** [Life Expectancy Analysis on Kaggle](https://www.kaggle.com/datasets/nailasrivastava/life-expectancy-analysis), originally from WHO and UN data
- **Size:** 2,938 rows × 22 columns, 193 countries, 2000–2015

## Project structure
- `raw_data/`: original CSV
- `cleaned_data/`: cleaned CSV created by the notebook
- `notebooks/`: the analysis notebook
- `images/`: charts saved by the notebook

## Data cleaning
- Tidied column names (stray spaces, mixed case)
- Dropped 10 rows with no life expectancy
- Dropped BMI and population (unreliable values)
- Marked impossible values (e.g. 0 years of schooling) as missing
- Filled 2,403 missing values using each country's own data, then the group median

## Key findings
- Mean life expectancy is 69.2 years and the median is 72.1. A group of low-scoring countries pulls the mean down.
- Developed countries average 79.2 years and developing countries 67.1.
- From 2000 to 2015 the gap narrowed from 12.2 to 11.0 years.
- Income composition (r = 0.86) and schooling (r = 0.77) have the strongest positive links. Adult mortality (r = −0.76) has the strongest negative link.

| | |
|---|---|
| ![](images/03_status_bar.png) | ![](images/04_top_bottom_2015.png) |
| ![](images/05_correlations.png) | ![](images/07_schooling_scatter.png) |

## How to run
1. Clone the repo
2. `python3 -m venv venv` then `source venv/bin/activate`
3. `pip install -r requirements.txt`
4. `jupyter notebook`, then open the notebook in `notebooks/` and run all cells

## Tools
Python 3, Pandas, NumPy, Matplotlib, Jupyter