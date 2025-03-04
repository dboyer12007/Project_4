# Project 4: Analysis of At-Bats With a First Pitch Swing

## Overview
This project aimed to predict hit success using ball-in-play metrics such as:
- Exit velocity
- Launch angle
- Hit location

Initial models using post-contact features performed well, achieving 75-85% accuracy in predicting whether a first-pitch swing would result in a hit. However, we shifted our focus to pre-swing characteristics to better understand decision-making before contact occurs.

Key factors:
- Pitch type
- Velocity
- Spin rate
- Location

The goal was to determine whether pre-swing data alone could predict the quality of a first-pitch swing.

---

## Methodology

### Data Collection
- Pulled Statcast data for all first-pitch swings in the 2024 MLB season. Initially included final at-bat outcomes (hits/outs) but later shifted focus to classifying swing outcomes.

### Data Processing
- Encoded categorical variables (e.g., pitch type) and standardized numerical features (e.g., velocity, spin rate).
- Balanced dataset using SMOTE to handle class imbalance.
- Classified swings into four categories: 
  - Swing and Miss (Complete miss on the first pitch)
  - Foul (Contact but out of play)
  - Weak Contact (Exit velocity < 95 mph)
  - Hard Contact (Exit velocity ≥ 95 mph)

---

## Model Training
- Tested three machine learning models: Logistic Regression, Random Forest, and XGBoost.
- Evaluated performance using precision, recall, F1-score, and confusion matrices.

### Findings
- Machine learning struggles to predict first-pitch swing quality using pre-swing data alone.
- The best model achieved ~43-47% accuracy, which is not significantly better than random guessing.
- Contact quality is influenced by factors such as hitter mechanics, reaction time, and approach, which are not captured in pitch-tracking data.

---

## Key Takeaways & Next Steps

### Key Takeaways
- Machine learning models can accurately predict outcomes when using post-contact data (e.g., exit velocity, launch angle).
- Pre-swing characteristics alone do not reliably predict contact quality. Zone and pitch type matter, but hitter-specific tendencies may play a larger role than pitch data alone can capture.

### Future Improvements
- Incorporate hitter-specific data (e.g., historical swing tendencies, whiff rates).
- Analyze situational factors (e.g., count, game state, pitcher tendencies).
- Expand dataset to multiple seasons to see if trends persist.
- Shift focus away from ML and explore raw stats on at-bats with first-pitch swings.





