# Pokémon Battles Prediction

A Machine Learning project for the **Fundamentals of Data Science (FDS)** course at Sapienza University of Rome.

The goal is to predict the outcome of Pokémon battles using information about the player's team, the opponent's lead Pokémon, type matchups, and held items.

## Competition

**Kaggle competition:** [FDS Pokémon Battles Prediction 2026](https://www.kaggle.com/competitions/fds-pokemon-battles-prediction-2026)

The task is a binary classification problem:

- `1` — the player wins.
- `0` — the player loses.

## Dataset

The competition provides battle data in JSONL format.

The training data contains 10,000 battles, while the test data contains 5,000 battles.

Each battle includes information about:

- The player's six Pokémon.
- The opponent's lead Pokémon.
- The battle timeline.
- The battle outcome (training data only).

**Note:** The competition datasets are not stored in this repository. Obtain them through the permitted competition data source and place them in the project directory before running the notebook.

## Repository Structure

```text
Pokemon-Competition/
├── FDS_Pokemon_Battles_Prediction.ipynb
├── starter-notebook.ipynb
├── sample_submission.csv
├── submission.csv
├── type_chart_gen2.csv
├── .gitignore
└── README.md
```

- `FDS_Pokemon_Battles_Prediction.ipynb` — main notebook for data exploration, feature engineering, model training, and evaluation.
- `starter-notebook.ipynb` — original starter notebook provided for the competition.
- `sample_submission.csv` — example of the required submission format.
- `submission.csv` — local submission file.
- `type_chart_gen2.csv` — Pokémon type-effectiveness chart.
- `.gitignore` — specifies files that should not be tracked by Git.

## Feature Engineering

The current feature engineering pipeline extracts information from several parts of each battle:

- **Team statistics:** average base stats of the player's six Pokémon.
- **Opponent statistics:** base stats of the opponent's lead Pokémon.
- **Pokémon types:** type counts for the player's team and type indicators for the opponent's lead.
- **Type matchups:** counts of advantageous, disadvantageous, and neutral matchups.
- **Held items:** counts of items held by the player's team.

The engineered features are combined into a single training matrix. The target variable `player_won` is separated from the input features.

**Assumption:** Unlisted type-effectiveness combinations are currently treated as neutral (`1.0`). This is a working assumption that should be verified against the competition's data specification.

## Models and Evaluation

The project starts with a baseline approach and evaluates model performance using a validation split.

The current baseline models include:

- Dummy Classifier — reference performance.
- Logistic Regression — an initial machine learning model.

Evaluation includes accuracy and a confusion matrix. Additional models and feature engineering improvements may be explored as the project develops.

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/diana-s368/Pokemon-Competition.git
cd Pokemon-Competition
```

### 2. Prepare the data

Obtain `train.jsonl` and `test.jsonl` through the permitted competition data source and place them in the project directory.

The dataset files are excluded from Git using `.gitignore`.

### 3. Install dependencies

The project uses Python and common data science libraries. The exact dependencies may evolve during development.

Typical dependencies include:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

Install any additional packages required by the notebook.

### 4. Run the notebook

Open the main notebook in Jupyter or Visual Studio Code:

```text
FDS_Pokemon_Battles_Prediction.ipynb
```

Run the cells in order, starting with data loading and continuing through feature engineering, model training, and evaluation.

## Tools and Technologies

- Python
- Jupyter Notebook
- pandas and NumPy
- scikit-learn
- Matplotlib and Seaborn
- Git and GitHub
- Kaggle

## Team Project

This repository is used for collaboration on the FDS Pokémon Battles Prediction competition.

Contributors can clone the repository, work on separate features or models, and submit changes through Git.

## Project Status

**In progress.** Data exploration, feature engineering, and baseline model evaluation are underway. The final modelling approach and competition submissions will be updated as development continues.

## License and Data Usage

This repository is intended for educational and academic use. Competition data remains subject to Kaggle's competition rules and must not be redistributed unless permitted by those rules.
