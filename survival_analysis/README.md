# Survival Analysis

## Introduction
Survival analysis aims to analyze the expected duration of time until an event such as progression or death occurs. Kernel survival
SVMs predict a risk score  $f(X)$ for a given test patient using their WSI representation $X$ after being trained over a training dataset $\{(X_I,T_I,\delta_I)|i=1\ldots N_{train}\}$ which consists of tuples of a patient's whole slide image $X_I$, their disease-specific survival time $T_i$ and a binary event indicator variable $\delta_I \in \{0,1\}$ which shows whether the patient has passed away from breast cancer within a censoring time $T_{censor} = 10$ years or not.

## Usage
To perform this the $1052 \times 1052$ distance matrix and its correspsoning slide IDs located at `data/MMD_matrix/D_1052_blur_10.npy` and `data/MMD_matrix/slide_IDs_1052.npy` respectively are used. This has then been filtered down to  $1033 \times 1033$ sized matrix as we only have surival data for these patients. You can also use your own distance matrix by using `MMD_distance_matrix_generator`.

To generate and validate this SVM use the IPython Notebook file `survival_analysis/survival_analysis.ipynb`.
