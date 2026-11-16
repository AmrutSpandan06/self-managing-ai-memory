# Self-Managing AI Memory
### Learning Continuously with Minimal Storage and Reduced Catastrophic Forgetting

## 📌 Project Overview

This project explores **Continual Learning** in Deep Learning, focusing on one major challenge called **Catastrophic Forgetting**.

Catastrophic forgetting happens when a neural network learns new tasks but loses previously learned knowledge.

This project compares two approaches:

1. **Without Memory:** The model learns tasks sequentially without storing previous training samples.
2. **With Memory:** The model maintains a limited memory buffer of selected samples and reuses them during subsequent learning.

The objective is to reduce forgetting while maintaining reasonable accuracy with limited storage.

## 🎯 Objectives

- Understand catastrophic forgetting in continual learning.
- Compare learning with and without a memory buffer.
- Reduce the loss of previously learned knowledge.
- Maintain accuracy across sequential tasks.
- Minimize memory storage requirements.

## ⚙️ Methodology

The experiment follows a sequential learning approach involving five tasks.

**Approach 1: Without Memory**
- Train the model on Task 1.
- Move to subsequent tasks sequentially.
- Do not retain previous task samples.
- Evaluate how much previously learned knowledge is forgotten.

**Approach 2: With Memory**
- Train the model on sequential tasks.
- Store selected samples in a limited memory buffer.
- Replay stored samples during subsequent learning.
- Evaluate accuracy and forgetting across tasks.

## 📊 Experimental Results

### Average Accuracy

| Metric | Without Memory | With Memory |
|---|---:|---:|
| Final Average Accuracy | 19.77% | 68.23% |

**Accuracy Improvement: 48.46 percentage points**

### Average Forgetting

| Approach | Average Forgetting |
|---|---:|
| Without Memory | 99.47 pp |
| With Memory | 38.96 pp |

### Memory Usage

| Metric | Value |
|---|---:|
| Stored Samples | 500 |
| Maximum Capacity | 500 |
| Approximate Image Storage | 1.5 MB |

## 🛠️ Technologies Used

- Python
- Deep Learning
- Google Colab
- Jupyter Notebook
- Neural Networks
- Continual Learning
- Memory Buffer / Experience Replay

## 📁 Project Structure

```text
self-managing-ai-memory/
│
├── README.md
└── Self_Managing_AI_Memory.ipynb
```

## 🚀 How to Run

1. Open the project notebook.
2. Click **Open in Colab** or download the notebook.
3. Run the notebook cells sequentially.
4. Observe the comparison between the two approaches.
5. Review the final accuracy, forgetting and memory usage results.

## 💡 Key Findings

The experiment demonstrates that retaining and replaying selected previous samples can help reduce catastrophic forgetting in sequential learning.

Compared with learning without memory, the memory-based approach achieved higher average accuracy and lower average forgetting while using a limited memory buffer.

## 🔮 Future Scope

- Develop more efficient memory selection strategies.
- Reduce memory storage requirements further.
- Explore advanced continual learning algorithms.
- Evaluate performance on larger datasets and more tasks.
- Investigate adaptive memory management.

## 👨‍💻 Author

**V Amrut Spandan**

GitHub: [AmrutSpandan06](https://github.com/AmrutSpandan06)

## 📌 Project Status

Academic Deep Learning implementation and experimental comparison.
