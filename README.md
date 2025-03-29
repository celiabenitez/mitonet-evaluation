# MitoNet Evaluation Pipeline

This repository contains the evaluation pipeline for MitoNet, a deep learning model for nuclear-level prediction of Ki-67 expression from H&E-stained breast cancer images. The pipeline is designed to evaluate MitoNet's performance on the Liu test set, providing comprehensive metrics and visualizations.

## Overview

MitoNet is a specialized ResNet-style classifier optimized for small patch classification of nuclei in H&E-stained images. It can predict Ki-67 expression at the nuclear level, potentially eliminating the need for costly and time-consuming immunohistochemistry (IHC) staining in breast cancer assessment.

The evaluation pipeline:
1. Loads the pre-trained MitoNet model
2. Evaluates it on the Liu test set (nearly 2300 samples)
3. Generates comprehensive metrics and visualizations
4. Analyzes error cases for further improvement

## Repository Structure

```
mitonet-evaluation/
├── best_model.pth                  # Pre-trained MitoNet model 
├── liu-evaluation.ipynb            # Evaluation notebook
├── liu-test-set/                   # Test dataset
│   ├── positive/                   # Ki-67 positive nuclei patches
│   └── negative/                   # Ki-67 negative nuclei patches
```

## Prerequisites

You can install all necessary dependencies using pip:

```bash
pip3 install torch torchvision torchaudio numpy matplotlib seaborn scikit-learn pandas pillow tqdm
```

## Usage

### 1. Clone the repository

```bash
git clone https://github.com/celiabenitez/mitonet-evaluation.git
cd mitonet-evaluation
```

### 2. Set up the Liu test set

Ensure the Liu test set is properly organized with the following structure:

```
liu-test-set/
├── positive/    # Contains Ki-67 positive nuclei patches
└── negative/    # Contains Ki-67 negative nuclei patches
```

Each directory should contain patch images (PNG, JPG, or JPEG) of the corresponding class.

### 3. Run Evaluation

Open the `liu-evaluation.ipynb` notebook and run all cells in the notebook to:
- Load and visualize samples from the test set
- Load the pre-trained MitoNet model
- Evaluate the model on the Liu test set
- Generate and display performance metrics
- Visualize error cases

## Evaluation Metrics

The evaluation pipeline reports the following metrics:

- Accuracy: Overall classification accuracy
- Precision: Ratio of true positives to all predicted positives
- Recall: Ratio of true positives to all actual positives
- F1 Score: Harmonic mean of precision and recall
- ROC-AUC: Area under the Receiver Operating Characteristic curve

## Credits
* **MitoNet model**: Developed by Celia Benitez Camacho, Esha Nasir, and Shan E Ahmed Raza at the University of Warwick
* **Liu et al. dataset**: Liu, Y., Li, X., Zheng, A., Zhu, X., Liu, S., Hu, M., Luo, Q., Liao, H., Liu, M., He, Y., & Chen, Y. (2020). Predict Ki-67 Positive Cells in H&E-Stained Images Using Deep Learning Independently From IHC-Stained Images. Frontiers in molecular biosciences, 7, 183. https://doi.org/10.3389/fmolb.2020.00183
