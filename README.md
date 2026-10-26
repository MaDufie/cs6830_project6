# Project 6: Predicting River Baseflow with Multiple Linear Regression

CS 5830/6830 course project. We apply multiple linear regression to the RRCA baseflow dataset from the Republican River basin (Colorado, Nebraska, Kansas) to predict monthly baseflow in 42 river segments from 1939 to 2000, and to measure how precipitation, evapotranspiration, and irrigation pumping relate to it.

## Key findings

* Climate, pumping, and date alone explain little of pooled baseflow (test R2 about 0.12) because the 42 segments sit on very different flow scales.
* Adding segment identity as a one hot encoded categorical variable raises test R2 to about 0.82 and cuts the typical error from 55 to 25 cfs.
* In 69 percent of segments with irrigation pumping, more pumping is significantly associated with lower baseflow. For a fixed cohort of ten long record segments, average baseflow fell from about 14 cfs in the 1940s to about 8 cfs by the late 1990s while pumping grew from near zero.

## Files

* `project6.ipynb` is the full analysis notebook.
* `project6_report.pdf` is the project report (`project6_report.docx` is the editable version).
* `project6_slides.pptx` is the presentation deck.
* `RRCA_baseflow.csv` is the dataset. If it is not in the repository, download it from the course page and place it in this folder next to the notebook.

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

## Team

[Team member names]

Presentation slides: [insert Google Slides link]
