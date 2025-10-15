### Machine Learning Online Bootcamp (MLOB)

Welcome to the Machine Learning Online Bootcamp workspace. This repository contains session-wise notebooks, datasets, practice projects, and a simple Flask web app built during the course.

- **Course outline**: see `Course_Outline.pdf`
- **Slides/handouts**: in `Sessions/Day13` and `Sessions/Day14`
- **Demo app**: a Flask app in `Sessions/Day15` that predicts mobile prices

---

## Getting started

### Prerequisites
- Python 3.10+ recommended
- Git (optional)

### Setup
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

If you are on macOS/Linux, activate with:
```bash
source .venv/bin/activate
```

---

## Running the Day 15 demo app (Mobile Price Predictor)
This is a small Flask project demonstrating data preprocessing and inference using a pre-trained SGD Regressor.

Files of interest:
- `Sessions/Day15/app.py` — Flask server with preprocessing and prediction route
- `Sessions/Day15/templates/index.html` — Bootstrap UI for input & prediction
- `Sessions/Day15/sgd_regressor_model.pkl` — trained model (joblib)
- `Sessions/Day15/regression_mobile_price.csv` — source dataset used to align preprocessing

Run locally:
```bash
cd Sessions/Day15
python app.py
```
Then open `http://127.0.0.1:5000` in your browser.

Notes:
- The app expects the dataset and model at the relative paths shown above.
- Preprocessing mirrors the notebook pipeline: imputations, IQR-based outlier handling, categorical encodings, and standard scaling.

---

## Repository structure

Top-level:
- `Course_Outline.pdf` — complete course outline
- `requirements.txt` — Python dependencies for notebooks and the demo app
- `Sessions/` — session-wise materials

By sessions (high level):
- `Day1/` — Intro and course logistics (`topics.txt`)
- `Day2/` — Python basics (notebook)
- `Day3/` — Python continuation (notebook)
- `Day4/` — Python core structures: `Lists`, `Dictionaries` (notebooks)
- `Day5/` — `Sets`, `Tuples` (notebooks)
- `Day6/` — Functions, lambda, map, filter (notebooks, `sample.txt`)
- `Day7/` — Practice with Python (`student_grades.txt`)
- `Day8/` — OOP: classes, inheritance, polymorphism, encapsulation, abstraction (notebooks)
- `Day9/` — `Numpy_basic.ipynb`, `Pandas.ipynb`, sample `series.csv`
- `Day10/` — Data visualization (matplotlib/seaborn), anatomy images, practice project notebook
- `Day11/` — Kaggle Competition brief (`Kaggle_Competition.txt`)
- `Day12/` — Data preprocessing (notebook)
- `Day13/` — Statistics for ML + PDFs on analytics/decision making
- `Day14/` — Unsupervised learning visuals; Linear Regression module with images, `LR.ipynb`, `Salary_Data.csv`; supporting PDFs
- `Day15/` — Model training notebook, Flask app and artifacts for regression on mobile prices

Images and PDFs in the session folders support the theory and examples presented in each day.

---

## Learning outcomes
- Solid Python fundamentals for data work
- Numpy and Pandas essentials for data wrangling
- Data visualization best practices
- Data preprocessing: cleaning, encoding, outlier handling, scaling
- Introductory statistics for ML
- Supervised learning: Linear Regression (and variants)
- Unsupervised learning overview
- Model deployment basics with a minimal Flask app

---

## Working with notebooks
You can run any `.ipynb` using Jupyter/Lab/VS Code:
```bash
pip install -r requirements.txt
jupyter lab  # or: jupyter notebook
```

Datasets are stored alongside the notebooks (e.g., `Sessions/Day14/LR/Salary_Data.csv`, `Sessions/Day15/regression_mobile_price.csv`).

---

## Contributing / extending
- Add new sessions under `Sessions/DayX/`
- Keep datasets small and colocated with their notebooks
- Update `requirements.txt` when new libraries are introduced
- If you change the Day 15 preprocessing, retrain the model and re-save `sgd_regressor_model.pkl`

---

## License
See `LICENSE` for details.


