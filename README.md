\# ICD311 Lab: Competency-Based Deep Learning Neural Networks



\## Overview

This project contains the implementation for the ICD311 Neural Networks lab. It covers building and training MLPs for XOR, Fashion-MNIST, and custom image inference, along with debugging and activation experiments.



\## Environment Setup

This project uses a Python virtual environment. Follow these steps to set it up:



1\. Create a virtual environment (Windows):

&#x20;  ```bat

&#x20;  py -m venv .venv



2\. Activate the virtual environment:

&#x09;.venv\\Scripts\\activate



3\. Confirm python version:

&#x09;python --version



4\. Install required dependencies:

&#x09;pip install -r requirements.txt



Project Structure



· notebooks/ : Jupyter notebooks containing code, explanations, and outputs.

· src/ : Python scripts (if any).

· reports/ : Generated loss curves and error analysis tables.

· requirements.txt : Exact package versions for reproducibility.



How to Run



1\. Activate the virtual environment (see above).

2\. Launch Jupyter Lab:

&#x20;  ```bat

&#x20;  jupyter notebook

&#x20;  ```

3\. Open the notebooks in the notebooks/ directory and run the cells in order:

&#x20;  · 01\_setup\_and\_neuron.ipynb

&#x20;  · 02\_xor.ipynb

&#x20;  · 03\_fashion\_mnist.ipynb

&#x20;  · (Add any other notebooks you have)



Reproducibility



· Random seed used: 42

· Device: CPU (CUDA is not available in this environment)



\## Reflection



The first thing that failed was the shape mismatch during the debugging challenge. I deliberately set a linear layer to `nn.Linear(3, 1)` instead of `8, 1`. The evidence that helped me fix it was reading the traceback: `mat1 and mat2 shapes cannot be multiplied (4x8 and 3x1)`. By reasoning about the dimensions, I realized the hidden layer output 8 features, so the next layer needed to accept 8 inputs.



If I were to test next, I would replace the MLP with a Convolutional Neural Network (CNN). My real-world inference test showed that the MLP predicted "Sandal" for every custom image because it lacks spatial awareness and cannot handle domain shifts (different backgrounds, lighting). A CNN would preserve the spatial structure of the image and be much more robust for real-world classification.

