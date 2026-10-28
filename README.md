# Project 6: Predicting River Baseflow with Multiple Linear Regression

CS 5830/6830 course project. We apply multiple linear regression to the RRCA baseflow dataset from the Republican River basin (Colorado, Nebraska, Kansas) to predict monthly baseflow at 46 gaging stations (42 river segment ids) from 1939 to 2000, and to measure how precipitation, evapotranspiration, and irrigation pumping relate to it.

## Key findings

* Climate, pumping, and date alone explain little of pooled baseflow (R2 about 0.12 on a random split) because the stations sit on very different flow scales.
* Most of the apparent skill from adding each river's identity comes from knowing the river's average size: predicting only each station's average already scores about 0.78 on random months.
* Trained on 1939 to 1989 and tested on 1990 to 2000, a relative model (baseflow as a share of each station's normal flow) scores R2 0.78, against 0.61 for each station's average, and cuts the typical error from 10.7 to 8.1 cfs. About three quarters of that gain is the downward drift over time.
* Evapotranspiration lowers baseflow and precipitation raises it (cluster-robust p below 0.001 and about 0.002).
* At ten stations with complete records, baseflow fell from about 23 cfs (1945 to 1949) to about 14 cfs (1995 to 1999), a 38 percent drop, while pumping grew from near zero. However, once errors are clustered by station, the pumping effect cannot be separated from the time trend (p about 0.28), so the data shows the two moved together, not that pumping caused the decline.

## Files

* `project6.ipynb` is the full analysis notebook.
* `project6_report.pdf` is the project report.
* `requirements.txt` lists the Python dependencies.
* `RRCA_baseflow.csv` is the dataset. Download it from the course page and place it in this folder next to the notebook.

## How to run

1. Create and activate a virtual environment (Python 3.12 or newer):

   ```
   python3.12 -m venv .venv
   source .venv/bin/activate
   ```

2. Install the dependencies:

   ```
   pip install -r requirements.txt
   ```

3. Open `project6.ipynb` in Jupyter or VS Code, select the `.venv` interpreter as the kernel, and run all cells (Kernel, Restart and Run All). The notebook reads `RRCA_baseflow.csv` by relative path, so run it from this folder.