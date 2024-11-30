-------------------------------
# Molecular Solubility Prediction

This project predicts the **Solubility (LogS)** values of molecules based on their molecular descriptors. The model is trained using a dataset from the **John S. Delaney**, containing solubility values and molecular descriptors.

----------------------------

## Project Overview

The goal of this project is to predict the aqueous solubility (`logS`) of molecules based on their chemical structure. The model uses a **Linear Regression** algorithm and takes as input several molecular descriptors calculated from the molecule's structure, such as:

- LogP (octanol-water partition coefficient)
- Molecular weight (MolWt)
- Number of rotatable bonds
- Aromatic proportion

The model is built using the **Delaney solubility dataset**.

------------------------------
## Dataset

The dataset used in this project is obtained from the article:

- **Source**: *"ESOL:  Estimating Aqueous Solubility Directly from Molecular Structure"*  
  John S. Delaney. *J. Chem. Inf. Comput. Sci. 2004*, 44, 3, 1000–1005.  
  [Link to dataset](https://pubs.acs.org/doi/10.1021/ci034243x)

-------------------------------
### Dataset Columns:

- `logS`: Experimental solubility (logarithmic scale)
- Descriptors: Molecular features such as LogP, Molecular weight, number of rotatable bonds, and aromatic proportion

-----------------------------
##  Model Evaluation

The model's performance was assessed using the following metrics:

- **Mean Squared Error (MSE)**: This metric measures the average squared difference between the predicted and actual values. A lower MSE indicates better model performance.
  
  **MSE = 1.01**

- **R-squared (R²)**: This is a measure of how well the independent variables (molecular descriptors) explain the variance in the dependent variable (logS). The closer the R² value is to 1, the better the model is at predicting the solubility values.

  **R² = 0.77**

  This means that approximately **77%** of the variance in solubility is explained by the features used in the model (LogP, molecular weight, number of rotatable bonds, and aromatic proportion).

### Model Coefficients:

- **Intercept**: 0.26
- **LogP (octanol-water partition coefficient)**: -0.74
- **Molecular weight (MolWt)**: -0.0066
- **Number of rotatable bonds (RB)**: 0.0032
- **Aromatic proportion (AP)**: -0.42

These coefficients highlight how each feature impacts the solubility prediction:
- A negative coefficient for LogP and aromatic proportion suggests that as the number of aromatic atoms increases, or as the molecule becomes more hydrophobic (higher LogP), solubility decreases.
- The small positive coefficient for the number of rotatable bonds indicates a slight increase in solubility with more flexible molecules.
- The coefficient for molecular weight suggests that larger molecules tend to have lower solubility.

### Model Equation:
```bash
LogS = 0.26 - 0.74 * LogP - 0.0066 * MW + 0.0032 * RB - 0.42 * AP
```

---

## Results

The linear regression model, trained on the Delaney solubility dataset, successfully predicts the solubility of molecules based on their molecular descriptors. The model was able to explain **77% of the variance** in solubility, achieving a **R² value of 0.77**. This suggests that the model can be used to predict solubility for new compounds with a reasonable degree of accuracy.

The **Mean Squared Error (MSE)** of 1.01 indicates that the predictions are generally close to the actual values, but there is still room for improvement in the model's accuracy.

## Conclusion

The model performs well in predicting solubility values based on molecular descriptors. With an R² value of 0.77, it can be considered moderately successful for the task of solubility prediction. The key molecular descriptors influencing solubility include LogP, molecular weight, number of rotatable bonds, and aromatic proportion.

While this model provides a useful approximation of solubility, further improvements can be made by incorporating additional descriptors or exploring more complex modeling techniques. Additionally, the model's accuracy can be further enhanced by fine-tuning and validating it on a larger dataset or using other machine learning techniques such as Random Forests or Gradient Boosting Machines.

Overall, this project demonstrates the application of machine learning for chemoinformatics and solubility prediction, and it can serve as a foundation for future work in predicting other molecular properties.

---


