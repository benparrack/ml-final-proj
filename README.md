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
git switch -c fix-data-paths        # new branch (your uncommitted changes come with you)
git add -A
git commit -m "Fix data paths so the notebook runs from notebooks/"
git pull origin main                # bring in teammates' latest main (needs `origin main` on a new branch)
git push -u origin fix-data-paths   # create the branch on GitHub
```

Explanation: For all new changes, to avoid merge issues we create a new branch, you create the name taking the place of my-branch-name, and push your changes to there. From this branch, on github you create a merge request and review it to see if their are any merge issues and we can troubleshoot or merge from there



Open `notebooks/Proposal.ipynb` and run all cells. It checks and cleans the data, builds the target, and saves the result as `data/cars_joined.csv`.
