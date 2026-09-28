## Individual worker:
Lan Xiao

## Deliverable

1. a web-based data [visualization](https://keeea.github.io/Hotel_Review_Analysis/) with **description** of the project and the **results**

2. a [document](https://github.com/MUSA-550-Fall-2021/final-project-lan_xiao/blob/main/whole_process.ipynb) stating the **description**, the **results**, the **technical methods** used in each step (collection, analysis and visualization), and all process **code**. 

## Kaggle authentication

Before starting Jupyter or importing `kaggle`, configure your own credentials
outside this repository using either:

- The `KAGGLE_USERNAME` and `KAGGLE_KEY` environment variables, inherited by the
  notebook kernel.
- A private `~/.kaggle/kaggle.json` file downloaded from your Kaggle account
  settings. On macOS/Linux, restrict access with `chmod 600 ~/.kaggle/kaggle.json`.

The notebook uses `KaggleApi.authenticate()` and does not set credentials itself.
Some Kaggle client versions authenticate during import, so configure credentials
before running the import cell. A `.env` file is not automatically loaded.
Never paste credentials into notebook cells, outputs, or committed files.

The notebook records Python 3.8.12; use a Kaggle client compatible with your Python
environment rather than assuming current packages reproduce this historical setup.
If credentials were exposed, expire/revoke the old key under **Legacy API
Credentials** in [Kaggle API settings](https://www.kaggle.com/settings/api).
Removing credentials from files or Git history does not revoke them.

## Technologies / Methods
### Collection 

1. Requesting data with API, involving the credential key

2. Wrangling data with geospatial joins, data shaping

### Analysis

1. Words frequency analysis on reviews

2. Sentiment analysis on reviews

3. Machine learning (random forest) on reviewer scores 

4. Two clustering analysis: one on hotels, the other on guests

### Visualization 

1. The **Interactive** word clouds by country

2. The **Interactive** dashboard based on hotel clustering
