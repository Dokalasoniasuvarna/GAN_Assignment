# Generative Adversarial Networks — From Scratch and Real-World Applications

This repository contains a complete GAN coursework implementation, starting with GANs built from scratch on synthetic 2D data and extending them to three real-world applications: **medical imaging, cybersecurity, and creative sketch generation**.

## Repository Contents

| File                        | Description                                               |
| --------------------------- | --------------------------------------------------------- |
| `Sony_GAN_Assignment.ipynb` | Complete implementation, experiments, figures and results |
| `requirements.txt`          | Required Python dependencies                              |
| `README.md`                 | Project overview and setup instructions                   |

> The written coursework report is submitted separately.

## Project Overview

### Part 1 — GANs from Scratch

A PyTorch GAN is developed and tested on synthetic 2D distributions:

* Sine-wave distribution
* 3×3 mixture of Gaussians
* Generator architecture comparison using different depths and activation functions

Real and generated samples are compared visually to examine how well the GAN learns each target distribution.

### Part 2 — Real-World Applications

| Section | Domain          | Dataset     | Model        | Framework        |
| ------- | --------------- | ----------- | ------------ | ---------------- |
| **2.1** | Medical Imaging | OCTMNIST    | DCGAN + cGAN | TensorFlow/Keras |
| **2.2** | Cybersecurity   | CICIDS 2017 | Dense GAN    | PyTorch          |
| **2.3** | Creative AI     | QuickDraw   | DCGAN        | TensorFlow/Keras |

**OCTMNIST:** A DCGAN generates synthetic retinal OCT images, evaluated visually and using FID. A conditional GAN extension generates specific OCT classes on demand.

**CICIDS 2017:** A GAN generates synthetic network-traffic feature vectors. The main experiment uses Wednesday BENIGN/DoS traffic, followed by an extension using data from all available days.

**QuickDraw:** A DCGAN generates birthday-cake sketches. The extension also explores **cat** and **house** categories and compares generation quality across classes.

## Key Results

| Experiment                           |                    Result |
| ------------------------------------ | ------------------------: |
| OCTMNIST FID ↓                       |                 **17.89** |
| CICIDS Wednesday mean / std gap ↓    |       **0.2435 / 0.2395** |
| CICIDS All-Days mean / std gap ↓     |       **0.2955 / 0.5277** |
| QuickDraw FID — cake / cat / house ↓ | **25.56 / 28.51 / 41.98** |

## Running the Notebook

Create an environment and install the dependencies:

```bash
python -m venv venv
pip install -r requirements.txt
```

Activate the environment and open:

```text
Sony_GAN_Assignment.ipynb
```

Run all cells in order using **Kernel → Restart & Run All**.

A CUDA-enabled GPU or Google Colab is recommended for the image GAN experiments.

## Datasets

* **OCTMNIST:** downloaded through the `medmnist` package.
* **CICIDS 2017:** obtained from the public Kaggle Network Intrusion Dataset.
* **QuickDraw:** bitmap data obtained from the Google QuickDraw dataset.

Random seeds are fixed for reproducibility.

## References

The project follows established GAN research including **Goodfellow et al. (2014)**, **Radford et al. (2015)**, **Mirza & Osindero (2014)** and **Heusel et al. (2017)**.


