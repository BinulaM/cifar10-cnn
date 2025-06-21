# CIFAR-10 Image Classification using PyTorch

## 📌 Overview

This project is a coursework submission for ECS659U/A: Neural Networks & Deep Learning at Queen Mary University of London. It implements a specific Convolutional Neural Network (CNN) architecture to classify images from the CIFAR-10 dataset into 10 classes. The model strictly follows the architectural guidelines provided in the assignment specification, including a **Stem**, multiple **Expert Blocks** with **Soft Attention**, and a final **Classifier**.

The main objective was to achieve the highest possible test accuracy while maintaining a modular, well-documented, and readable codebase in **PyTorch**. The project achieved a peak test accuracy of **90.60%**, satisfying the top grade band requirement.

## 🧠 Model Architecture

Input Image → Stem → [Block 1 → ... → Block N] → Classifier → Output


### Components:
- **Stem**: A single convolutional layer for early feature extraction.
- **Blocks (B1 to BN)**: Each block includes:
  - An **expert branch** to generate attention weights via global average pooling + MLP + softmax.
  - **K convolutional branches**, merged using the learned soft attention vector.
- **Classifier**: A global average pooling followed by a fully connected layer to produce class probabilities.

## 🛠️ Technologies Used

- **Python 3.10**
- **PyTorch**
- **Google Colab**
- **Matplotlib & NumPy** for evaluation and visualization

## 🔧 Training Pipeline

- **Loss Function**: CrossEntropyLoss (with optional Label Smoothing)
- **Optimizer**: Adam
- **Scheduler**: StepLR (for learning rate decay)
- **Regularisation**: Weight Decay
- **Data Augmentation**:
  - `RandomHorizontalFlip`
  - `RandomCrop` with padding
  - `ColorJitter`
  - `RandomRotation`

## 📊 Results

| Metric               | Value     |
|----------------------|-----------|
| Final Test Accuracy  | **90.60%** |
| Best Epoch           | 110       |
| Total Epochs Trained | 240       |
| Training Time/Epoch  | ~1 minute |

Loss and accuracy plots are provided in the final report.

## 🗃️ Project Structure

.
├── cifar10_model.ipynb # Jupyter Notebook with full implementation
├── model/ # Contains model definition files (Stem, Block, Classifier)
├── utils/ # Data loaders, transform functions, and plotting tools
├── README.md # Project description
└── report.pdf # Final 3-page coursework report


## 🚀 How to Run

1. Clone this repository.
2. Open `cifar10_model.ipynb` on **Google Colab**.
3. Run all cells from top to bottom.
   - Ensure CIFAR-10 dataset is downloaded automatically by PyTorch.
   - Training, evaluation, and visualization are included in sequence.

## 📌 Notes

- This implementation strictly adheres to the coursework specification provided by Dr. Yorgos Tzimiropoulos.
- No external architectures or pretrained models were used.
- Collaboration or sharing was strictly prohibited per assignment rules.

## 🧾 Acknowledgements

- Coursework provided by the School of Electronic Engineering and Computer Science (EECS), QMUL.
- CIFAR-10 dataset: https://www.cs.toronto.edu/~kriz/cifar.html
- PyTorch Docs: https://pytorch.org/docs/stable/index.html
