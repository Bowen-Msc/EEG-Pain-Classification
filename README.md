# EEG-Pain-Classification
A Hybrid Feature Engineering Framework for EEG Pain Classification
<img width="469" height="683" alt="image" src="https://github.com/user-attachments/assets/a42f1ed8-ee24-445a-a640-7f0a45b2c9e7" />


# Abstract
Objective pain quantification is a key issue that urgently needs to be addressed in clinical medicine. Currently, reliance on subjective self-reports is infeasible for patients who are unable to express themselves verbally or have cognitive impairments, which hinders accurate diagnosis and treatment. Although existing physiological measurement methods often lack specificity, electroencephalography (EEG) provides a direct and non-invasive approach to observe the pain processing in the brain. This study aims to leverage the high temporal resolution of electroencephalogram (EEG) to develop a machine learning framework that can objectively distinguish different types of induced pain states, and the characteristics of the frequency bands and the functional connectivity of different experimental groups were analysed respectively. The study collected EEG data from 22 healthy subjects under cold and hot pain stimuli (applied to both hands, with eyes open and closed) and in the baseline state. Methodologically, a hybrid feature engineering strategy was proposed: first, time-frequency statistical moments (mean, variance, skewness, kurtosis) were extracted from five frequency bands (Delta, Theta, Alpha, Beta, Gamma) for each channel using the Choi-Williams Distribution (CWD); second, functional connectivity networks were constructed using the weighted Phase Lag Index (wPLI), from which graph-theoretical metrics (node strength and global efficiency) were derived. After feature dimensionality reduction using t-tests and Sequential Forward Selection (SFS), four machine learning models (including Random Forest, SVM, KNN and Decision Tree) were used for classification. The results indicate that the Random Forest model achieved the best performance across all experimental conditions, with a peak classification accuracy of 91.76%. The key findings are that cold pain is mainly characterized by altering the energy magnitude (mean value) of low-frequency (Delta) oscillations, while heat pain is characterized by changing the energy distribution pattern (skewness) of the Delta and Gamma bands. Moreover, the study confirmed the lateralization effect of the brain hemispheres in pain processing, that is, left-hand stimulation can generate more easily classified neural signals. This study has verified a new method for interpreting the neural characteristics of pain, opening a new path for objective clinical pain diagnosis.

# Result
Experimental Group	SVM Accuracy (%)	KNN Accuracy (%)	Decision Tree Accuracy (%)	Random Forest Accuracy (%)
HAND-LCP-EC vs Baseline-EC	84.12	84.26	85.44	91.76
HAND-LCP-EO vs Baseline-EO	82.22	86.59	84.30	90.22
HAND-RCP-EC vs Baseline-EC	80.66	82.57	82.94	89.41
HAND-RCP-EO vs Baseline-EO	77.16	79.54	72.98	81.56
HAND-LHP-EC vs Baseline-EC	72.29	72.35	73.53	80.90
HAND-LHP-EO vs Baseline-EO	79.50	75.16	75.70	84.24
HAND-RHP-EC vs Baseline-EC	70.24	66.54	68.68	72.94
HAND-RHP-EO vs Baseline-EO	68.53	66.69	69.93	74.26

Experimental Group	Classifier	Sensitivity	Specificity
HAND-LCP-EC vs Baseline-EC	SVM	79.12	87.21
	KNN	81.03	86.77
	Decision Tree	83.38	83.53
	Random Forest	88.09	93.83
HAND-LCP-EO vs Baseline-EO	SVM	77.04	85.48
	KNN	83.70	89.48
	Decision Tree	80.74	81.93
	Random Forest	89.04	88
HAND-RCP-EC vs Baseline-EC	SVM	81.18	83.68
	KNN	77.21	87.21
	Decision Tree	83.53	86.18
	Random Forest	84.71	90
HAND-RCP-EO vs Baseline-EO	SVM	73.49	73.78
	KNN	71.33	75.50
	Decision Tree	70.46	68.59
	Random Forest	78.10	74.78
HAND-LHP-EC vs Baseline-EC	SVM	65.15	85.29
	KNN	71.77	70
	Decision Tree	70.59	68.24
	Random Forest	76.62	81.18
HAND-LHP-EO vs Baseline-EO	SVM	73.45	75.93
	KNN	75.93	67.39
	Decision Tree	76.40	74.38
	Random Forest	85.72	77.02
HAND-RHP-EC vs Baseline-EC	SVM	60.88	80.88
	KNN	65.74	63.97
	Decision Tree	68.82	68.27
	Random Forest	63.09	64.85
HAND-RHP-EO vs Baseline-EO	SVM	66.18	59.56
	KNN	60.15	63.82
	Decision Tree	63.68	67.35
	Random Forest	69.56	73.97
# Conclusion
The core contribution of this study lies in the successful construction and verification of a machine learning framework that can objectively distinguish different induced pain states, and based on this, it reveals the changes in frequency bands and functional connectivity exhibited by the brain for different pain types. The novelty of this study lies in the extraction of features through the combination of CWD and graph theory methods, and the completion of feature selection using t-test and SFS methods. Finally, four classifiers are used for classification. Among them, the random forest model, due to its advantage in handling high-dimensional and complex data, performed the best under all conditions, with the highest accuracy reaching 91.76%, a sensitivity of 89%, and a specificity of 94%. At the neural oscillation level, pain suppresses the Alpha and Beta band power in the posterior brain regions while enhancing the Gamma band activity in the brain. At the functional connectivity level, pain can trigger the reorganization of the whole brain network, among which the weakened connection in the prefrontal polar region (Fp1) is a recurring feature. On this basis, further feature analysis revealed deeper coding differences. Analysis shows that this decidability stems from two key factors: Firstly, the lateralization effect of the cerebral hemispheres, that is, left-hand stimulation (dominated and processed by the right brain) can generate more stable and easily classifiable neural responses; Secondly, there are differences in the encoding of pain modes. Specifically, cold pain is mainly encoded by changing the energy magnitude (mean) of low-frequency (Delta) oscillations, while hot pain relies on more subtle changes in the energy distribution pattern (skewness) of Delta and Gamma bands. The combined effect of these two factors also explains why the classification accuracy of the right hand's hot pain state is the lowest, as it combines a weaker hemispheric response with more complex neural signals.
	However, due to the limited duration of the research and the fact that the research samples were restricted to healthy subjects, this imposed limitations on the specificity of the pain classification. Future research should focus on extending this analytical framework to the legs and incorporating data on different levels of pain for classification to explore more robust markers of pain-related neural activity. Furthermore, the introduction of more advanced deep learning models (such as convolutional neural networks) is expected to further enhance the classification performance. These future explorations will drive the advancement of precision medicine.
