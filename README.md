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

The project uses the instructor-provided file `covid_19_clean_complete.csv`, which is included in this repository. It contains 49,068 rows and 10 columns, covering 187 countries/regions from January 22, 2020, through July 27, 2020.

**Data provenance and reuse:** The file was supplied for this assignment. Before treating it as approved for public redistribution, confirm the original source and applicable license, then add the appropriate attribution here. If the file is from the Johns Hopkins University CSSE COVID-19 Data Repository, follow its stated CC BY 4.0 attribution requirements and cite the original repository: https://github.com/CSSEGISandData/COVID-19. Do not assume that source without verifying that it matches the supplied file.

## Open the notebook

- [View the notebook on GitHub](./COVID_19_Trend_Analysis.ipynb)
- [Open the notebook in Google Colab](https://colab.research.google.com/github/PatelHarshil2288/covid-19-trend-analysis/blob/main/COVID_19_Trend_Analysis.ipynb)

The notebook expects the CSV at `/content/covid_19_clean_complete.csv` in the Colab runtime. To run it, download the CSV from this repository and upload it to the Colab Files panel at that path, then run the cells from top to bottom.

## Technologies

- Python
- Pandas and NumPy
- Plotly Express
- Prophet
- Scikit-learn
- Google Colab

The repository includes `requirements.txt` with the main Python dependencies. In Colab, you can install them in a notebook cell with:

```python
%pip install pandas numpy plotly prophet scikit-learn
```

## Methodology

1. Inspect the raw data and validate column types, missing values, duplicates, dates, and case-count consistency.
2. Retain the original records and flag 18 records with negative active-case values and/or deaths plus recoveries exceeding confirmed cases, rather than silently deleting or altering them.
3. Aggregate the source data by date for global and India time series, and by country and WHO region for comparisons.
4. Use Plotly to explore cumulative counts and daily changes.
5. Fit Prophet to global cumulative confirmed cases. Evaluate on the final 14 historical days, then refit on all available observations to produce a seven-day forecast.

## Results

- Records: 49,068; countries/regions: 187; date range: 2020-01-22 to 2020-07-27.
- Data-quality checks flagged 18 records with inconsistent active-case values.
- The Prophet holdout evaluation produced MAE **844,762.48 cases** and RMSE **899,652.37 cases**.
- The seven-day forecast covers July 28 to August 3, 2020. These are historical model estimates, not observed counts or current COVID-19 predictions.

## Limitations

The data ends on July 27, 2020, and reflects historical reported counts, which may vary in completeness and reporting practices across countries. The holdout errors indicate that the baseline Prophet model underestimated actual cumulative counts during the test period. Forecasts and uncertainty intervals are exploratory estimates, not guarantees or public-health advice.

## Reproducibility

Run the notebook cells from top to bottom in Google Colab after making the CSV available at the path shown above. The notebook creates derived tables and a forecast CSV during execution. These are outputs from the single source dataset, not additional source datasets.

## Acknowledgment

This project was completed as part of a training assignment titled *Analyzing the Trends of COVID-19 with Python*.
