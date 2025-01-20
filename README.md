# Internship Project Report @ Baden-Wuerttemberg Cooperative State University (DHBW)

## AI Application to Material Testing Using Acoustic Emission and Analysis of AE Spectra

### Overview
This project focused on leveraging Artificial Intelligence (AI) and data analysis techniques to analyze acoustic emission (AE) signals and classify material wear conditions. The report details the steps undertaken during the internship, including data preparation, model training, Fourier analysis, and comparisons of ANN and CNN models.

---

### Project Steps

1. **Merging and Labeling Datasets**
   - Combined three datasets into a unified structure.
   - Data was labeled based on wear condition logic:
     ```python
     if (df2["flute_1"].iloc[idx] >= 166) or (df2["flute_2"].iloc[idx] >= 166) or (df2["flute_3"].iloc[idx] >= 166):
         status = "severe wear"
     elif (df2["flute_1"].iloc[idx] > 66) or (df2["flute_2"].iloc[idx] > 66) or (df2["flute_3"].iloc[idx] > 66):
         status = "uniform wear"
     else:
         status = "rapid wear"
     ```
   - Wear conditions were categorized as **Severe Wear**, **Uniform Wear**, and **Rapid Wear**.

2. **Data Preprocessing**
   - Cleaned and preprocessed data for Exploratory Data Analysis (EDA) and model training.
   - Addressed data imbalance using oversampling techniques.

3. **Exploratory Data Analysis (EDA)**
   - Conducted statistical and visual analyses to understand wear patterns.
   - Key observation: Higher AE values correlated with severe wear conditions.

4. **Feature Engineering**
   - Applied domain-specific techniques to extract meaningful features from AE data.

5. **Fourier Transformation**
   - Transformed AE signals from the time domain to the frequency domain using Fast Fourier Transform (FFT):
     - Zero-centered the AE data.
     - Visualized frequency components for different wear conditions.
   - Organized output plots into wear-condition-specific directories for clarity.

6. **Artificial Neural Networks (ANNs)**
   - Trained an ANN on the labeled dataset.
   - Evaluated performance using metrics like precision, recall, and F1-score.

7. **Convolutional Neural Networks (CNNs)**
   - Designed a CNN for image classification of wear patterns.
   - Preprocessed images, split datasets, and trained the model.
   - Achieved an overall accuracy of 83%.

8. **Performance Comparison: ANN vs. CNN**
   - The ANN achieved 77% accuracy, excelling at detecting severe wear.
   - The CNN outperformed the ANN with better-balanced performance across all wear classes.

---

### Results

#### ANN Performance:
| Class           | Precision | Recall | F1-Score |
|-----------------|-----------|--------|----------|
| Rapid Wear      | 0.78      | 0.65   | 0.71     |
| Uniform Wear    | 0.67      | 0.74   | 0.70     |
| Severe Wear     | 0.86      | 0.93   | 0.89     |
| **Overall**     | -         | -      | **77%**  |

#### CNN Performance:
| Class           | Precision | Recall | F1-Score |
|-----------------|-----------|--------|----------|
| Rapid Wear      | 0.95      | 1.00   | 0.98     |
| Uniform Wear    | 0.76      | 0.80   | 0.78     |
| Severe Wear     | 0.75      | 0.67   | 0.71     |
| **Overall**     | -         | -      | **83%**  |

---

### Key Contributions
- **Dataset Balancing:** Oversampling improved model generalization.
- **Fourier Transformation:** Uncovered frequency-domain insights from AE signals.
- **Modeling Techniques:** Demonstrated the strengths of ANN for sequential data and CNN for image data.

---

### Tools & Technologies
- **Programming Language:** Python
- **Libraries:** Keras, TensorFlow, NumPy, Pandas, Matplotlib
- **Data Source:** [PHM Data Challenge 2010](https://www.kaggle.com/datasets/rabahba/phm-data-challenge-2010)

---

### Future Work
- Combine ANN and CNN models for a hybrid approach to analyzing AE data and images.
- Enhance preprocessing techniques to further improve model accuracy.

---

### References
1. Chen, Bo-Xiang et al. *Application of Generative Adversarial Network and Diverse Feature Extraction Methods to Enhance Classification Accuracy of Tool-Wear Status*. Electronics, 2022.

2. [PHM Data Challenge 2010](https://www.kaggle.com/datasets/rabahba/phm-data-challenge-2010)
