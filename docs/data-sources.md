# Data sources

## Primary sources

### 1. Provincial cumulative confirmed cases
- **Source:** dsfsi/covid19za (Data Science for Social Impact, University of Pretoria)
- **Compiled from:** NICD and Department of Health statements
- **File:** `data/raw/covid19za_provincial_confirmed.csv`
- **URL:** https://raw.githubusercontent.com/dsfsi/covid19za/master/data/covid19za_provincial_cumulative_timeline_confirmed.csv
- **Licence:** CC BY-SA 4.0
- **Coverage:** Provincial cumulative confirmed cases over time

### 2. Provincial cumulative deaths
- **Source:** dsfsi/covid19za
- **File:** `data/raw/covid19za_provincial_deaths.csv`
- **URL:** https://raw.githubusercontent.com/dsfsi/covid19za/master/data/covid19za_provincial_cumulative_timeline_deaths.csv
- **Licence:** CC BY-SA 4.0

### 3. Provincial vaccination timeline
- **Source:** dsfsi/covid19za
- **File:** `data/raw/covid19za_provincial_vaccination.csv`
- **URL:** https://raw.githubusercontent.com/dsfsi/covid19za/master/data/covid19za_provincial_cumulative_timeline_vaccination.csv
- **Licence:** CC BY-SA 4.0

## Notes
- All raw files are kept unchanged in `data/raw/`.
- Cleaning and merging will be done in notebooks and saved to `data/processed/`.
- Date range and any issues found during loading will be documented here or in the notebook.

## Last updated
- Sources downloaded: 11 October 2026