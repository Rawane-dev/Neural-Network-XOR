# XOR Neural Network

A simple neural network built with TensorFlow/Keras that learns the XOR logical operation.

## Overview

The XOR problem is a classic benchmark for neural networks since it's not linearly separable — a single-layer perceptron cannot solve it. This project demonstrates how a small multi-layer network can learn the pattern.

| Input A | Input B | XOR Output |
|---------|---------|------------|
| 0       | 0       | 0          |
| 0       | 1       | 1          |
| 1       | 0       | 1          |
| 1       | 1       | 0          |

## Model Architecture

- **Input layer:** 2 neurons (one per input bit)
- **Hidden layer:** 4 neurons with `tanh` activation
- **Output layer:** 1 neuron with `sigmoid` activation
- **Optimizer:** Adam
- **Loss:** Binary Cross-Entropy
- **Epochs:** 1000

## How It Works

1. **Forward Propagation** — Inputs pass through the hidden layer (tanh) then the output layer (sigmoid), producing a value between 0 and 1.
2. **Error Computation** — Binary cross-entropy loss compares predictions to the true XOR outputs.
3. **Backpropagation** — Gradients are computed layer by layer using the chain rule.
4. **Weight Updates** — The Adam optimizer adjusts weights each epoch to minimize loss.

## Requirements

```bash
pip install tensorflow numpy pandas
```

## Usage

Open and run `script.ipynb` in Jupyter Notebook or JupyterLab.

```bash
jupyter notebook script.ipynb
```

## Results

The model achieves **75% accuracy** after 1000 epochs, correctly classifying 3 out of 4 XOR patterns. This is a known limitation of small networks with random weight initialization — re-running training often yields 100% accuracy.
