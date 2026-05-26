# Customer Sentiment & NLP Behavioral Analysis
### Amazon Melatonin Product Reviews — Dose-Level Analysis

## Overview
Most melatonin research groups products by brand. This project 
takes a different approach — grouping 4,984 Amazon customer reviews 
by dosage level (1mg to 20mg) to uncover how customer sentiment, 
behavioral patterns, and side effects actually vary across doses.

Raw data came in 8 separate messy Excel files totaling 41,251 rows. 
The project covers the full analytics pipeline: data wrangling, 
EDA, sentiment analysis, and NLP-based theme extraction.

---

## Tools & Technologies
- **Python** — core analysis language
- **Pandas** — data cleaning, merging, transformation
- **NumPy** — numerical operations
- **Regex (re)** — NLP pattern extraction and theme matching
- **Matplotlib** — visualizations (heatmaps, bar charts, pie charts)
- **Collections (Counter)** — bigram frequency analysis

---

## Dataset
| Dose | Brand | Raw Rows |
|------|-------|----------|
| 1mg | Natrol | 4,492 |
| 3mg | OLLY | 1,307 |
| 5mg | OLLY | 4,478 |
| 5mg | Natrol | 7,524 |
| 10mg | Natrol | 7,624 |
| 12mg | Carlyle | 9,554 |
| 12mg | Nature's Truth | 936 |
| 20mg | Nature's Perfect Night | 5,336 |

**Total raw rows:** 41,251
**Final clean dataset:** 4,984 unique reviews
**Dose groups:** 6 (1mg, 3mg, 5mg, 10mg, 12mg, 20mg)

---

## Project Workflow

### 1. Data Wrangling & Integration
- Loaded 8 separate Excel files and merged into one dataframe
- Assigned dose values from filenames as a new column
- Dropped irrelevant columns (Images, PageUrl, ProductLink)
- Handled null values — dropped rows with no review text
- Removed 35,874 duplicate reviews
- Parsed inconsistent ReviewDate formats using Regex
- Converted HelpfulCounts and ReviewScore to correct data types

### 2. Data Manipulation
- Extracted and verified dose values from product titles using Regex
- Added sentiment labels: Positive (4–5★), Neutral (3★), 
  Negative (1–2★)
- Added dose category groupings: Low (1–4mg), Medium (5–10mg), 
  High (11–20mg)

### 3. Dose Distribution Analysis
- Analyzed review volume and market share across all dose levels
- 5mg dominates the market at 25.2% of all reviews
- Medium dose products lead overall at 38.7% market share
- 3mg grew 3x between 2020 and 2024
- 20mg is the rarest dose at 7.9% of reviews

### 4. Sentiment Analysis by Dose
- Grouped all reviews by dose, merging brands within same dose
- Calculated average ratings, standard deviation, and sentiment 
  distribution per dose group
- 1mg had the highest average rating (3.30)
- 10mg had the lowest average rating (2.91) with 43% 
  negative sentiment
- 20mg was the most polarized: 37.6% five-star AND 
  30.5% one-star simultaneously

### 5. NLP Theme Analysis
- Built a regex pattern library across 10 behavioral themes:
  Timing, Duration of Effect, Long-term Use, Recommendation,
  Side Effects, Effectiveness, Sleep Quality, Dosage Reaction,
  Natural/Drug-free, Reactions
- Generated a theme mention heatmap across all dose groups
- Extracted top bigrams per dose using custom stopword filtering

### 6. Behavioral Pattern Extraction
Answered dose-centered questions from the review text:

| Question | Finding |
|----------|---------|
| When do users take it? | Most common: before bed |
| How long until sleepy? | Most cited: ~30 minutes |
| How long have they used it? | "For years" — 115 mentions |
| Would they recommend it? | 3mg had highest recommendation rate (7.6%) |
| Most common theme? | Effectiveness (40–53% across all doses) |
| Top bigram? | "fall asleep" — #1 at every single dose |
| Highest no-effect rate? | 20mg at 13.7% |

---

## Key Findings

**Dose Personalities:**
- **1mg — The Precision Dose:** Most satisfied users, 
  doctor-recommended timing, highest avg rating
- **3mg — The Sweet Spot:** Highest recommendation rate, 
  most helpful reviews, strongest community trust
- **5mg — The Mass Market:** Most reviewed (25.2%), 
  first-time users, high volume mixed results
- **10mg — The Disappointed Dose:** Lowest avg rating (2.91), 
  43% negative sentiment, most frustration
- **12mg — The Long-term User:** 99.2% verified purchases, 
  loyal users, nightmares noted at higher rate
- **20mg — The Polarizing Dose:** Highest 5-star (37.6%) 
  AND 1-star (30.5%) — works completely or not at all

---

## Files
| File | Description |
|------|-------------|
| `nlp_sentiment_analysis_code.ipynb` | Full analysis notebook with code and visualizations |
| `nlp_sentiment_analysis_presentation.pptx` | Project presentation with key findings and charts |

---

## Course
DAMG6105 — Data Science Engineering with Python
Northeastern University | January 2026
