# Quantum-Inspired Evolutionary Algorithm for Neural Architecture Search (QIEA-NAS)

**QIEA-NAS** is a technique for automating the design of Convolutional Neural Networks (CNNs) using a Quantum-Inspired Evolutionary Algorithm.  
It represents neural architectures as quantum chromosomes and evolves them through observation and rotation-based updates.  
This approach allows for efficient and intelligent exploration of network structures with fewer resources than traditional search strategies.

##  How It Works

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


##  Dataset

You can use **any image classification dataset** with this method.

- Modify the `train_cnn_model()` function to specify your dataset path.
- Input shape, class count, and preprocessing steps must match your dataset.

---

##  Initial Parameters


Before running the program, you can initialize and customize the following parameters in the `main()` function:

- `population_size` — Number of chromosomes in the population.
- `training_itration` — Number of training and rotation iterations per chromosome.
- `epochs_per_training` — Number of epochs for training each CNN model.
- `batch_size` — Batch size used during CNN training.
- `learning_rate` — Learning rate for the optimizer.
- `max_layers` — Maximum number of convolutional layers allowed per architecture.
- `max_fc_layers` — Maximum number of fully connected layers allowed.
- `num_classes` — Number of output classes (adjust based on your dataset).
- `additional_epochs` — Optional extra epochs for retraining final architectures.
- `train_cnn_threshold` — Accuracy drop threshold for early stopping within a CNN.
- `start_epoch_fraction` — Fraction of total epochs after which to apply early stopping.
- `stop_itration_threshold` — Maximum number of iterations without accuracy improvement before stopping.

These parameters allow you to control the structure, training strategy, and early stopping behavior of the search process.

---

