# BT4012 Kaggle Competition: Fraudulent Bitcoin Transaction Detection

The notebook `e1397982.ipynb` contains the full pipeline, from data preparation to the final submission.

## Setup

Install the required libraries listed in `requirements.txt`:

```
pip install -r requirements.txt
```

## Data

Download the competition files and place them in a folder named `data` next to the notebook:

```
data/
├── train.csv
├── test.csv
├── txs_edgelist.csv
```

## Running

Open `e1397982.ipynb` and run all cells from top to bottom. The notebook creates a folder `outputs_final` containing:

- `submission_16.csv`: my best submission on both the public and private leaderboards (the neighbour-difference model with the post-shutdown adjustment)
- `submission_7.csv`: an earlier variant that adds large-difference shares (the share of neighbours that differ strongly from a transaction) to the neighbour-difference features*

The two submission files are saved under the same names as on the Kaggle leaderboard so they are easy to match up.

Sections 1–7 produce both submissions; section 8 is evaluation only and can be skipped if you only need the submission files.

All random seeds are fixed, so rerunning the notebook gives the same files every time, and `submission_16.csv` matches the file I submitted.

*Note: submission_7 was selected as my second final submission by mistake (I had intended LightGBM on stable features); this did not affect my final result, since submission_16 scored highest on both leaderboards out of all my submission. Sumbission_7 comes from an earlier version of this notebook, when I was experimenting with averaging over different numbers of seeds and with the model settings, and its seeds were not fixed, so the reproduced file differs slightly from the original.