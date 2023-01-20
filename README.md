# qml-cad

## Quantum Machine Learning  for Coronary Artery Disease

These notebooks explore the metrics obtained by classical and quantum support vector machine with different random seeds for the partition into training and test sets.

Two versions: the eleven feature regularly tested in classical ML and the eight feature exhibiting the best correlation with the label CAD / NoCAD

The dataset was obtained  from: https://ieee-dataport.org/open-access/heart-disease-dataset-comprehensive

Absurd values of 0.0 for cholesterol and for blood pressure underwent mean substitution, because we are sure that these are missing values (more sophisticated methods for missing data can of course be contemplated).

11 feature set: ['age', 'sex', 'chest pain type','resting bp s','cholesterol','fasting blood sugar',
                 'resting ecg','max heart rate','exercise angina', 'oldpeak', 'ST slope'] 

8 feature sets : ['age', 'sex', 'chest pain type','fasting blood sugar',
                 'max heart rate','exercise angina', 'oldpeak', 'ST slope'] 

The feature drop is on basis of poor correlation with the target. 

No difference in the metrics is observed for the eleven feature set between classical and quantum SVM. However, the accuracy is stastically significantly lower quantum SVM when 8 features are used.

Therefore, it's probably best option to stick to the eleven feature set in order to remain in line with previous publications using classical ML. 

However, the eight feature set can be considered if the depth of the quantum circuit significantly affects the metrics in noisy quantum simulations or hardware experiments.

NOTE: For the eleven feature dataset, the ECG at rest has values 0, 1 and 2. ST-T abnormality (Value 1) has a priori a higher correlation with coronary artery disease than left ventricular hypertrophy (Value 2). Value 0 is for normal ECG. Therefore I looked at the correlation in the data That confirmed the a priori expectation. This leads to a proposal to recode the attribute: 1 for left ventricular hypertrophy and 2 for ST-T abnormality. The notebook recoding_resting_ecg shows that the AUC score is then better, with a value of 0.90 for classical _and_ quantum SVM.

ROC curve after recoding the resting_ecg attribute:

![image](https://user-images.githubusercontent.com/29145045/213746071-f1610960-bcdd-411e-a674-6da638fb257d.png)


### References

Impact of train/test sample regimen on performance estimate stability of machine learning in cardiovascular imaging

https://www.nature.com/articles/s41598-021-93651-5#Tab3

2021 AHA/ACC/ASE/CHEST/SAEM/
SCCT/SCMR Guideline for the
Evaluation and Diagnosis of Chest Pain:

https://www.jacc.org/doi/pdf/10.1016/j.jacc.2021.07.053?_ga=2.85562654.649136116.1674121202-7665523.1671358677
