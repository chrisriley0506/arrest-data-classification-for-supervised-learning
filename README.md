# LAPD Arrest Type Classification

**Supervised Machine Learning Final Project**

## Overview

This project uses machine learning to predict arrest type classifications (Misdemeanor, Investigation, Dependent, Other) from arrest circumstances in Los Angeles. Using publicly available LAPD arrest data from 2020-present, we analyze temporal, geographic, and demographic patterns to understand factors influencing arrest classifications.

## Problem Statement

Understanding patterns in arrest classifications can help law enforcement agencies optimize resource allocation, improve officer training, and enhance operational efficiency. This project builds supervised learning models to predict arrest types from incident characteristics.

## Dataset

- **Source**: [LA Open Data Portal - Arrest Data from 2020 to Present](https://data.lacity.org/Public-Safety/Arrest-Data-from-2020-to-Present/amvf-fr72)
- **Size**: 340,339 records
- **Time Period**: 2020 - Present
- **Features**: Temporal (time, day), Geographic (area, district), Demographic (age, sex, descent)
- **Target Classes**: Felony (F), Misdemeanor (M), Investigation (I), Other (O)

## Methodology

### Data Processing
1. Data cleaning and missing value handling
2. Feature engineering (temporal features, age groups, time of day)
3. Encoding categorical variables
4. Train-test split (80/20) with stratification

### Models Tested
1. **Logistic Regression** (Baseline)
2. **Random Forest Classifier**
3. **XGBoost Classifier**

### Evaluation Metrics
- Accuracy
- Precision, Recall, F1-Score (macro-averaged)
- Confusion matrices
- Feature importance analysis
- Bias/fairness testing across demographics

## Key Findings

This analysis of 340,339 LAPD arrests reveals:
- **Geographic and temporal factors** are the strongest predictors of arrest type
- **Class imbalance** (Felony 46.8%, Misdemeanor 44.6%, Investigation 7.7%, Other 0.9%) presents challenges
- **Fairness analysis** shows minimal demographic bias in model predictions

**Best Model**: Random Forest Classifier
**Accuracy**: 60.49%
**Most Important Features**: Reporting District (26.3%), Age (22.0%), Hour of Day (17.4%)

## Project Structure

```
├── LA_Arrest_Prediction_Project.ipynb   # Main analysis notebook
├── requirements.txt                      # Python dependencies
├── README.md                             # This file
└── presentation_video.mp4                # Project presentation
```

## Installation & Usage

### Requirements
- Python 3.8+
- Jupyter Notebook

### Setup
```bash
# Clone repository
git clone [your-repo-url]
cd [repo-name]

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook LA_Arrest_Prediction_Project.ipynb
```

### Running the Analysis
1. Download the arrest data from [LA Open Data Portal](https://data.lacity.org/Public-Safety/Arrest-Data-from-2020-to-Present/amvf-fr72)
2. Place the CSV file in the project directory
3. Run all cells in the notebook sequentially

## Results Summary

### Model Performance
| Model | Accuracy | F1-Score (Macro) | Precision (Macro) | Recall (Macro) |
|-------|----------|------------------|-------------------|----------------|
| Logistic Regression | 50.71% | 0.262 | 0.253 | 0.276 |
| Random Forest | **60.49%** | **0.483** | **0.590** | **0.459** |
| XGBoost | 60.36% | 0.474 | 0.688 | 0.448 |

### Feature Importance (Random Forest)
1. **Reporting District** - 26.3%
2. **Age** - 22.0%
3. **Hour of Day** - 17.4%
4. **Month** - 15.3%
5. **Day of Week** - 8.7%

### Fairness Analysis
Performance by demographic groups shows minimal bias:
- Sex-based accuracy variance: ~3% difference
- Model predictions driven by circumstances rather than demographics
- Geographic and temporal factors dominate over demographic characteristics

## Limitations

1. **Data Quality**: Transcribed from paper reports; may contain errors
2. **Missing Values**: Some fields have high missing rates
3. **Temporal Scope**: Model trained on 2020-present data
4. **Generalization**: Specific to LAPD jurisdiction

## Ethical Considerations

- All data is publicly available and anonymized
- Model tested for demographic bias
- Intended for research/educational purposes only
- Operational use would require extensive validation and oversight

## Future Work

1. Incorporate neighborhood socioeconomic data
2. Time series analysis of arrest patterns
3. Integration with calls-for-service data
4. Cross-jurisdictional comparison
5. Deep learning approaches for complex pattern recognition

## Author

**Chris**  
Master's in Computer Science (in progress)  
Specialization: Machine Learning, Quantum Computing

## Acknowledgments

- Los Angeles Open Data Portal for providing public access to arrest data
- LAPD for maintaining and updating the dataset

## License

This project is for educational purposes. Data sourced from LA Open Data Portal under their terms of use.

---

*Last Updated: November 2024*
