self-managing-ai-memory/
│
├── README.md
├── Self_Managing_AI_Memory.ipynb
└── requirements.txt

## 1. Project Overview

This project demonstrates **Continual Learning** using Deep Learning and explores the problem of Catastrophic Forgetting.

Catastrophic Forgetting occurs when a neural network learns new tasks but loses previously acquired knowledge.

This project implements and compares two approaches:

- **Without Memory:** The model learns tasks sequentially without retaining previous training samples.
- **With Memory:** The model uses a limited memory buffer to store and replay selected samples from previous tasks.

The main objective is to reduce catastrophic forgetting while maintaining accuracy with limited memory storage.

## 2. Objectives

- Understand catastrophic forgetting in neural networks.
- Implement sequential learning across multiple tasks.
- Compare learning with and without memory.
- Implement a class-wise experience replay memory.
- Evaluate accuracy and forgetting.
- Maintain a limited memory capacity.

## 3. Dataset

**MNIST Handwritten Digit Dataset**

- Training images: 60,000
- Testing images: 10,000
- Image dimensions: 28 × 28 pixels
- Classes: Digits 0–9
- Image type: Grayscale

### Task Division

| Task | Digit Classes |
|---|---|
| Task 1 | 0, 1 |
| Task 2 | 2, 3 |
| Task 3 | 4, 5 |
| Task 4 | 6, 7 |
| Task 5 | 8, 9 |

The model learns these five tasks sequentially.

## 4. Model Architecture

This project uses an **Artificial Neural Network (ANN)** implemented using PyTorch.

| Layer | Configuration |
|---|---|
| Input | 784 features |
| Hidden Layer 1 | 128 neurons + ReLU |
| Hidden Layer 2 | 64 neurons + ReLU |
| Output Layer | 10 neurons |

The 28 × 28 images are flattened into 784 input features.

### Training Configuration

- Optimizer: Adam
- Learning Rate: 0.001
- Loss Function: Cross Entropy Loss
- Epochs: 3 per task
- Batch Size: 64

## 5. Methodology

### Approach 1: Without Memory

1. Initialize an ANN model.
2. Train on Task 1.
3. Sequentially train on Tasks 2–5.
4. Do not retain previous task samples.
5. Evaluate performance on previously learned tasks.

### Approach 2: With Memory

1. Initialize another ANN model.
2. Train on the first task.
3. Store selected training samples in a memory buffer.
4. Combine stored samples with new task data.
5. Train the model using both old and new samples.
6. Update the memory buffer after each task.
7. Evaluate performance across all learned tasks.

### Memory Management

The implementation uses a class-wise memory buffer.

- Maximum samples per digit class: 50
- Total digit classes: 10
- Maximum memory capacity: 500 samples
- Selection method: Random sampling

This approach is based on **Experience Replay**.

## 6. Experimental Results

### Final Average Accuracy

| Approach | Accuracy |
|---|---:|
| Without Memory | 19.72% |
| With Memory | 71.77% |

**Accuracy Improvement: 52.05 percentage points**

### Average Forgetting

| Approach | Forgetting |
|---|---:|
| Without Memory | 99.40 percentage points |
| With Memory | 34.37 percentage points |

### Memory Usage

| Metric | Value |
|---|---:|
| Stored Samples | 500 |
| Maximum Capacity | 500 |
| Approximate Image Storage | 1.5 MB |

## 7. Key Findings

- Sequential learning without memory resulted in severe forgetting.
- Experience Replay helped preserve previously learned knowledge.
- The memory-based model achieved higher average accuracy.
- A limited memory buffer reduced forgetting compared with the baseline approach.

## 8. Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Google Colab
- MNIST Dataset

## 9. Project Structure

```text
self-managing-ai-memory/
│
├── README.md
└── Self_Managing_AI_Memory.ipynb
```

## 10. How to Run

1. Open the Jupyter Notebook.
2. Open it in Google Colab.
3. Run the notebook cells sequentially.
4. Observe the accuracy comparison.
5. Review the forgetting and memory usage results.

## 11. Limitations

- The experiment uses the MNIST dataset.
- The memory buffer uses random sample selection.
- The model is evaluated on five sequential tasks.
- Results may vary between executions because random seeds are not fixed.
- The two models are independently initialized.

## 12. Future Scope

- Explore intelligent memory selection techniques.
- Investigate adaptive memory management.
- Reduce storage requirements further.
- Experiment with larger datasets.
- Explore advanced continual learning algorithms.

## 13. Author

**V Amrut Spandan**

GitHub: https://github.com/AmrutSpandan06

---

**Project Type:** Deep Learning | Continual Learning | Academic Implementation
