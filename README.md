# qml-cad

## Quantum Machine Learning  for Coronary Artery Disease

### Important addition: CAD_quantum_k_fold_cross_validation notebook.

- The 11-qubit SVM model gives the best AUC value

![image](https://user-images.githubusercontent.com/29145045/214704051-3f298986-47dc-4aa7-91d8-44d091252721.png)

-  No encoding modification appears necessary for the resting ECG feature in SVM models


### Previous notebooks

The previous other notebooks explore the metrics obtained by classical and quantum support vector machine with different random states for the partition into training and test sets.

Two versions: the eleven feature regularly tested in classical ML and the eight feature exhibiting the best correlation with the label CAD / NoCAD

These notebooks were edited on end january 2022. The random state set is know made of the 100 first prime numbers. They include now 11-qubit SVM version for 11 features and 8-qubit SVM version for 8 features, in addition to the 4-qubits SVM. 

The dataset was obtained  from: https://ieee-dataport.org/open-access/heart-disease-dataset-comprehensive

Absurd values of 0.0 for cholesterol and for blood pressure underwent mean substitution, because we are sure that these are missing values (more sophisticated methods for missing data can of course be contemplated).

11 feature set: ['age', 'sex', 'chest pain type','resting bp s','cholesterol','fasting blood sugar',
                 'resting ecg','max heart rate','exercise angina', 'oldpeak', 'ST slope'] 

8 feature sets : ['age', 'sex', 'chest pain type','fasting blood sugar',
                 'max heart rate','exercise angina', 'oldpeak', 'ST slope'] 

The feature drop is on basis of poor correlation with the target.

For comparing the metrics in classical, 4-qubit and 8 or 11-qubit SVM, a random state giving AUC scores approximating the mean AUC for the compared methods was chosen.

The main finding is that the better metrics are observed for the 11-qbit SVM on the 11 feature dataset.

![image](https://user-images.githubusercontent.com/29145045/215255809-1b6aa076-098c-4f86-b676-295ab92e9c7e.png)

Therefore, it's probably best option to stick to the eleven feature set in order to remain in line with previous publications using classical ML. 

However, the eight feature set can be considered if the depth of the quantum circuit significantly affects the metrics in noisy quantum simulations or hardware experiments.


### References

Impact of train/test sample regimen on performance estimate stability of machine learning in cardiovascular imaging

https://www.nature.com/articles/s41598-021-93651-5#Tab3

2021 AHA/ACC/ASE/CHEST/SAEM/
SCCT/SCMR Guideline for the
Evaluation and Diagnosis of Chest Pain:

https://www.jacc.org/doi/pdf/10.1016/j.jacc.2021.07.053?_ga=2.85562654.649136116.1674121202-7665523.1671358677
