# **MEM-679 HW-1 SUBMISSION**

# Whitepaper: Machine Learning for Wake Structure Classification in Turbulent Flows

## 1. Introduction

### 1.1. Problem Domain
In fluid dynamics, the wake that forms behind a bluff body such as a cylinder can significantly impact the aerodynamic or hydrodynamic behavior of the body, leading to oscillations. These oscillations, when resonating with the natural frequency of structures, can induce dangerous vibrations, which may cause structural damage or even collapse. Such phenomena have been observed in bridges, underwater pipelines, and offshore structures. Understanding and controlling these wake structures is crucial for minimizing harmful vibrations and, in some cases, can offer opportunities to harness energy from these vibrations. 

A wake structure refers to the distinct patterns formed in the fluid as it flows past a body. When flow becomes turbulent, these patterns can become complex, necessitating advanced methods to classify and understand them. Recent studies, such as those by Morse and Williamson (2009), have identified several wake patterns based on observations. These wake structures depend on variables such as the Reynolds number (Re), the oscillation frequency ratio (U*), and the oscillation amplitude ratio (A*). However, manually identifying wake structures is time-consuming and prone to error. Thus, there is an opportunity to leverage machine learning to automate the classification of these structures.

### 1.2. Objective
The objective of this project is to apply machine learning techniques to classify turbulent wake structures based on time series sensor measurements. The goal is to accurately identify known wake structures and explore the potential of unsupervised learning to discover new patterns. By classifying these wake structures, we can develop control strategies for minimizing dangerous oscillations and explore the possibility of utilizing these oscillations for energy harvesting.

## 2. Dataset Overview

The dataset used in this project contains time series sensor measurements from a numerically simulated turbulent wake behind an oscillating cylinder. Measurements are recorded every 0.25 seconds for a period of 100 seconds along various sampling lines located at distances of 2D, 4D, 6D, 8D, 10D, and 12D from the cylinder (where D represents the cylinder’s diameter). The data provides a variety of values for three key dimensionless variables: 
- **Reynolds number (Re)** – Governing the degree of turbulence.
- **Amplitude ratio (A\*)** – Reflecting the oscillation amplitude relative to the cylinder diameter.
- **Frequency ratio (U\*)** – Depicting the ratio of the oscillation frequency relative to the mean flow velocity.

These three variables are crucial to understanding the behavior of the wake and the structure it forms. The dataset also includes labels representing known wake structure types (C(2S), P+S, 2S, 2Po, 2P) based on human observations.

### 2.1. Data Format
The dataset is organized in a format that is readily importable into Python for analysis. Each row represents a sensor reading at a specific time and location, with columns corresponding to the time, Reynolds number, amplitude ratio, frequency ratio, and wake structure type (where available).

### 2.2. Feature Summary
- **Reynolds Number (Re)** – Influences the turbulence level in the wake.
- **Amplitude Ratio (A\*)** – Governs the oscillation magnitude.
- **Frequency Ratio (U\*)** – Controls the wake oscillation frequency.
- **Sensor Measurements** – Time series data providing flow measurements along various distances downstream from the cylinder.

## 3. Problem Definition

### 3.1. Research Questions
The project seeks to address the following research questions:
1. **Can machine learning models accurately classify wake structures based on time series sensor data?**
    - This will involve training supervised models on labeled data to predict known wake structures.
2. **Can unsupervised learning discover new wake structure patterns?**
    - Clustering and anomaly detection techniques will be explored to identify new or previously unknown wake structures.
3. **Can models trained on wake structures at Re = 4000 generalize to predict wake structures at different Reynolds numbers (e.g., Re = 1000 or Re = 10000)?**
    - Transfer learning approaches will be investigated to extend the utility of the model beyond the original dataset.
4. **Can machine learning be used to identify wake structures at higher turbulence levels, where human observation becomes impractical?**

### 3.2. Scope
This project will focus on building both supervised and unsupervised machine learning models using the dataset. Initially, supervised models such as Support Vector Machines (SVM), Random Forests, and Neural Networks will be developed to classify wake structures. Subsequently, unsupervised techniques like k-means clustering and Principal Component Analysis (PCA) will be applied to uncover potential new wake structures. The project will also explore how well models trained on one set of Reynolds numbers perform when applied to other Reynolds number regimes.

## 4. Methodology

### 4.1. Data Preprocessing
The dataset will undergo preprocessing steps to handle missing values, normalize or scale sensor measurements, and transform the data into a suitable format for machine learning algorithms. Additionally, temporal patterns in the time series data will be captured using features such as time lags and moving averages.

### 4.2. Supervised Learning Approach
The labeled portion of the dataset will be used to train models on known wake structures. Classifiers like Random Forest, SVM, and Neural Networks will be implemented, and their performance will be evaluated using metrics such as accuracy, precision, recall, and F1-score.

### 4.3. Unsupervised Learning Approach
Clustering algorithms, such as k-means, hierarchical clustering, and DBSCAN, will be applied to the data to detect natural groupings of wake structures without labels. Dimensionality reduction techniques, such as PCA or t-SNE, will be employed to visualize the resulting clusters and identify any emergent patterns.

### 4.4. Transfer Learning and Generalization
Models trained on the dataset at Re = 4000 will be evaluated on how well they generalize to different Reynolds numbers, such as Re = 1000 and Re = 10000. This will involve retraining or fine-tuning the models on small portions of data from these new regimes and testing their ability to predict wake structures.

## 5. Expected Outcomes

By the end of this project, the following outcomes are expected:
- A machine learning model capable of accurately classifying wake structures based on sensor data.
- Insights into the efficacy of unsupervised learning in discovering new wake structures.
- A model that can generalize across different Reynolds numbers to extend the classification to more turbulent flow conditions.
- Recommendations on the use of machine learning for predictive control of wake oscillations in practical engineering applications, along with the potential for energy harvesting in relevant cases.

## 6. Conclusion

This project proposes the use of machine learning to address the challenge of classifying wake structures in turbulent fluid flows. By leveraging both supervised and unsupervised techniques, the project aims to improve our understanding of wake behaviors in engineering contexts and offer solutions for minimizing hazardous vibrations or harnessing energy from them. The dataset of time series sensor measurements provides a rich source of information that will be instrumental in developing and validating the proposed models.

---

## 7. References
- Morse, T.L., Williamson, C.H.K. (2009), "Fluid forcing, wake modes, and transitions for a cylinder undergoing controlled oscillations," *Journal of Fluids and Structures*, 25(4), 697-712. [doi:10.1016/j.jfluidstructs.2008.12.003](https://doi.org/10.1016/j.jfluidstructs.2008.12.003)
- Vortex Hydro Energy, "How It Works," [https://www.vortexhydroenergy.com/technology/how-it-works](https://www.vortexhydroenergy.com/technology/how-it-works)
