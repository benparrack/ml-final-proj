# Machine Learning Final Project

### Group Members:
- Claire Carroll
- Ben Parrack
- Caitlin Brogden

## Dataset Brainstorming:
1. [Cyber Attack Detection & Risk Prediction Dataset with 100k+ instances](https://www.kaggle.com/datasets/aiexplorer77/cyber-attack-detection-and-risk-prediction-dataset)
2. [Phishing URL Detection with 111K URLs, 22 Features](https://www.kaggle.com/datasets/sahandnamvar/phishing-url-detection-111k-urls-22-features)
3. [NFL Injury Reports Dataset (2009–2025) with 90k instances](https://www.kaggle.com/datasets/mansiaggarwal88/nfl-injury-reports-dataset-20092025)
4. [FAA Wildlife Strike Database](https://wildlife.faa.gov/home)
5. [PhiUSIIL Phishing URL (UCI)](https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset)
6. [Endometriosis Dataset with 10k instances](https://www.kaggle.com/datasets/michaelanietie/endometriosis-dataset/data)

## Setup

Python 3.12 or newer (`python3 --version`; get it from [python.org](https://www.python.org/downloads/) if it's older), git, and the accepted GitHub invite to this repo.

### macOS / Linux

```bash
git clone https://github.com/benparrack/ml-final-proj.git
cd ml-final-proj
python3 -m venv .venv                 # creates the project's virtual environment
source .venv/bin/activate             # your prompt now starts with (.venv)
pip install -r requirements.txt       # installs Jupyter, pandas, scikit-learn, etc.
nbstripout --install                  # strips notebook outputs on commit (prevents merge conflicts)
jupyter lab                           # opens in your browser
```

### Windows (PowerShell)

```powershell
git clone https://github.com/benparrack/ml-final-proj.git
cd ml-final-proj
py -3.12 -m venv .venv
.venv\Scripts\Activate.ps1            # if blocked, run once: Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
pip install -r requirements.txt
nbstripout --install
jupyter lab
```

**Pushing for the first time:** GitHub doesn't accept your account password over HTTPS. The easiest fix is to install the [GitHub CLI](https://cli.github.com/) and run `gh auth login` once, or use GitHub Desktop.

**Optional shortcut (macOS/Linux):** add this to `~/.bashrc` (or `~/.zshrc` on a Mac), with your own path, and then just type `final` to jump in with the venv active:

```bash
alias final='cd ~/path/to/ml-final-proj && source .venv/bin/activate'
```

## Everyday workflow

```bash
cd ml-final-proj
source .venv/bin/activate             # Windows: .venv\Scripts\Activate.ps1
git pull                              # ALWAYS pull before you start
pip install -r requirements.txt       # only needed if requirements.txt changed
jupyter lab
# ...work, save...
git add <files you changed>
git commit -m "Short description of what you did"
git push
```

**Ground rules to avoid merge conflicts:**
- One notebook per person (e.g. `notebooks/01_eda.ipynb`, `notebooks/02_baseline.ipynb`). Don't edit someone else's notebook without telling them first.
- Put code that several notebooks share in `.py` files under `src/`. Those merge cleanly.
- Added a package? Run `pip install <package>`, then `pip freeze > requirements.txt`, then commit `requirements.txt` and tell the group.
- Notebook outputs (plots, tables) are stripped on commit, so re-run a notebook after pulling to see its results.
