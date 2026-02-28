# Helsinki Digital Humanities Hackathon 2025

Colonial discourse analysis in Early Modern British newspapers — studying representations of places, people, and trade goods.

## Overview

Research project exploring how colonial systems are represented in Early Modern newspaper discourse. Using NLP techniques on the Burney and Nichols newspaper collections, we analyze the representation of geographical places, famous figures, and colonial trade goods (sugar, tobacco) through named entity recognition, n-gram extraction, and geographic co-occurrence mapping.

## Tech Stack

- **NLP:** spaCy (NER), NLTK
- **Data Processing:** Pandas, NumPy
- **Geospatial:** GeoPandas, QGIS
- **Package Manager:** UV

## Research Tracks

### 1. Famous Figures Exploration
Extract historically significant individuals from colonial-era newspapers using NER, filtered by country mentions.

```bash
python -m src.preprocessing.detect_words
python -m src.preprocessing.extract_country_paragraphs
python -m src.preprocessing.ner
```

### 2. Colonial Goods in Advertisements
Analyze discourse surrounding colonial goods through tri-gram extraction and noun/adjective categorization.

```bash
python -m src.EDA.count_ngrams
python -m src.EDA.generate_advertisement_noun_adj_list
```

### 3. Colonial Geography
Map co-occurrence patterns between trade goods and geographic locations, using the DK Atlas of World History Gazetteer to create spatial visualizations.

```bash
python -m src.preprocessing.detect_words
python -m src.EDA.get_cooccurence_frequencies
```

## Getting Started

```bash
# Install uv: https://docs.astral.sh/uv/getting-started/installation/
uv sync

# Download data
bash scripts/get_data.sh bl_newspapers_meta.csv json_res.tar

# Preprocess (OCR cleaning, spelling correction, article segmentation)
python -m src.preprocessing.clean_dataset
```

All code should be run from project root.

## Data

Newspaper data from the Burney and Nichols collections. Available files:
- `bl_newspapers_meta.csv` — Collection metadata
- `json_res.tar` — Newspaper details with OCRed texts
- `bln-places.csv` — Publication locations with coordinates
- `burney-titles.csv` / `nichols-titles.csv` — Title and issue date listings

## Context

Group project at the Helsinki Digital Humanities Hackathon 2025. Combines computational text analysis with historical research on British colonial trade networks and their newspaper representations.
