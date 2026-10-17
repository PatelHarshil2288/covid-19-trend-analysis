# COVID-19 Trend Analysis with Python

A data science project exploring historical COVID-19 trends with Python, Pandas, NumPy, Plotly, and Prophet. Developed in Google Colab as a portfolio project based on the training assignment *Analyzing the Trends of COVID-19 with Python*.

## Project objectives

- Inspect, clean, and validate the supplied COVID-19 dataset.
- Explore cumulative confirmed cases, deaths, recoveries, and active cases globally and in India.
- Create interactive Plotly visualizations for trends, daily changes, country rankings, and WHO regional comparisons.
- Forecast global cumulative confirmed cases seven days ahead using Prophet.
- Evaluate the forecast on a chronological 14-day holdout using MAE and RMSE.
- Document data-quality issues, findings, and forecasting limitations.

## Dataset

The project uses the single instructor-provided file `covid_19_clean_complete.csv`. It contains 49,068 rows and 10 columns, covering 187 countries/regions from January 22, 2020, through July 27, 2020.

The raw CSV is not included in this repository. Before running the notebook, make the file available in the Colab runtime at `/content/covid_19_clean_complete.csv`. If the runtime is reset, the file may need to be made available again; Google Drive can be used as an alternative storage location.

## Notebook

Open [`COVID_19_Trend_Analysis.ipynb`](./COVID_19_Trend_Analysis.ipynb) in GitHub, or open it in Google Colab using the Colab interface.

## Technologies

- Python
- Pandas and NumPy
- Plotly Express
- Prophet
- Scikit-learn
- Google Colab

Install dependencies in Colab with:

```python
%pip install -r requirements.txt
```

Alternatively, install Prophet directly in a notebook cell with `%pip install prophet -q` if you are not using the requirements file.

## Methodology

1. Inspect the raw data and validate column types, missing values, duplicates, dates, and case-count consistency.
2. Retain the original records and flag 18 records with negative active-case values / deaths plus recoveries exceeding confirmed cases, rather than silently deleting or altering them.
3. Aggregate the source data by date for global and India time series, and by country and WHO region for comparisons.
4. Use Plotly to explore cumulative counts and daily changes.
5. Fit Prophet to global cumulative confirmed cases. Evaluate on the final 14 historical days, then refit on all available observations to produce a seven-day forecast.

## Results

- Records: 49,068; countries/regions: 187; date range: 2020-01-22 to 2020-07-27.
- Data-quality checks flagged 18 inconsistent active-case records.
- The Prophet holdout evaluation produced MAE **844,762.48 cases** and RMSE **899,652.37 cases**.
- The seven-day forecast covers July 28 to August 3, 2020. These are historical model estimates, not observed counts or current COVID-19 predictions.

## Limitations

The data ends on July 27, 2020, and reflects historical reported counts, which may vary in completeness and reporting practices across countries. The holdout errors indicate that the baseline Prophet model underestimated actual cumulative counts during the test period. Forecasts and uncertainty intervals are exploratory estimates, not guarantees or public-health advice.

## Reproducibility note

Run the notebook cells from top to bottom in Google Colab after making the CSV available at the path shown above. The notebook creates derived tables and a forecast CSV during execution. Generated files are reproducible outputs from the single source dataset, not additional source datasets.
