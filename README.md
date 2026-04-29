<div align="center">

<br/>

```
╔═══════════════════════════════════════════════════════════════╗
║                                                               ║
║        ██████╗ ███████╗███╗   ██╗ █████╗ ██╗                 ║
║       ██╔════╝ ██╔════╝████╗  ██║██╔══██╗██║                 ║
║       ██║  ███╗█████╗  ██╔██╗ ██║███████║██║                 ║
║       ██║   ██║██╔══╝  ██║╚██╗██║██╔══██║██║                 ║
║       ╚██████╔╝███████╗██║ ╚████║██║  ██║██║                 ║
║        ╚═════╝ ╚══════╝╚═╝  ╚═══╝╚═╝  ╚═╝╚═╝                ║
║                                                               ║
║              L A B O R A T O R Y   F I L E S                 ║
║                                                               ║
╚═══════════════════════════════════════════════════════════════╝
```

# 🤖 Generative AI — Lab Experiments

### _Exploring the frontiers of probabilistic models, deep learning & generative systems_

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)

<br/>

---

</div>

## 👩‍💻 About the Author

| Field | Details |
|---|---|
| **Name** | Ishika |
| **Roll Number** | 2301420052 |
| **Course** | B.Tech — Data Science |
| **Year / Semester** | 3rd Year · 6th Semester |
| **University** | K.R. Mangalam University |
| **Subject** | Generative AI (Lab) |

---

## 📁 Repository Structure

```
GENAI-exppro/
│
├── 📓 2301420052_ISHIKA_GENAI_LABEXP.ipynb   ← Lab experiments notebook
│
└── 📂 Project/
    ├── 🌐 index.html                          ← MLE Explorer web app
    └── 📄 SPEC.md                             ← Project specification
```

---

## 🧪 Lab Experiments

The notebook `2301420052_ISHIKA_GENAI_LABEXP.ipynb` covers a wide range of Generative AI concepts, implemented from scratch:

<br/>

### 📊 Experiment 1 — Probability Distributions
> Visualizing **Normal** and **Uniform** distributions using NumPy & Matplotlib. Generates 1000 samples from each and plots side-by-side histograms to understand the shape and spread of data.

```python
normal_data  = np.random.normal(loc=0, scale=1, size=1000)
uniform_data = np.random.uniform(low=0, high=1, size=1000)
```

---

### 📐 Experiment 2 — Maximum Likelihood Estimation (MLE)
> Implements **MLE parameter estimation** for a Normal distribution. Generates synthetic data and uses sample mean & standard deviation as MLE estimators.

```python
mu_estimate    = np.mean(data)       # MLE for mean
sigma_estimate = np.std(data)        # MLE for std deviation
```

---

### 🧠 Experiment 3 — Neural Network on MNIST (SGD)
> Builds a **Feedforward Neural Network** using TensorFlow/Keras to classify handwritten digits from the MNIST dataset. Trained with SGD optimizer over 5 epochs.

```
Architecture:  Flatten(28×28) → Dense(128, ReLU) → Dense(10, Softmax)
Optimizer:     SGD
Dataset:       MNIST (60k train / 10k test)
```

---

### 🎨 Experiment 4 — Generative Adversarial Network (GAN) — Architecture
> Defines a basic **GAN skeleton** with a Generator and Discriminator. Generator maps 100-dim noise → 784-dim image space; Discriminator classifies real vs. fake.

```
Generator:      Dense(100→128, ReLU) → Dense(128→784, Sigmoid)
Discriminator:  Dense(784→128, ReLU) → Dense(128→1, Sigmoid)
```

---

### 🌊 Experiment 5 — Flow-Based Model (Sketch)
> Implements a skeleton of a **flow-based generative model** using dense layers, illustrating the concept of bijective transformations for density estimation.

---

### 📏 Experiment 6 — Evaluation Metrics
> Computes core **classification metrics** — Accuracy, Precision, and Recall — using `sklearn.metrics` to evaluate model performance on ground-truth labels.

```python
accuracy  = accuracy_score(y_true, y_pred)    # → 0.8
precision = precision_score(y_true, y_pred)   # → 1.0
recall    = recall_score(y_true, y_pred)      # → 0.67
```

