# PyTorch Notes

This repository is a collection of my personal notes and practice notebooks while learning PyTorch.

> Note: This README was generated with the help of an AI assistant.

## Overview

In this project I explored the core building blocks of deep learning with PyTorch, focusing on:

- Artificial Neural Networks (ANN)
- Convolutional Neural Networks (CNN)
- Recurrent Neural Networks (RNN)
- Data loading utilities (`Dataset` and `DataLoader`)
- Training loops, optimization, and basic hyperparameter tuning

Each notebook in the root of the repository focuses on a specific concept or experiment.

## Contents

- `pytorch.ipynb`: First steps with tensors, gradients, and basic PyTorch APIs.
- `pytorch_nn_module.ipynb`: Using `nn.Module` to build neural network architectures.
- `ann_practice.ipynb`: Implementing and training fully connected neural networks (ANNs).
- `cnn.ipynb` / `cnn_practice.ipynb`: Building and training convolutional neural networks, mainly for image classification.
- `rnn_practice.ipynb`: Experiments with recurrent neural networks for sequence data.
- `data_loader_and_dataset.ipynb`: Creating custom datasets and using `DataLoader` for efficient batching and shuffling.
- `fasion_mnist_ann.ipynb`: Training an ANN on Fashion-MNIST, including preprocessing and evaluation.
- `optimised_nn.ipynb`: Trying different architectures and hyperparameters to improve performance.
- `hyperparameter_tuning_on_cnn.ipynb`: Exploring the effect of learning rate, batch size, epochs, and other hyperparameters on CNN performance.
- `first _ret.ipynb`: Early experiments and quick tests while getting familiar with the library.

The dataset folders:

- `sign_mnist_train/` and `sign_mnist_test/`: CSV-based sign language MNIST datasets used for classification experiments.

## What I Learned

- How to work with tensors, automatic differentiation, and GPU acceleration in PyTorch.
- How to define models using `nn.Module` and `nn.Sequential`.
- How to write training and evaluation loops with loss functions and optimizers.
- How to prepare data with `Dataset` and `DataLoader`, including custom datasets.
- How to build and train ANN, CNN, and RNN architectures for different tasks.
- How to experiment with hyperparameters (learning rate, batch size, number of layers, etc.) to improve model performance.

## Quick Revision Notes

### ANN (Artificial Neural Networks)

- Basic building block: stacked linear layers with activation functions (e.g. ReLU, Sigmoid, Tanh).
- Typical structure in PyTorch: `nn.Linear` layers inside an `nn.Module` or `nn.Sequential`.
- Used mainly for tabular data or flattened image inputs (e.g. Fashion-MNIST with fully connected layers).
- Training loop pattern: forward pass → compute loss (e.g. `nn.CrossEntropyLoss`) → `loss.backward()` → `optimizer.step()` → `optimizer.zero_grad()`.

### CNN (Convolutional Neural Networks)

- Key layers: `nn.Conv2d`, `nn.MaxPool2d` / `nn.AvgPool2d`, followed by fully connected layers.
- Convolutions learn spatial features from images using filters/kernels; pooling reduces spatial size and adds invariance.
- Common pattern: `[Conv2d → ReLU → Pool]` repeated, then `Flatten` and `Linear` layers for classification.
- Often used with image datasets like MNIST, Fashion-MNIST, or Sign-MNIST.
- Important hyperparameters: number of filters, kernel size, stride, padding, learning rate, batch size, and regularization (dropout, weight decay).

### RNN (Recurrent Neural Networks)

- Designed for sequence data (text, time series, etc.) by maintaining a hidden state across time steps.
- Core modules: `nn.RNN`, `nn.LSTM`, `nn.GRU` (LSTM/GRU help with long-term dependencies and vanishing gradients).
- Input shape for many RNN APIs: `(seq_len, batch, input_size)` or `(batch, seq_len, input_size)` depending on `batch_first`.
- Typical flow: embed/encode input → pass through RNN/LSTM/GRU → use last hidden state (or all outputs) for prediction.
- Important hyperparameters: hidden size, number of layers, sequence length, bidirectional vs unidirectional, dropout.

## How to Use This Repo

1. Create and activate a Python environment.
2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Open the notebooks (e.g. in VS Code or Jupyter) and run the cells to explore the code and experiments.

This repository is meant as a learning journal rather than a polished library, so feel free to modify the notebooks, try new architectures, and extend the experiments.
