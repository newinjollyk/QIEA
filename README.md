## ⚙️ Quantum Inspired Evolutionary Algorithm for Neural Architecture Search 

# Quantum-Inspired Evolutionary Algorithm for Neural Architecture Search (QIEA-NAS)

**QIEA-NAS** is a technique for automating the design of Convolutional Neural Networks (CNNs) using a Quantum-Inspired Evolutionary Algorithm.  
It represents neural architectures as quantum chromosomes and evolves them through observation and rotation-based updates.  
This approach allows for efficient and intelligent exploration of network structures with fewer resources than traditional search strategies.

## ⚙️ How It Works

1. **Initialization**: A population of quantum chromosomes is created, each representing a candidate CNN architecture.  
   Each chromosome is initialized with randomly selected layer types (e.g., convolution, pooling, fully connected, or disabled).  
   The corresponding qubits are set based on these layer types.

2. **Observation**: Each qubit is measured to form a binary string, which is then converted into a dot-decimal representation.

3. **Evaluation**: The CNN architecture is constructed from the dot-decimal value and built as a TensorFlow model.  
   It is then trained for a few epochs to estimate its validation performance.

4. **Selection & Update**: Based on the validation accuracy, the qubits are updated using a rotational gate guided by a reference table.

5. **Iteration**: Steps 2–4 are repeated for a fixed number of iterations. At the end, the best-evolved chromosome for that round is selected.

6. **Population Scan**: The process is repeated for each chromosome in the initial population.

7. **Final Selection**: From all evolved chromosomes in the population, the best one is selected based on its validation accuracy.


## 🧪 Dataset

You can use **any image classification dataset** with this method.

- Modify the `train_cnn_model()` function to specify your dataset path.
- Input shape, class count, and preprocessing steps must match your dataset.

---

## 🧰 Initial Parameters

Initial population size, layer count, learning rate, and other hyperparameters can be configured in the `main()` function inside the notebook.

---

