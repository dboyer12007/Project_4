# Project_4
Analysis of At-Bats With a First Pitch Swing

 Overview
This project originally aimed to predict hit success using ball-in-play metrics, such as:

Exit velocity
Launch angle
Hit location
Initial models using these post-contact features performed well, achieving 75-85% accuracy in predicting whether a first-pitch swing would result in a hit.

However, to better understand decision-making before contact occurs, we shifted our focus to pre-swing characteristics, including:

Pitch type
Velocity
Spin rate
Location
The goal was to determine whether pre-swing data alone could predict the quality of a first-pitch swing..

Methodology
Data Collection

Pulled Statcast data for all first-pitch swings in the 2024 MLB season.
Initially included final at-bat outcomes (hits/outs) but later shifted to classifying swing outcomes.

Data Processing

Encoded categorical variables (e.g., pitch type).
Standardized numerical features (e.g., velocity, spin rate).
Balanced dataset using SMOTE to handle class imbalance.
Classification Approach

Instead of predicting hit success, we classified swings into four categories:
Swing and Miss (Complete miss on the first pitch)
Foul (Contact but out of play)
Weak Contact (Exit velocity < 95 mph)
Hard Contact (Exit velocity ≥ 95 mph)

Model Training

Tested three machine learning models:
Logistic Regression
Random Forest
XGBoost
Evaluated performance using precision, recall, F1-score, and confusion matrices.

Findings
ML struggles to predict first-pitch swing quality using pre-swing data alone.

The best model achieved ~43-47% accuracy, which is not significantly better than random guessing.
Contact quality is influenced by hitter mechanics, reaction time, and approach, which are not captured in pitch-tracking data.
Including ball-in-play metrics significantly improves accuracy.

In an earlier model where launch angle, exit velocity, and batted ball type were included as features, accuracy was much higher (75-80%) across all models.
This suggests that batted ball characteristics are strong predictors of outcomes, but pre-swing pitch characteristics alone are insufficient.
Pitch type and location are the most important factors when limited to pre-swing data.

Feature importance showed zone, pitch type, and extension had the most predictive value.
However, these were not strong enough to reliably classify contact quality.
First-pitch swing decisions may not be optimized for contact quality.

Hitters may swing for different reasons (e.g., situational hitting, pitcher tendencies) rather than simply maximizing hard contact.

Conclusion & Next Steps

Key Takeaways
ML models can accurately predict outcomes when using post-contact data (exit velocity, launch angle, etc.).
Pre-swing characteristics alone do not provide enough information to reliably predict contact quality.
Zone and pitch type matter, but hitter-specific tendencies may play a larger role than pitch data alone can capture.

Future Improvements
Incorporate hitter-specific data (e.g., historical swing tendencies, whiff rates, spray charts).
Analyze situational factors (e.g., count, game state, pitcher tendencies).
Expand dataset to multiple seasons to see if trends persist.
Shift away from ML and see raw stats on at bats with first swings, not just at bats where the first pitch is in play such as BA/SLG/OBP.




