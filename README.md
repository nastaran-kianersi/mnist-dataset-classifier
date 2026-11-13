# Machine Learning Course Final Project

This project was completed in 2020 for a machine learning course. It explores handwritten digit classification on the MNIST dataset (digits 0–9), implementing a baseline neural network and comparing it with convolutional neural networks trained with different settings.

## Solution and Results

The baseline is a multilayer perceptron (MLP) with 784 input features, two 64-neuron hidden layers using ReLU, and a 10-class output. Images are normalized, and the training data is split for validation. The best model by validation accuracy is saved and evaluated on the test set, where it achieves **97.75%** accuracy.

The optional section evaluates a CNN with two convolutional layers (64 and 32 filters) and a 10-class output. Experiments compare ReLU and Softmax activations and several learning rates with Adam and SGD optimizers. According to the report, the CNN with SGD and ReLU reaches about **98%** test accuracy at a learning rate of 0.01; a rate of 0.001 reaches about **95%**, while 0.1 performs poorly. With SGD and Softmax, a rate of 0.1 reaches about **95%**, while lower rates perform poorly within the tested number of epochs. In the Adam experiments, ReLU trains faster than Softmax, but Softmax is reported to achieve higher accuracy. See the [full project report](report.pdf) for plots and additional results. The report is in Persian language.

Model scripts: [MNIST_MLP.py](MNIST_MLP.py), [CNN_Adam.py](CNN_Adam.py), and [CNN_SGD.py](CNN_SGD.py).

## Setup and Usage

The original scripts are preserved as written and use legacy TensorFlow/Keras APIs. Use **64-bit Python 3.8** with TensorFlow 2.2 and Keras 2.4.3, the versions listed in [requirements.txt](requirements.txt). Python 3.6 is the minimum for this code and dependency set; Python 3.8 is recommended. These pinned legacy dependencies do not support newer Python versions.

Create and activate a virtual environment from the project directory. On Windows PowerShell:

```powershell
py -3.8 -m venv .venv
.\.venv\Scripts\Activate.ps1
```

On macOS or Linux:

```bash
python3.8 -m venv .venv
source .venv/bin/activate
```

With the environment activated, install TensorFlow, Keras, and the other dependencies:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Run any script from the project directory:

```bash
python MNIST_MLP.py
python CNN_Adam.py
python CNN_SGD.py
```

The first run downloads and caches MNIST in the system's temporary directory, so an internet connection is required. Each script trains its model(s), saves the best checkpoint and reports test accuracy. Deactivate the environment when finished with `deactivate`.

These are legacy package versions provided to match the original code, not as a recommendation for new projects.

## Dataset & Acknowledgments
This project uses the **MNIST handwritten digit database** created by Yann LeCun, Corinna Cortes, and Christopher J.C. Burges. The dataset consists of 60,000 training images and 10,000 testing images of handwritten digits.

### Citation
> LeCun, Y., Cortes, C., & Burges, C. J. (2010). *MNIST handwritten digit database*. ATT Labs. Available via [Hugging Face](https://huggingface.co/datasets/ylecun/mnist).
