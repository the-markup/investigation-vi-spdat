# Los Angeles's Homelessness Scoring System

This repository contains data and code to reproduce the findings featured in our story, "[L.A.’s Scoring System for Subsidized Housing Gives Black and Latino People Experiencing Homelessness Lower Priority Scores](TK)."

Our methodology is described in "[How We Investigated L.A.’s Homelessness Scoring System](TK)."

We cleaned the original CRPA response from the Los Angeles Homeless Services Authority using [`notebooks/0-clean.ipynb`](notebooks/0-clean.ipynb) to create a cleaned file called [`data/assessments.csv`](data/assessments.csv), which we used for our analyses. Outputs for our analyses, which were used for graphics in our story, are available in the [`output`](output) folder.

Jupyter notebooks used for data preparation and analysis are in the [`notebooks`](notebooks) folder.

## Notebooks

### [`notebooks/0-clean.ipynb`](notebooks/0-clean.ipynb)

This notebook takes the original CPRA response, which we did not include in this repo due to privacy concerns, and outputs a cleaned version called `data/assessments.csv`, which we use in our analyses. 

### [`notebooks/1-analysis.ipynb`](notebooks/1-analysis.ipynb)

This notebook takes [`data/assessments.csv`](data/assessments.csv) and performs several analyses, including chi-square tests for both the Next Step Tool and the CES Survey Part 1. It outputs several `.csv` files we use for graphics in both our story and methodology, all of which are available in the [`output`](output) folder.

### [`notebooks/2-regressions.ipynb`](notebooks/2-regressions.ipynb)

This notebook takes [`data/assessments.csv`](data/assessments.csv) and performs linear and logistic regressions for both the Next Step Tool and the CES Survey Part 1. For more details, please refer to [our methodology](TK).

### [`notebooks/3-subscores-note.ipynb`](notebooks/3-subscores-note.ipynb)
This notebook takes [`data/assessments.csv`](data/assessments.csv) and calculates two sets of subscores: one using all assessmesnts, and another using only assessments without discrepancies between our calculated score and the actual score in the dataset. For more details, please refer to [our methodology](TK).


### [`notebooks/4-analysis-note.ipynb`](notebooks/4-analysis-note.ipynb)
This notebook takes [`data/assessments.csv`](data/assessments.csv) and performs everything done in [`notebooks/1-analysis.ipynb`](notebooks/1-analysis.ipynb), but instead of using `TOTAL_SCORE` (including to calculate `Acuity`), it uses `CALC_TOTAL_SCORE`. It outputs several `.csv` files, all of which are available in the [`output/calc_total_score_note`](output/calc_total_score_note) folder.



## Reproducibility

All notebooks have already been run. 

We used Python 3.9. A list of libraries we used, and which versions they are, is available in [`requirements.txt`](requirements.txt). If you already have Python 3 installed, you can install these packages by running `pip install -r requirements.txt`.

You can then re-run our notebooks by running `nbexec notebooks/1-analysis.ipynb notebooks/2-regressions.ipynb`.

## Data

A data dictionary for [`data/assessments.csv`](data/assessments.csv) can be found in [`docs/assessments-dict.md`](docs/assessments-dict.md). 

While we do not include the original CPRA response we recieved from LAHSA due to privacy concerns, we include a data dictionary at [`docs/cpra-response-dict.md`](docs/cpra-response-dict.md).
