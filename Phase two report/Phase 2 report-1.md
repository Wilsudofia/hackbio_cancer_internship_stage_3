# Building a ML model to predict the IC50
## Authors (@slack): Hanna, BigWils, samar-samir, sarasamer22, DerleenM
## Link to [The project script](https://github.com/Hana-Nadir/hackbio_cancer_internship_stage_3/blob/main/ML%20project%20python%20script/Building%20ML%20model%20to%20predict%20the%20pIC50.ipynb)

## Introduction
In this project, the goal was to develop a machine learning model to predict compounds' bioactivity against a therapeutic target. We focused on Methionine Aminopeptidase 2, a cancer-related protein. Bioactivity data were retrieved from the ChEMBL database, specifically compounds with IC50 values, which indicate the concentration required to inhibit 50% of the target protein's activity.

## Dataset and Preprocessing
The dataset from ChEMBL (version 34) included IC50 values, assay information, and molecular descriptors calculated using RDKit and Mordred. **Data preprocessing** involved:
- Cleaning and filtering missing or invalid IC50 values.
- Generating molecular descriptors to capture chemical and structural properties.
- Feature engineering with Principal Component Analysis (PCA) to reduce dimensionality.


## Model Development and Training
A **Random Forest Regressor** was selected for predicting pIC50 (log-transformed IC50). The dataset was split into 80% training and 20% testing sets. The training phase captured non-linear relationships between molecular descriptors and pIC50. Evaluation metrics used were:
- **Mean Squared Error (MSE)**: 0.0504
- **Mean Absolute Error (MAE)**: 0.0952
- **R-squared**: 0.9647

Cross-validation was performed to ensure generalizability across different data folds.

## Results and Feature Importance
The Random Forest model demonstrated strong predictive performance with an R-squared value of 0.9647, explaining 96.47% of the variance in pIC50 values, indicating its effectiveness in predicting bioactivity. Additionally, the model showed low prediction errors, with a Mean Squared Error of 0.0504 and a Mean Absolute Error of 0.0952, reflecting its accuracy. Cross-validation results confirmed the model’s generalizability, with scores indicating it can effectively predict unseen data. These results highlight the model’s potential in identifying and optimizing bioactive compounds for drug discovery.
Key molecular descriptors influencing bioactivity include:
- **Molecular Weight (MW)**: Heavier compounds showed varied bioactivity, indicating the importance of size.
- **LogP**: Lipophilicity affected compounds’ ability to permeate membranes.
- **Hydrogen Bond Acceptors/Donors**: Essential for compound-target interactions.

The scatter plot below shows a positive correlation between binding affinity from ligands in phase one and their pIC50 predicted using our model.This indicates that compounds with stronger binding affinity tend to exhibit higher potency, helping to identify potent compounds and outliers. It provides insights into structure-activity relationships and guides optimization in drug discovery.

![Binding Affinity vs. pIC50](https://github.com/Wilsudofia/Hackbio-Phase-2/blob/main/Phase%202/pIC50%20VS%20Docking%20score.png)

*Figure 3: Positive correlation between binding affinity and pIC50 values.*

## Conclusion
This study successfully built a Random Forest model for predicting pIC50 values, demonstrating robust predictive power. Future work should focus on refining molecular descriptors and validating results experimentally to discover more potent cancer therapy compounds.
