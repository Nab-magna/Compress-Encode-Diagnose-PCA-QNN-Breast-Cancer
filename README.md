This repository presents a comprehensive comparison between Hybrid Quantum Machine Learning (HQML) models and classical machine learning models, evaluated on the breast cancer dataset. We explore the performance of a Quantum Support Vector Machine (QSVM) with angle feature mapping, a Variational Quantum Classifier (VQC) with PCA and a custom feature map, and a classical SVM with an RBF kernel.



Table of Contents





Introduction



Installation



Usage



Results



Discussion



Contributing



License



Acknowledgments



Introduction

This repository investigates the capabilities of quantum-enhanced machine learning by benchmarking HQML models against a classical baseline using the breast cancer dataset. The dataset, a standard benchmark for binary classification, involves predicting whether a tumor is malignant or benign based on feature data.

The experiments include:





Quantum Support Vector Machine (QSVM) with angle feature mapping.



Variational Quantum Classifier (VQC) with PCA dimensionality reduction and a custom feature map, utilizing 5 qubits.



Classical Support Vector Machine (SVM) with an RBF kernel.

Our objective is to evaluate and compare the accuracy of these models, shedding light on the potential of quantum computing in machine learning applications.



Installation

To run the experiments, ensure you have Python installed and follow these steps to set up the environment:





Clone the Repository:

git clone https://github.com/yourusername/yourrepository.git
cd yourrepository



Create a Virtual Environment:

python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate



Install Dependencies:

pip install -r requirements.txt

Note: The quantum experiments require a quantum computing framework. This repository uses Qiskit, which supports both simulators and real quantum hardware.



Usage

Dataset

The breast cancer dataset is sourced from scikit-learn's datasets module. It is preprocessed with an 80:20 train-test split.

Experiments

QSVM with Angle Feature Mapping





Script: qsvm_experiment.py



Feature Map: Angle encoding



Quantum Backend: Qiskit simulator



Command:

python qsvm_experiment.py

Classical SVM with RBF Kernel





Script: classical_svm.py



Kernel: RBF



Parameters: C=1.0, gamma='scale'



Command:

python classical_svm.py

PCA + VQC with Custom Feature Map





Script: vqc_experiment.py



Dimensionality Reduction: PCA (5 dimensions)



Feature Map: Custom (rotation gates)



Quantum Circuit: 5 qubits



Optimizer: COBYLA



Command:

python vqc_experiment.py

Each script trains its respective model and outputs the accuracy on the test set.



Results

The experimental results are summarized below:







Model



Accuracy





QSVM (angle feature mapping)



95%





Classical SVM (RBF kernel)



96.49%





PCA + VQC (custom feature map)



96%

The classical SVM slightly outperforms the quantum models, but the HQML approaches demonstrate highly competitive results, highlighting their promise for future quantum machine learning applications.



Discussion

The classical SVM with an RBF kernel achieved the highest accuracy at 96.49%, leveraging its robust optimization for this dataset. The PCA + VQC model, with 96% accuracy, closely rivals the classical approach, suggesting that quantum variational methods, combined with dimensionality reduction, hold significant potential. The QSVM, at 95%, performs slightly below the others, possibly due to limitations in the angle feature mapping or current quantum hardware constraints.

Future enhancements could include exploring alternative feature maps, scaling up qubit counts, or testing additional quantum algorithms to further close the performance gap.



Contributing

We welcome contributions! To enhance the experiments or propose new models, please fork the repository and submit a pull request with your changes.



License

This project is licensed under the MIT License.



Acknowledgments

We express gratitude to the scikit-learn team for providing the breast cancer dataset and to the Qiskit community for their quantum computing tools and support.
