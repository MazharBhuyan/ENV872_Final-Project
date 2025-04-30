# README: Ulaanbaatar PM2.5 Dataset (2015–2025)

## Source
This dataset was collected from the U.S. Embassy in Ulaanbaatar, Mongolia, through the U.S. Environmental Protection Agency’s (EPA) AirNow platform. The AirNow system provided hourly air quality monitoring data until its service was discontinued for this location in February 2025. All records were archived before shutdown.

## Description
The dataset contains hourly PM2.5 (fine particulate matter ≤2.5 µm) concentration measurements recorded by a reference-grade instrument located at the U.S. Embassy in central Ulaanbaatar. The monitor captures pollution patterns highly influenced by winter coal combustion, domestic heating, and meteorological effects like temperature inversions.

## Time Coverage
- **Start:** January 1, 2015, 01:00 (Local Time)
- **End:** February 1, 2025, 00:00 (Local Time)

## File Format
Each file is a CSV named:
```
Ulaanbaatar_PM2.5_<YEAR>_YTD.csv
```

## Data Columns
All files share the following structure:

- `Site`: Monitoring site (`U.S. Embassy`)
- `Parameter`: Always `PM2.5`
- `Date (LT)`: Local timestamp (Asia/Ulaanbaatar, UTC+8)
- `Year`, `Month`, `Day`, `Hour`: Date/time components
- `NowCast Conc.`: Real-time weighted concentration (µg/m³)
- `AQI`: U.S. Air Quality Index (AQI) value
- `AQI Category`: AQI label (e.g., Good, Unhealthy)
- `Raw Conc.`: Measured PM2.5 (µg/m³)
- `Conc. Unit`: Units (always `µg/m³`)
- `Duration`: Typically `1 Hour`
- `QC Name`: Quality control information or flags

## Notes
- All timestamps are in local time (Asia/Ulaanbaatar, UTC+8).
- The data are consistent across years and ready for trend, exposure, and seasonal analysis.
- Minor gaps may occur due to maintenance or quality control filtering.
- As of February 2025, new data from this monitor is no longer available via AirNow.

## Suggested Citation
U.S. Embassy Ulaanbaatar & U.S. EPA. (2015–2025). *Hourly PM2.5 Data from Ulaanbaatar, Mongolia*. Retrieved via AirNow and archived prior to the platform's discontinuation.
