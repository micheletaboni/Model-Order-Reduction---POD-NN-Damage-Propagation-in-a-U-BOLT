# Data-Driven-Model-Order-Reduction-with-POD-NN

## Damage Propagation in a U-Bolt

This repository presents a data-driven approach for damage propagation in a U-Bolt, utilizing advanced Model Order Reduction (MOR) techniques. The project's core is the development of a surrogate model based on **Proper Orthogonal Decomposition (POD)**, **Neural Networks (NN)**, **Deep-Learning Reduced Order Model (DL-ROM)** to approximate the propagation of a damage governed by the underlying Partial Differential Equations (PDEs). This methodology effectively bypasses the computational cost of solving high-fidelity Finite Element Method (FEM) simulations, providing a fast and accurate solution for parameter estimation.

## Key Features and Methodologies

- **Dataset Utilization**: The project is built upon a pre-computed dataset of high-fidelity FEM simulations, which serves as the "truth data" to train and validate our reduced-order model. The dataset maps a set of parameters (leakage location and size) to the corresponding full-state pressure field.
- **Data-Driven ROM Implementation**: I implemented a **POD-NN** (Proper Orthogonal Decomposition - Neural Network) framework. This technique leverages POD to find an optimal low-dimensional basis (the POD modes) for the high-dimensional data, followed by a neural network that learns the nonlinear mapping from the model parameters to the POD coefficients.
- **POD-NN Training and Assessment**: The POD-NN model was trained on a subset of simulations. I quantified the model's performance by computing the average relative error in the $L^2$ norm, achieving an accuracy well below the target threshold of 4.7%, demonstrating the surrogate model's predictive power.
- **DL-ROM Training and Assessment**: The DL-ROM model was trained on a subset of simulations. I quantified the model's performance by computing the average relative error in the $L^2$ norm, achieving an accuracy well below the target threshold of 5.6%.
- **Inverse Problem Solving**: The trained ROM is then used to solve a crucial inverse problem: computing the overall damage by changing different parameters in order to prevent future damages.


## Tools and Libraries

- **Python**: The project is implemented in Python, the de facto standard for machine learning and scientific computing.
- **`dlroms` Library**: I used the `dlroms` library, a dedicated tool for implementing data-driven ROMs, which streamlined the development process.
- **Jupyter Notebook**: For interactive development, code execution, and rich visualization of results.

