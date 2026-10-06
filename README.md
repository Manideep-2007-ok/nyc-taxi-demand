# nyc-taxi-demand

NYC taxi demand forecaster, in progress.

**Goal:** predict how many yellow taxi trips will start in each NYC zone, each hour.

## What's here so far

`nyc_taxi_demand.ipynb` builds the table the model will learn from:

1. Loads the January 2025 NYC TLC yellow taxi data (about 3.5 million trips).
2. Rounds each pickup time down to the hour (`hour_start`).
3. Drops stray rows whose dates fall outside January 2025.
4. Counts trips per hour per pickup zone (`PULocationID`). That gives 97,014 rows, which is the target the model will predict.

## Data

The data is not stored in this repo. The notebook downloads it directly from the
[NYC TLC trip record data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page) page
(Parquet file, `yellow_tripdata_2025-01.parquet`).

## Next steps

- Add more months of data (recent 2-3 years).
- Split train/test by time, not randomly.
- Build a simple baseline, then train a LightGBM model.
- Serve predictions with a small API.
