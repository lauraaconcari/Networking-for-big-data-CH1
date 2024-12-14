# Networking for Big Data: Homework 1

## Course: Master’s in Data Science

### Kleinrock Group:
- Laura Concari (1890490)
- Laura López Sànchez (2125723)
- Giuliana Prinzi (1952137)
- Erika Ioana Zetu (1888659)

**Academic Year**: 2023/2024

---

## Table of Contents

- [Introduction](#introduction)
- [Part 1: Connectivity Analysis](#part-1-connectivity-analysis)
- [Part 2: Network Topology Optimization](#part-2-network-topology-optimization)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Results and Insights](#results-and-insights)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction

This project focuses on understanding the complexities of connectivity in random graph models and optimizing network performance in large-scale distributed systems. The homework is divided into two parts:

1. **Connectivity Analysis**: Explores the computational complexity of various connectivity-checking algorithms and evaluates the probability of connectedness in Erdos-Renyi and r-regular random graphs.
2. **Network Topology Optimization**: Analyzes the mean response time and job running cost in Fat-tree and Jellyfish network topologies, providing insights into optimal configurations for workload distribution.

---

## Part 1: Connectivity Analysis

### Objectives:

- Compare the computational complexity of graph connectivity algorithms:
  - Adjacency matrix irreducibility.
  - Laplacian eigenvalue analysis.
  - Breadth-First Search (BFS).

- Evaluate the probability of connectedness:
  - **Erdos-Renyi random graphs**: Simulate graphs with varying edge probabilities (p).
  - **r-regular random graphs**: Simulate graphs with fixed degrees (r) and varying node counts.

### Key Findings:

1. **Algorithmic Efficiency**:
   - BFS is the most efficient method with \(O(n + m)\) complexity.
   - Adjacency matrix irreducibility is the slowest (\(O(n^3)\)).

2. **Connectivity in Random Graphs**:
   - For Erdos-Renyi graphs, connectivity exceeds 50% at \(p = 0.05\) and is nearly certain at \(p = 0.15\).
   - For r-regular graphs:
     - \(r = 2\): Low connectivity, unsuitable for large networks.
     - \(r = 8\): High connectivity even with 100 nodes.

---

## Part 2: Network Topology Optimization

### Objectives:

- Evaluate **mean response time** and **job running cost** in two topologies:
  - **Fat-tree**: Structured for load balancing.
  - **Jellyfish**: Randomized for flexibility.

- Analyze performance under varying server counts (N).

### Key Findings:

1. **Mean Response Time**:
   - Increases with N but is minimized in Fat-tree topologies due to better load balancing.
   - Peaks at \(N = 1000\) due to increased communication overhead.

2. **Job Running Cost**:
   - Initially decreases with N but rises beyond \(N = 1000\) due to overhead.
   - Optimal value for minimizing cost: \(N = 250\).

### Implications:
- Fat-tree is more efficient for workloads requiring balanced distribution.
- Over-splitting jobs can degrade performance; careful configuration is essential.

---

## Technologies Used

- **Programming Language**: Python (Jupyter Notebook)
- **Libraries**:
  - NetworkX: Graph generation and analysis.
  - NumPy: Mathematical operations.
  - Matplotlib: Visualization.

---

## Setup Instructions

### Prerequisites

1. Install Python (>= 3.8) and Jupyter Notebook.
2. Install required libraries:
   ```bash
   pip install networkx numpy matplotlib
   ```

### Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Kleinrock_HW1.git
   ```
2. Navigate to the project directory:
   ```bash
   cd Kleinrock_HW1
   ```
3. Open the Jupyter Notebook:
   ```bash
   jupyter notebook Kleinrock_Hw1.ipynb
   ```

4. Run the cells sequentially to reproduce the analysis and visualizations.

---

## Results and Insights

- **Algorithm Efficiency**: BFS is the fastest approach for connectivity checks.
- **Network Optimization**:
  - Fat-tree topologies are preferable for balanced workloads.
  - Jellyfish topologies are versatile but less efficient at high workloads.
- **Optimal Configurations**: Use \(N = 250\) servers for minimal job running cost.

---

## Project Structure

```
Kleinrock_HW1/
├── Kleinrock_Hw1.ipynb   # Main notebook
├── Kleinrock_Hw1.pdf     # Project report
├── README.md             # Documentation
└── results/              # Output plots and figures
```

---

## Contributing

Contributions are welcome! Follow these steps:

1. Fork the repository.
2. Create a feature branch:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature description"
   ```
4. Push your changes:
   ```bash
   git push origin feature-name
   ```
5. Submit a pull request for review.

---

## License

This project is licensed under the [MIT License](LICENSE). Use responsibly.
