# ESG Pillar Imbalance Analysis

A data analytics project investigating whether companies balance Environmental, Social, and Governance (ESG) performance evenly, or whether strong performance in one pillar tends to mask weakness in another.

## Purpose

Public ESG ratings are typically communicated as a single aggregate score or letter grade. This can obscure meaningful internal variation — a company can present a strong overall ESG profile while performing poorly in one specific pillar. This project analyses ~700 mid- and large-cap companies to quantify and visualise this kind of pillar-level imbalance, both at the individual company level and across industries.

**Primary business question:** Do companies balance Environmental, Social, and Governance performance, or do they lean on one pillar to compensate for weakness in another?

**Secondary question:** How do industries rank in overall ESG performance, and does that ranking hold up once pillar-level imbalance is accounted for?

## Who this is for

This project is aimed at anyone evaluating companies through an ESG lens where a single aggregate score may be insufficient — for example, investors screening for genuinely well-rounded ESG performance rather than a strong headline grade, or analysts researching sector-level ESG patterns.

## Dataset

[Public Company ESG Ratings Dataset](https://www.kaggle.com/datasets/alistairking/public-company-esg-ratings-dataset) (Kaggle) — ESG scores, grades, and levels for 722 public companies across 44 industries.

## Repository structure

```
├── data/
│   ├── public_company_esg_ratings.csv   # Raw dataset
│   └── public_company_esg_ratings_cleaned.csv.csv  # Cleaned dataset (output of notebook 1)
├── jupyter_notebooks/
│   ├── esg_corporate_analysis.ipynb   # ETL, cleaning, normalisation
│   └── esg_corporate_analysis_visualisation.ipynb  # EDA, visualisation, imbalance analysis
├── requirements.txt
└── README.md
```

## How to run

1. Clone this repository and open it in your IDE of choice.
2. Create and activate a virtual environment.
3. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
4. Run `esg_corporate_analysis.ipynb` first — this loads the raw dataset, cleans it, and exports `data/public_company_esg_ratings_cleaned.csv`.
5. Run `esg_corporate_analysis_visualisation.ipynb` — this loads the cleaned dataset and performs the exploratory analysis and visualisation.

## Summary of findings

- **Social is the weakest ESG pillar almost universally.** Once scores were normalised onto a common scale, Social ranked as the lowest-performing pillar in 21 of 23 industries analysed.
- **Governance never reaches the top rating tier in this dataset**, regardless of industry — no company achieved an "Excellent"/"AA" governance rating, despite this being achievable on both Environment and Social.
- **Industry-level imbalance follows two distinct patterns.** Utilities and Energy show high imbalance driven by an unusually strong Environmental score; Biotechnology and Electrical Equipment show high imbalance driven by two weak pillars (Environment and Social) propped up by a stronger Governance score.
- **CMS Energy** is a standout individual example: the dataset's highest Social score paired with its lowest Governance score — a live illustration of the imbalance this project set out to investigate.
- **At the company level, severe imbalance is the exception, not the norm** — most companies cluster in a moderate imbalance range, with extreme cases forming a small tail rather than a common pattern.

## Technologies used

Python, pandas, Matplotlib, Seaborn, Jupyter Notebook

## Limitations

This dataset does not disclose its rating methodology or provider, which limits how confidently some findings (e.g. the Governance ceiling) can be explained. Industry comparisons exclude industries with fewer than 10 companies for statistical reliability. Full details are documented in the analysis notebook's Limitations & Alternatives section.

## AI usage acknowledgement

Generative AI (Claude) was used throughout this project for project management, debugging support, code review, and AI-assisted narrative summarisation. Specific examples are documented in the AI Usage Log section of `esg_corporate_analysis_visualisation.ipynb`.