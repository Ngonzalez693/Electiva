# Deep Learning — From Single Neurons to Convolutional Networks

Coursework repository for the Deep Learning elective of the Systems Engineering program at
Universidad de San Buenaventura Cali. The notebooks follow a deliberate progression: first the
learning rule of a single neuron implemented from first principles with NumPy, then multi-layer
networks, and finally convolutional architectures with TensorFlow/Keras.

Everything in `Neurons/` and `Activation Functions/` is written without a deep learning framework —
weights, forward pass, error and update rule are coded by hand. `MLP/` and `CNN/` move to Keras once
the underlying mechanics are understood.

---

## Repository structure

```
Activation Functions/   Step, sigmoid, tanh and ReLU — plotted and compared
Neurons/
  Perceptron/           Perceptron implemented from scratch (NumPy)
  Adaline/              Adaline / LMS implemented from scratch (NumPy)
MLP/                    Multi-layer perceptrons for classification and regression (Keras)
CNN/                    Convolution fundamentals and CNNs for images and 1D signals (Keras)
```

---

## Contents

### Activation Functions

| Notebook | What it covers |
|---|---|
| `ActivationFunctions.ipynb` | Step, sigmoid, tanh and ReLU implemented in NumPy and plotted side by side to compare shape, range and saturation behaviour. |

### Neurons — implemented from scratch

**Perceptron**

| Notebook | What it covers |
|---|---|
| `Peceptron.ipynb` | Base perceptron: step activation, prediction, training loop and weight update rule. Error curve across epochs and resulting decision boundary. |
| `Perceptron2Outputs.ipynb` | Extension to a two-output perceptron with one weight vector per output. |
| `PerceptronNumbers.ipynb` | Digit recognition from binary matrix patterns. Includes a robustness test where noise is injected into the input and predictions are compared against the clean case. |
| `PuntoABC.ipynb` | Same idea applied to the lowercase letters a, b and c, again evaluated with and without noise. |

**Adaline**

| Notebook | What it covers |
|---|---|
| `Adaline.ipynb` | Adaline with linear activation and squared-error minimisation — the contrast against the perceptron's step rule. |
| `AdalineMultipleOutputs.ipynb` | Multi-output version: a weight matrix with one row per output signal. |
| `AdalineMultOutpUpgrade.ipynb` | The same network refactored into an `AdalineMultiOutput` class with configurable input size, output size, learning rate and epochs. |
| `PuntoSonido.ipynb` | Audio application: signals recorded with `sounddevice` are normalised and an Adaline network is trained to recover the original sources from the mixture. Evaluated with the error curve and the correlation between recovered and original audio. |

### MLP — multi-layer perceptrons (Keras)

| Notebook | What it covers |
|---|---|
| `clasificador_iris.ipynb` | Iris classification with a dense network, standardised inputs and L2 regularisation. |
| `clasificador_de_plantas_.ipynb` | Iris again, focused on exploratory analysis: feature distributions, 3D visualisation and confusion matrix. |
| `clasificador_vinos.ipynb` | Wine dataset classification, comparing optimisers and regularisation settings. |
| `regression_diabetes.ipynb` | Regression on the diabetes dataset with a dense network and scaled features. |
| `regression_function.ipynb` | Function approximation: the network learns `sin(x1) + log(x2+1) + x1·x2` from sampled data, evaluated with MAPE. |
| `metrics.ipynb` | Evaluation metrics for multi-class problems — precision, recall, F1, accuracy, ROC AUC and ROC curves over binarised labels. |

### CNN — convolutional networks (Keras)

| Notebook | What it covers |
|---|---|
| `ejemplo_filtros.ipynb` | Convolution before the network: blur, sharpen and horizontal/vertical edge kernels applied manually with OpenCV to show what a filter actually does to an image. |
| `clasificador_CNN.ipynb` | CIFAR-10 classifier — stacked `Conv2D` + `MaxPooling2D` blocks with dropout and a softmax output over 10 classes. |
| `regresion_cnn.ipynb` | MNIST treated as a regression problem: the network predicts the digit as a continuous value instead of a class. |
| `regresion_CNN1D.ipynb` | 1D CNN over a synthetic noisy sinusoid, using a sliding window of past values to predict the next one. |

---

## Requirements

```bash
pip install numpy matplotlib pandas seaborn scikit-learn tensorflow opencv-python sounddevice
```

`sounddevice` is only needed for `Neurons/Adaline/PuntoSonido.ipynb`, and `opencv-python` only for
`CNN/ejemplo_filtros.ipynb`. The CIFAR-10 and MNIST datasets download automatically through Keras;
Iris, Wine and Diabetes come bundled with scikit-learn.

## Running the notebooks

```bash
git clone https://github.com/Ngonzalez693/DeepLearning.git
cd DeepLearning
jupyter notebook
```

The notebooks are self-contained and can be run in any order, though they read best in the order
listed above. `CNN/ejemplo_filtros.ipynb` expects an image named `ejemplo.jpg` in the same folder.

---

## Author

**Nicolás González Toro** — Software Engineer · Multimedia Engineer, Universidad de San Buenaventura Cali

[LinkedIn](https://www.linkedin.com/in/nicolas-gonzalez-toro) · [GitHub](https://github.com/Ngonzalez693) · [Behance](https://www.behance.net/ngonzalez693)
