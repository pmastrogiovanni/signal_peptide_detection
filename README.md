# Signal Peptide Detection

Nascent proteins within cells must be transported to different compartments or organelles. To direct this transportation, proteins have intrinsic hydrophobic signal peptides (SP), functioning as "address tag". Developing a model to predict the presence of these peptides might provide new insights about the function and interactions of proteins with low experimental data, and may also reveal new potential targets.

To address the task, two different models were tested: The Von Hejine algorithm based on a position specific weight matrix (PSWM), and a support vector machine (SVM). Both methods were trained, validated (5-fold CV) and tested on the SignalP-5.0 datasets, relying on the UniprotKB database. 

Performances of the model were compared with various metrics (MCC, ACC, precision, recall, F1). The support vector machine proved to be more efficient in the classification, having 0.86% mcc versus the 0.78% obtained using the PSWM. 

Moreover, since both methods committed many misclassifications, the dataset was inspected for a wrong predition analysis. Most of the false positives presented transit peptides and transmembrane alpha helices in their sequence, structures that have a similar hydrophobic composition to the SPs, which justifies the misclassification. On the other hand, false negatives presented a different SP length and aminoacidic composition compared to the overall distribution observed on the dataset. Given these facts, the errors were caused by assumptions on which the models were trained, and probably, by exploiting different features, the overall performances might improve.

Complete code is available in the jupyter notebook, and more details about the project are contained in the pdf files.
