# Bank Marketing Subscription Prediction

This project analyzes a bank's direct-marketing campaign data and builds binary classification models to predict whether a customer will subscribe to a term deposit. The Jupyter Notebook covers data inspection, exploratory analysis, preprocessing, model training, evaluation, business recommendations, and ethical and practical limitations.

## Dataset

The project uses the **Bank Marketing** dataset, specifically the complete `bank-full.csv` file with 45,211 campaign records. The data describes phone-based direct-marketing campaigns by a Portuguese banking institution. It was created by Paulo Cortez and Sérgio Moro and is distributed through the UCI Machine Learning Repository at <https://archive.ics.uci.edu/dataset/222/bank+marketing>; the included `bank/bank-names.txt` file provides the dataset description and citation details.

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
- Matplotlib
- seaborn
- scikit-learn
- Jupyter Notebook or JupyterLab

For example:

```bash
python -m pip install jupyter pandas matplotlib seaborn scikit-learn
```

NumPy is installed automatically as a dependency of pandas and scikit-learn; the notebook does not import it directly.

## Running the notebook

1. Keep `FinalProjectAppliedAI.ipynb` and `bank-full.csv` in the repository root.
2. Start Jupyter from the repository root with `jupyter notebook` or `jupyter lab`.
3. Open `FinalProjectAppliedAI.ipynb`.
4. Restart the kernel, then run all cells.

The recommended execution order is Parts A through J. Run the notebook from top to bottom because later sections reuse the cleaned data, preprocessing objects, fitted models, and predictions created in earlier sections.

## Results summary

Both models were evaluated on the same stratified test set of 9,043 clients, using the pre-call feature set that excludes `duration`.

| Model | Accuracy | Precision | Recall | F1-score |
| --- | --- | --- | --- | --- |
| Decision Tree | 0.7958 | 0.3005 | 0.5614 | 0.3914 |
| kNN (k = 5) | 0.8874 | 0.5529 | 0.1975 | 0.2911 |

**Recommended model: Decision Tree.** Only 11.70% of clients subscribed, so accuracy alone is misleading. kNN reaches the higher accuracy while finding just 209 of the 1,058 actual subscribers in the test set, against 594 for the Decision Tree. The Decision Tree therefore achieves the higher recall (0.5614 against 0.1975) and F1-score (0.3914 against 0.2911), and it is also easier to explain, because its predictions reduce to a set of rules at most five levels deep with readable feature importances. Its trade-off is a larger number of false positives (1,383 against 169), so kNN remains preferable if avoiding unnecessary contacts matters more than finding subscribers.

The strongest historical segment is a successful previous campaign outcome (`poutcome = success`) at a 64.73% subscription rate across 1,511 clients, compared with an overall rate of 11.70%. These segment rates describe associations observed in past campaign data, not proven causes.

## Repository layout

- `FinalProjectAppliedAI.ipynb`: complete analysis and modeling workflow
- `bank-full.csv`: full dataset used by the notebook
- `bank/bank-names.txt`: dataset description and citation information
- `bank/bank.csv`: smaller sample supplied with the dataset, not used by the notebook

## Project outputs

The notebook produces data-quality checks, exploratory summaries and visualizations, pre-call Decision Tree and kNN models, test-set metrics and confusion matrices, customer-segment subscription rates, Decision Tree feature importance, error analysis, a model recommendation, campaign recommendations, business interpretation, and a concise discussion of ethics, limitations, and practical risks.
