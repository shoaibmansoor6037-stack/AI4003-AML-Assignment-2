# AI-Based Electrical Fault Detection System

**Course:** AI4003 – Applied Machine Learning  
**Project:** Detecting Faults on a Three-Phase Transmission Line

## Team Members

| Name | Roll Number |
|---|---|
| Shoaib Mansoor | 23F-6037 |
| Muhammad Malik | 22F-3487 |

## Project Description

This project uses machine learning to detect faults in a three-phase transmission line using current and voltage measurements. It compares Logistic Regression implemented from scratch using NumPy with Linear and RBF-kernel Support Vector Machines (SVMs).

## Technologies Used

- Python
- NumPy and Pandas
- Matplotlib
- Scikit-learn (SVM only)
- Joblib
- Jupyter Notebook
- VS Code

## Project Structure

- `data/` — Dataset
- `src/` — Source code for data preparation, model training, and evaluation
- `results/` — Model results, tables, and figures
- `app/` — Interactive fault-detection frontend

## Model Results

| Model | Test Accuracy |
|---|---:|
| Logistic Regression (Set R) | 72.64% |
| Logistic Regression (Set Q) | 97.00% |
| Linear SVM | 73.64% |
| RBF SVM | 99.58% |

## Output Screenshots

### 1. Exploratory Data Analysis

**Three-Phase Current Plot**

<img width="858" height="353" alt="image" src="https://github.com/user-attachments/assets/44d62f87-6c68-441c-8f3c-a783b55224ed" />

**Ia vs Ib Scatter Plot**

<img width="602" height="449" alt="image" src="https://github.com/user-attachments/assets/fd84d9ec-312b-4d46-87d5-045d1eb006dd" />


**Phase A Current Histogram**

<img width="782" height="430" alt="image" src="https://github.com/user-attachments/assets/781b27c0-d490-48d3-ab14-5bea1c25b997" />

## Logistic Regression: Set R vs Set Q

We evaluated Logistic Regression using two different feature sets.

- **Set R — Original Features:** Uses the six original measurements: Ia, Ib, Ic, Va, Vb, and Vc.
- **Set Q — Squared Features:** Uses the same six measurements plus their squared values, giving twelve features in total.

| Feature Set | Final Training Cost | Validation Accuracy | Test Accuracy |
|---|---:|---:|---:|
| Set R — Original Features | 0.677161 | 73.08% | 72.64% |
| Set Q — Original + Squared Features | 0.088989 | 96.50% | 97.00% |

The results show that adding squared features significantly improved Logistic Regression's ability to distinguish between fault and no-fault conditions.

## Comparison of All Models

| Model | Feature Set / Kernel | Test Accuracy |
|---|---|---:|
| Logistic Regression | Set R — Original Features | 72.64% |
| Logistic Regression | Set Q — Squared Features | 97.00% |
| SVM | Linear Kernel | 73.64% |
| SVM | RBF Kernel (C = 100, γ = 1) | 99.58% |

## Output Screenshots

### 1. Logistic Regression — Set R

**Original six features**

<img width="869" height="530" alt="image" src="https://github.com/user-attachments/assets/67e997f2-8e31-4428-ad0e-35f0d946376e" />


### 2. Logistic Regression — Set Q vs Set R

**Twelve features, including squared terms**

<img width="419" height="122" alt="image" src="https://github.com/user-attachments/assets/79ccddc9-153d-484a-b157-202790e3a165" />

**SVM Validation Accuracy**

<img width="705" height="242" alt="image" src="https://github.com/user-attachments/assets/d7b6c84f-bf36-406a-ba70-d60a82d20aa7" />
<img width="648" height="395" alt="image" src="https://github.com/user-attachments/assets/7929d58f-372d-4331-a12d-123ba7679fed" />


### 3. Frontend Output

**Electrical Fault Detection Dashboard**

<img width="975" height="609" alt="image" src="https://github.com/user-attachments/assets/95256c33-84ba-4b37-901f-da9453f82fb4" />


## How to Run

1. Open the project folder in VS Code.
2. Install the required Python libraries.
3. Run the scripts in the appropriate order.
4. Open `app/app.ipynb` and run its cells.
5. Enter the six electrical measurements and click **Predict Fault** to compare the Logistic Regression and RBF SVM predictions.

## Conclusion

The experiments show that adding squared features improves Logistic Regression performance, while the RBF SVM achieves the highest test accuracy among the four evaluated models. Further validation on independent real-world electrical data would be necessary before practical deployment.

