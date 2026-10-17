# COVID-19 Trend Analysis with Python

A data science project analyzing historical COVID-19 trends using Python, Pandas, Plotly, and Prophet.

## Project objectives

- Clean and validate COVID-19 case data.
- Analyze confirmed cases, deaths, recoveries, and active cases over time.
- Create interactive Plotly visualizations for global and India-focused exploration.
- Forecast the next seven days using Prophet and evaluate the forecast with a chronological holdout.
- Document findings and limitations clearly.

## Dataset

The current dataset is `covid_19_clean_complete.csv`, containing historical observations by date and country/region, with geographic fields and confirmed, death, recovered, and active case counts. The observed time range and data-quality results will be confirmed in the notebook.

Due to file size and provenance considerations, the raw dataset may be kept outside the repository and uploaded to Google Colab when running the notebook. Do not commit large raw data files unless their licensing and repository suitability have been checked.

## Tools

- Python
- Pandas and NumPy
- Plotly
- Prophet
- Google Colab

## Running the project

1. Open the notebook (to be added) in Google Colab.
2. Upload `covid_19_clean_complete.csv` when prompted, or configure an approved data source.
3. Run notebook cells from top to bottom.

## Methodology

The analysis will distinguish cumulative counts from daily changes. Forecasts will be interpreted as exploratory estimates from historical data, not as public-health predictions or medical advice. Data quality checks will be documented before interpretation.

## Project status

Initial repository setup. Notebook, cleaning workflow, interactive analysis, and forecasting will be added incrementally.

## Acknowledgment

This project is based on a training assignment titled *Analyzing the Trends of COVID-19 with Python*.