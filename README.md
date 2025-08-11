# QSR Menu Recommendation System

This project implements a recommendation system for a Quick Service Restaurant (QSR) chain using transaction data, customer demographics, and seasonal trends.

## Contents

- **Data Loading & Preprocessing**: Reads transaction, customer, and store data; normalizes and cleans item names.
- **Model Training & Validation**: Builds item-item co-occurrence similarity lists, store-level popularity metrics, and optional association rules using FP-Growth.
- **Prediction Pipeline**: Generates top-k menu recommendations for given customer orders and stores, optimized for Recall@3.

## Requirements

Install dependencies using:

```bash
pip install -r requirements.txt
```

## Usage

1. Upload the dataset files (`order_data.csv`, `customer_data.csv`, `store_data.csv`, `test_data_question.csv`) into your working directory (e.g., `/content/sample_data` in Google Colab).
2. Open `WWT_Unravel_2025_Recommendation System.ipynb` in Jupyter Notebook or Google Colab.
3. Run all cells sequentially to preprocess data, train the model, and generate predictions.
4. The output sheet will be saved in the working directory.

## Notes

- Ensure sufficient runtime memory in Google Colab when running on the full dataset.
- For faster FP-Growth, limit transactions to top-N most frequent items and increase `min_support`.
- Co-occurrence similarity computation uses sparse matrices for memory efficiency.

## Output

The notebook produces:
- `<Teamname>_Recommendation_Output.csv`: Top-k recommendations for test queries.
