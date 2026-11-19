# How much value does a used car keep?

Machine Learning final project, DIS Stockholm, Fall 2026: Claire Carroll, Ben Parrack, Caitlin Brogden.

We predict a used car's **value retention ratio**: its advertised price divided by the entry-level new price of the same model in the year it was registered. It's a regression problem on 223,216 UK used-car adverts from the [DVM-CAR dataset](https://deepvisualmarketing.github.io/) (Huang et al., 2022).

Proposal: [Google Doc (view only)](https://docs.google.com/document/d/1s15pZi5cLb2GOl4LVGZxnm_1rtAuXFJo37_QhaX5ygs/edit?usp=sharing)

## Setup

You need Python 3.12+.

```bash
git clone https://github.com/benparrack/ml-final-proj.git
cd ml-final-proj
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Data

The data isn't in the repo. Download the tables from [figshare](https://figshare.com/articles/figure/DVM-CAR_Dataset/19586296/2) and put the CSVs in a `data/` folder at the top of the repo. The notebook needs `Ad_table (extra).csv` and `Price_table.csv`.

## Run

```bash
jupyter lab
```

## Edits

In .venv terminal

To stage commits (add changes files), type 
```bash
git status                          # check what changed before you commit
git switch -c Branch name       # new branch (your uncommitted changes come with you)
git add -A // or git add (filepath of changes you want to add)
git commit -m "Fix data paths so the notebook runs from notebooks/"
git pull origin main                # bring in teammates' latest main (needs `origin main` on a new branch)
git push -u origin Branch name   # create the branch on GitHub
```

Explanation: For all new changes, to avoid merge issues we create a new branch, you create the name taking the place of my-branch-name, and push your changes to there. From this branch, on github you create a merge request and review it to see if their are any merge issues and we can troubleshoot or merge from there

## Future changes

Clearly defined the problem (classification, regression, clustering, forecasting, etc.)
- [x] Specified the target variable
- [ ] Identified key evaluation metrics (accuracy, F1, ROC-AUC, MSE, MAE, etc.)
- [ ] Described the success criteria and what “good performance” means
- [x] Outlined assumptions and constraints (data limits, cost, fairness, real-time needs)
- [x] Found relevant literature on similar datasets and explored the approach
- [x] Discovered a novel approach to the dataset / problem

Explored the dataset (shape, types, distributions)
- [x] Identified data quality issues
- [ ] Examined class balance and apply techniques as needed (SMOTE, class weights etc)
- [ ] Investigated feature correlations or interactions
- [ ] Visualized your data appropriately (histograms, boxplots, heatmaps, etc.)
- [ ] Handle missing values, outliers, and noise
- [ ] Standardisation of numerical features
- [ ] Encoding categorical variables
- [ ] Feature engineering / dimensionality reduction if needed
- [ ] Time series-specific pre-processing (if applicable)
- [ ] Image / text data processing (if applicable)

Created train / test / validation splits
- [ ] Implemented at least one simple baseline (mean predictor, logistic regression, etc.)
- [ ] Compared performance of more complex models against the baseline
- [ ] Tuned hyperparameters (GridSearch, RandomSearch)
- [ ] Ensured reproducibility (random seeds, consistent preprocessing)
- [ ] Evaluated using appropriate metrics for the task
- [ ] Checked for overfitting/underfitting
- [ ] Interpreted and visualised results (confusion matrix, ROC curves, feature importance, etc.)
- [ ] Noted limitations and future improvements
- [ ] Compared results to previous work / research / state-of-the-art





Open `notebooks/Proposal.ipynb` and run all cells. It checks and cleans the data, builds the target, and saves the result as `data/cars_joined.csv`.
