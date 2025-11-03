# SEO Content Quality & Duplicate Detector

A machine learning pipeline that analyzes web content for SEO quality assessment and duplicate detection using NLP techniques.

## Setup Instructions
```bash
git clone https://github.com/YOUR_USERNAME/seo-content-detector
cd seo-content-detector
pip install -r requirements.txt
jupyter notebook notebooks/seo_pipeline.ipynb
```

## Quick Start

1. The dataset is already included in `data/data.csv`
2. Open the Jupyter notebook: `notebooks/seo_pipeline.ipynb`
3. Run all cells sequentially
4. Results will be saved in the `data/` folder

## Key Decisions

- **BeautifulSoup with lxml parser**: Fast and reliable HTML parsing
- **Sentence Transformers (all-MiniLM-L6-v2)**: Efficient embeddings for semantic similarity
- **Cosine similarity threshold (0.80)**: Balances precision/recall for duplicate detection
- **Random Forest Classifier**: Handles non-linear relationships in quality features
- **Clear label criteria**: Non-overlapping rules ensure model learns distinct patterns

## Results Summary

- **Model Accuracy**: 0.78 (vs baseline 0.64)
- **Duplicate Pairs Found**: 3 pairs above 0.80 similarity
- **Thin Content**: 6 pages (10% of dataset)
- **Top Feature**: word_count (importance: 0.45)

## Limitations

- Simple rule-based labeling may not capture all quality nuances
- Embedding-based similarity may miss stylistic duplicates
- Model trained on small dataset; performance may vary on new domains
