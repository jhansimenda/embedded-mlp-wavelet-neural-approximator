# Neural Network–Based Function Approximator on STM32

##  Overview
This project implements a **function approximator** using two neural network models:
- **Multilayer Perceptron (MLP)**
- **Wavelet Neural Network (WNN)**

The models are designed, trained, and optimized for deployment on an **STM32 (NUCLEO-F401RE) microcontroller**, demonstrating that **complex neural network–based signal processing can be performed on resource-constrained embedded systems**.

The system focuses on **approximating noisy biomedical signals** (such as ECG/EEG fragments) with high accuracy while maintaining **low power consumption and real-time performance**.

---

##  Objectives
- Implement MLP and WNN–based approximation algorithms
- Optimize neural networks for **embedded execution**
- Compare approximation accuracy and error performance
- Demonstrate real-time feasibility on an STM32 microcontroller

---

##  Key Features
- ✔ Neural network–based function approximation  
- ✔ Noise handling and error estimation  
- ✔ Optimized memory and computation for STM32  
- ✔ MATLAB-based training and visualization  
- ✔ Embedded deployment using STM32CubeIDE  

---

##  Hardware Requirements
- **STM32 NUCLEO-F401RE**
- USB cable for programming and power

---

##  Software Requirements
- **MATLAB** – Wavelet Neural Network modeling & visualization  
- **DEV C++** – Multilayer Perceptron implementation  
- **STM32CubeIDE** – Embedded firmware development  

---

##  Methodology
1. **Data Generation**
   - Generate mathematical functions with added noise
2. **Model Training**
   - Train MLP using backpropagation
   - Train WNN using wavelet-based activation functions
3. **Evaluation**
   - Measure approximation error and deviation
4. **Embedded Deployment**
   - Port trained models to STM32
   - Validate real-time execution

---

##  Results
- WNN demonstrated **better noise handling** for biomedical signals  
- MLP achieved **fast convergence with fewer neurons**
- Approximation error maintained within acceptable limits  
- Successful real-time implementation on STM32 hardware  

---

