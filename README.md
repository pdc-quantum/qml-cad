# qml-cad

## Quantum Machine Learning  for Coronary Artery Disease

These notebooks explore the metrics obtained by classical and quantum support vector machine with different random seeds for the partition into training and test sets.

Two versions: the eleven features regularly tested in classical ML and the eight features exhibiting the best correlation with the label CAD / NoCAD

The dataset was obtained directly from: https://archive.ics.uci.edu/ml/datasets/heart+Disease, using this program: https://github.com/SpiroGanas/Heart-Disease-Machine-Learning/blob/master/load_heart_disease_data.py

It differs therefore slightly from the dataset used for the paper. Missing data treatment and data transformation is also somewhat different.

11 features set: ['age', 'sex', 'cp', 'trestbps', 'chol', 'fbs', 'restecg', 'thalach', 'exang', 'oldpeak', 'slope']

8 feature sets : ['age', 'sex', 'cp', 'fbs', 'thalach', 'exang', 'oldpeak', 'slope']

The feature drop is on basis of poor correlation with the condition. The chol variable is the weakest one, with many missing or absurdly 0.0 values.

A side by side review of the two notebooks shows no real difference in the metrics for the eight and eleven feature sets. 

Therefore, it's probably a good option to stick to the eleven feature set in order to remain in line with previous publications using classical ML. 

However, the eight features set remains an option, if the depth of the quantum circuit significantly affects the metrics in quantum simulatiosn or hardware experiments with noise with noise 

### References

Impact of train/test sample regimen on performance estimate stability of machine learning in cardiovascular imaging

https://www.nature.com/articles/s41598-021-93651-5#Tab3

2021 AHA/ACC/ASE/CHEST/SAEM/
SCCT/SCMR Guideline for the
Evaluation and Diagnosis of Chest Pain:

https://www.jacc.org/doi/pdf/10.1016/j.jacc.2021.07.053?_ga=2.85562654.649136116.1674121202-7665523.1671358677
