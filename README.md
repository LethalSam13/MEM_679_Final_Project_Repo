# Wake Structure Classification Project

## Overview
This repository contains the code, data, and documentation for a machine learning project aimed at classifying wake structures in turbulent flows using time-series sensor data. The primary objective of this project is to apply supervised and unsupervised learning techniques to classify and uncover patterns in wake structures. The insights gained from this study can be used to minimize harmful oscillations in fluid systems and explore energy harvesting possibilities.

---

## Repository Contents

- **Data Visualization.ipynb**: A Jupyter Notebook for visualizing the wake structure data and exploring its features.
- **Final Project File.ipynb**: The main notebook containing the complete code pipeline for preprocessing, training, and evaluating machine learning models.
- **Project Overview.md**: A detailed overview of the project objectives, research questions, and methodologies.
- **Scientific Data Management.ipynb**: A notebook demonstrating how to manage and preprocess scientific datasets efficiently using tools like DATAFED.

---

## Dataset

### Description
The dataset includes time-series sensor measurements from a numerically simulated turbulent wake behind an oscillating cylinder. Measurements are recorded every 0.25 seconds for a duration of 100 seconds across various distances from the cylinder (2D, 4D, 6D, etc., where D is the cylinder diameter).

### Features
- **Reynolds Number (Re)**: Governs the degree of turbulence.
- **Amplitude Ratio (A*)**: Reflects the oscillation amplitude relative to the cylinder diameter.
- **Frequency Ratio (U*)**: Depicts the ratio of oscillation frequency to mean flow velocity.
- **Sensor Measurements**: Time-series flow measurements from various sampling lines downstream of the cylinder.

### Target
- **Wake Structure Types**: Labels representing known wake patterns (e.g., C(2S), P+S, 2S, 2Po, 2P).

---

## Problem Statement
The project aims to address the following:
1. **Supervised Learning**: Can machine learning models classify wake structures accurately based on sensor data?
2. **Unsupervised Learning**: Can clustering methods discover new or unknown wake structure patterns?
3. **Generalization**: Can models trained on specific Reynolds numbers (e.g., Re = 4000) generalize to other values (e.g., Re = 1000 or 10000)?
4. **Practical Application**: Can machine learning handle high turbulence levels where human observation is impractical?

---

## Methodology

1. **Data Preprocessing**:
   - Handle missing values.
   - Normalize/standardize features.
   - Split data into training and testing sets.

2. **Supervised Learning**:
   - Train classifiers (e.g., Random Forest, Neural Networks) to predict wake structure types.

3. **Unsupervised Learning**:
   - Apply clustering techniques like k-means and PCA to identify potential new wake patterns.

4. **Neural Networks**:
   - Train a convolutional neural network (CNN) to explore deep learning insights.

5. **Evaluation**:
   - Use accuracy, mean squared error, confusion matrices, and clustering visualizations to assess model performance.

---

## Results

### Expected Outcomes:
- A machine learning model capable of accurately classifying wake structures.
- Insights into the efficacy of unsupervised methods for discovering new patterns.
- A generalizable model for different turbulence regimes.
- Recommendations for applying machine learning to practical engineering challenges (e.g., minimizing oscillations, energy harvesting).

---

## References
- **Morse, T.L., Williamson, C.H.K. (2009)**: "Fluid forcing, wake modes, and transitions for a cylinder undergoing controlled oscillations." Journal of Fluids and Structures, 25(4), 697-712. [DOI](https://doi.org/10.1016/j.jfluidstructs.2008.12.003)

---

## How to Run the Code
1. Clone this repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```
2. Install required libraries:
   ```bash
   pip install -r requirements.txt
   ```
3. Open and run the Jupyter Notebooks in the specified order:
   - Start with `Scientific Data Management.ipynb` for preprocessing.
   - Explore data using `Data Visualization.ipynb`.
   - Train and evaluate models using `Final Project File.ipynb`.

---

## Future Work
- Extend models to handle larger datasets with higher Reynolds numbers.
- Investigate transfer learning to improve generalization across datasets.
- Develop predictive control systems for real-time application in engineering scenarios.

---

## License
This project is licensed under the MIT License. See `LICENSE` for details.