---

### ⚡ Experiment 7 — Neural Network on MNIST (Adam)
> Repeats the MNIST classification task using the **Adam optimizer** — demonstrating its convergence advantage over SGD with a leaner 64-neuron hidden layer.

```
Architecture:  Flatten(28×28) → Dense(64, ReLU) → Dense(10, Softmax)
Optimizer:     Adam   |   Epochs: 3
```

---

### 🔁 Experiment 8 — Autoencoder
> Designs a **2-bottleneck Autoencoder** for MNIST — compresses 784-dim input to a 2-dimensional latent space, then reconstructs it. Useful for dimensionality reduction and data generation.

```
Encoder:  Flatten → Dense(64, ReLU) → Dense(2)
Decoder:  Dense(64, ReLU) → Dense(784, Sigmoid) → Reshape(28,28)
```

---

### 📝 Experiment 9 — Recurrent Neural Network (RNN)
> Builds a **Simple RNN language model** using an Embedding layer + SimpleRNN for text generation tasks. Maps token sequences to next-word predictions over a vocabulary of 1000 tokens.

```
Embedding(1000, 64) → SimpleRNN(128) → Dense(1000, Softmax)
```

---

### 📉 Experiment 10 — GAN Loss Dynamics
> Simulates and analyzes **adversarial training loss curves** for both Generator and Discriminator, illustrating the minimax game at the core of GAN training.

---

---

## 🌐 Project — MLE Explorer Web App

An **interactive single-page web application** for visualizing Maximum Likelihood Estimation in real time.

### ✨ Features
- 🔵 **Distribution Toggle** — Switch between Normal & Exponential distributions
- 🎲 **Sample Generator** — Generate n random samples using Box-Muller / Inverse Transform
- 📈 **Live Histogram** — Overlaid with true & estimated PDF curves (Chart.js)
- 📉 **Log-Likelihood Surface** — Visual curve showing the optimal parameter
- 📋 **Results Dashboard** — True vs. estimated parameters, Bias, MSE
- 💡 **Educational Tooltips** — Learn each concept on hover
- 📱 **Fully Responsive** — Works on mobile and desktop

### 🎨 Tech Stack
```
Frontend:   HTML5 · CSS3 · Vanilla JavaScript
Charts:     Chart.js
Design:     Dark theme (Deep Navy + Cyan accents)
Fonts:      Outfit · IBM Plex Mono
```

### 📐 MLE Formulas Implemented

**Normal Distribution:**
$$\hat{\mu} = \frac{1}{n}\sum x_i \qquad \hat{\sigma}^2 = \frac{1}{n}\sum(x_i - \hat{\mu})^2$$

**Exponential Distribution:**
$$\hat{\lambda} = \frac{1}{\bar{x}} = \frac{n}{\sum x_i}$$

---

## 🛠️ How to Run

### Jupyter Notebook
```bash
# Clone the repository
git clone https://github.com/<your-username>/GENAI-exppro.git
cd GENAI-exppro

# Install dependencies
pip install numpy scipy tensorflow scikit-learn matplotlib pandas

# Launch notebook
jupyter notebook 2301420052_ISHIKA_GENAI_LABEXP.ipynb
```

### Web App (MLE Explorer)
```bash
# Just open it in your browser — no server needed!
open Project/index.html
```

---

## 📚 Concepts Covered

| Topic | Status |
|---|---|
| Probability Distributions | ✅ |
| Maximum Likelihood Estimation | ✅ |
| Feedforward Neural Networks | ✅ |
| Generative Adversarial Networks | ✅ |
| Autoencoders | ✅ |
| Flow-Based Models | ✅ |
| Recurrent Neural Networks | ✅ |
| Model Evaluation Metrics | ✅ |
| MLE Convergence Analysis | ✅ |
| Interactive Data Visualization | ✅ |

---

<div align="center">

<br/>

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  Made with 💙 by Ishika  ·  Roll No. 2301420052
  B.Tech Data Science · 3rd Year · 6th Semester
  K.R. Mangalam University
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

_"In the world of generative AI, every sample tells a story."_

</div>
