# Consumer Complaint NLP Analysis (CFPB)

This repository contains an NLP workflow to analyze unstructured consumer complaint narratives (CFPB Consumer Complaint Database).  
Goal: identify frequently discussed complaint topics and compare different vectorization and semantic topic extraction techniques.

## Dataset
- Source: CFPB Consumer Complaint Database (public dataset)
- Used field: complaint narrative text (records without narratives removed)
- Note: the raw dataset file is not included in this repository.

## Workflow (Phase 2)
1. Load and inspect the dataset (basic EDA)
2. Text preprocessing (cleaning pipeline)
   - lowercasing, URL/special character removal
   - tokenization and stopword removal
   - lemmatization (spaCy)
   - removal of anonymization placeholders (e.g., "xxxx")
3. Vectorization (2 approaches)
   - TF-IDF (frequency-based)
   - Sentence embeddings (semantic)
4. Topic extraction (2 approaches)
   - LDA topic modeling (topic count selected via coherence score c_v)
   - KMeans clustering on embeddings
5. Short discussion of results and limitations

## How to run
### Option A: Google Colab
Open the notebook in Colab and run the cells step by step:
- `notebooks/01_nlp_topics.ipynb`

### Option B: Local
```bash
pip install -r requirements.txt
