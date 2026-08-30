# Bank Marketing Subscription Prediction

This project analyzes a bank's direct-marketing campaign data and builds binary classification models to predict whether a customer will subscribe to a term deposit. The Jupyter Notebook covers data inspection, exploratory analysis, preprocessing, model training, evaluation, business recommendations, and ethical and practical limitations.

## Dataset

The project uses the **Bank Marketing** dataset, specifically the complete `bank-full.csv` file with 45,211 campaign records. The data describes phone-based direct-marketing campaigns by a Portuguese banking institution. It was created by Paulo Cortez and Sérgio Moro and is distributed through the UCI Machine Learning Repository; the included `bank/bank-names.txt` file provides the dataset description and citation details.

The target variable is `y`:

- `yes`: the customer subscribed to a term deposit
- `no`: the customer did not subscribe

## Models

The required classification models are:

- Decision Tree
- k-Nearest Neighbors (kNN)

The main pre-call model excludes `duration`, because the duration of a future call is not available before the customer is contacted. The train/test split and model setup use `random_state=42` where applicable for reproducibility.

## Python requirements

Use a recent Python 3 environment with Jupyter and the main libraries used by the notebook:

- pandas
- NumPy
- Matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook or JupyterLab

For example:

```bash
python -m pip install jupyter pandas numpy matplotlib seaborn scikit-learn
```

## Running the notebook

1. Keep `FinalProjectAppliedAI.ipynb` and `bank-full.csv` in the repository root.
2. Start Jupyter from the repository root with `jupyter notebook` or `jupyter lab`.
3. Open `FinalProjectAppliedAI.ipynb`.
4. Restart the kernel, then run all cells.

The recommended execution order is Parts A through J. Run the notebook from top to bottom because later sections reuse the cleaned data, preprocessing objects, fitted models, and predictions created in earlier sections.

## Repository layout

- `FinalProjectAppliedAI.ipynb`: complete analysis and modeling workflow
- `bank-full.csv`: full dataset used by the notebook
- `bank/bank-names.txt`: dataset description and citation information
- `bank/bank.csv`: smaller sample supplied with the dataset, not used by the notebook

## Project outputs

The notebook produces data-quality checks, exploratory summaries and visualizations, pre-call Decision Tree and kNN models, test-set metrics and confusion matrices, customer-segment subscription rates, Decision Tree feature importance, error analysis, a model recommendation, campaign recommendations, business interpretation, and a concise discussion of ethics, limitations, and practical risks.
