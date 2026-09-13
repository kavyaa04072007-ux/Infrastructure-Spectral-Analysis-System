# InfraSpec — Infrastructure Spectral Analysis

An interactive infrastructure network analysis system that applies **graph theory, matrix methods, eigenvalues, eigenvectors, and spectral analysis** to evaluate network robustness and identify vulnerable components.

## Why This Project?

Infrastructure networks such as computer networks, communication systems, power grids, and transportation networks can contain **critical nodes and weak connections** whose failure may disrupt the entire system.

This project was developed as part of **MFC (Mathematical Foundations for Computing)** to connect mathematical concepts with a practical problem.

Instead of using matrices and eigenvalues only for theoretical calculations, the system uses them to answer questions such as:

- How well connected is the network?
- Which nodes are most important?
- Which nodes are potential single points of failure?
- Are there weakly connected regions?
- How can the network be made more resilient?

---

## Key Features

### Interactive Network Builder
- Add, delete, select, and connect nodes interactively
- Create weighted edges
- Move and modify network components
- Predefined **Ring, Hub-Spoke, and Mesh** topologies
- Import and export networks using JSON

### Spectral Analysis
The system constructs:

- Weighted Adjacency Matrix **A**
- Degree Matrix **D**
- Graph Laplacian **L = D − A**

It then performs eigendecomposition to calculate:

- **Fiedler Value (λ₂)**
- **Fiedler Vector**
- **Maximum Eigenvalue (λmax)**
- **Spectral Gap**

The Fiedler value is used as a measure of **algebraic connectivity**, helping identify whether a network is strongly connected or close to becoming disconnected.

### Node Importance & Risk Analysis

The system calculates:

- Spectral Centrality
- Betweenness Centrality
- Weighted Degree
- Articulation Points
- Composite Node Risk

The composite risk score is calculated as:

```text
Risk(v) =
0.35 × Spectral Centrality
+ 0.35 × Betweenness
+ 0.15 × Normalized Degree
+ 0.15 × Articulation Point
