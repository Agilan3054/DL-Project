# Anomalous Sound Detection for Machine Condition Monitoring

## Project Overview

Anomalous Sound Detection (ASD) is the task of identifying whether the sound emitted from a target machine is normal or anomalous. In this project, we aim to build an ASD system for machine condition monitoring. The goal is to infer a machine's performance and working health from the sounds it produces. The project's key requirements include:

- Training a model using only normal sound (unsupervised learning scenario).
- Detecting anomalies regardless of domain shifts (domain generalization task).
- Training a model for a completely new machine type.
- Training a model using a limited number of machines from its machine type.

## Project Scope

Automatic detection of mechanical failure is a critical technology in the context of the fourth industrial revolution, which involves AI-based factory automation. The ability to promptly detect machine anomalies by analyzing sounds is valuable for monitoring machine conditions. This project aligns with the concept of Artificial Intelligence and the Internet of Things (AIoT), which is the future of manufacturing industries. The project aims to predict if a machine requires maintenance before it fails, ensuring efficient and continuous production, and preventing production halts and significant financial losses.

## Dataset Description

The project uses a dataset available from the [DCASE Challenge 2023](https://dcase.community/challenge2023/task-first-shot-unsupervised-anomalous-sound-detection-for-machine-condition-monitoring). The dataset comprises three sections: the development dataset, additional training dataset, and evaluation dataset. It includes normal and anomalous operating sounds from various machine types, such as fans, gearboxes, bearings, and more.

## Performance Evaluation Metric

The project's performance is evaluated based on the Area Under the Receiver Operating Characteristic (ROC) curve (AUC) and partial AUC (pAUC) with a harmonic mean (hmean) of AUC and pAUC. The formula for calculating the total score (Ω) is provided in the project documentation.

## Recent Base Model Architecture

The recent base model used in the project is the Selective Mahalanobis Autoencoder. The architecture includes an input layer, feature extraction, input vector formation, autoencoder, and the training and testing phases.

### Model Architecture:

- Input Layer: Short-Time Fourier Transform (STFT) is applied to input audio samples with specific parameters.
- Feature Extraction: The STFT output is transformed into 128 bands of Log-mel energies.
- Input Vector Formation: Input vectors for the autoencoder are created by concatenating five consecutive frames of Log-mel energies, resulting in input vectors of 640 dimensions.
- Autoencoder: Comprises an encoder and a decoder. The encoder maps input vectors to a lower-dimensional representation, and the decoder maps the lower-dimensional representation back to the original input space.
- Training: The model parameters are trained to minimize mean square error (MSE) between input normal samples and their reconstructions.
- Testing: Anomaly scores are calculated during the testing phase using the reconstruction error.



