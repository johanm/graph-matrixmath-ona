# The Mathematics of Organizational Network Analysis

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/johanm/graph-matrixmath-ona/blob/main/graphmatrixmath.ipynb)  [![Read Essay](https://img.shields.io/badge/Read-Essay-1a4a7a?style=flat)](https://johanm.github.io/graph-matrixmath-ona/graphmatrixmath.html)

> **Replace `johanm/graph-matrixmath-ona` in the badge link above with your actual GitHub username and repository name before pushing.**

---

## What is this?

This repository contains two companion pieces that develop the mathematical foundations of **Organizational Network Analysis (ONA)**, the discipline of using network science to understand how people actually collaborate, communicate, and share information inside organizations.

ONA is increasingly used by HR, People Analytics, and organizational design teams to answer questions like: Where are the informal leaders? Where are the silos? Who is a single point of failure for organizational resilience? How fast does information actually travel? The mathematics behind these questions is spectral graph theory, and that is what this material covers.

The two files are designed to be read together: the essay builds intuition and explains the *why*, the notebook shows the *how* in working code.

---

## Files

### `graphmatrixmath.html`
A long-form essay covering the full mathematical toolkit for ONA, written for a reader with some quantitative background but no prior knowledge of graph theory or linear algebra. Topics include:

- The adjacency matrix and what it encodes
- The Laplacian matrix (combinatorial, weighted, and normalized variants) and why each entry pattern has the structure it does
- The Fiedler value (λ₂) and algebraic connectivity as a measure of organizational resilience
- Spectral clustering for discovering informal communities
- Spectral graph drawing: using eigenvectors as geometric coordinates, and why a large λ₂ is a proof that no clean visualization of the network exists
- Eigenvector centrality, betweenness, and PageRank
- Directed networks, bipartite networks, hypergraph Laplacians, and multi-layer networks
- Temporal tracking of spectral health over time

Each concept is grounded in an ONA interpretation throughout.

### `graphmatrixmath.ipynb`
An interactive Jupyter notebook that implements every concept from the essay in working Python. Each part of the notebook corresponds to a section of the essay and can be run independently.

**Contents (18 parts):**

| Part | Topic |
|------|-------|
| 0 | Setup & file-size configuration |
| 1 | The adjacency matrix |
| 2 | The Laplacian L = D − A, and all three variants (combinatorial, weighted, normalized) |
| 3 | Laplacian intuition: heat diffusion on a graph |
| 4 | Fiedler value, algebraic connectivity & resilience |
| 4b | Sign ambiguity and eigenvalue degeneracy (interlude) |
| 5 | Spectral clustering: finding informal communities |
| 6 | Spectral graph drawing: eigenvectors as geometry, and the λ₂ ↔ drawability theorem |
| 8 | Directed networks: in/out centrality |
| 9 | Centrality: degree, eigenvector, betweenness, PageRank |
| 10 | Matrix powers: walks, triangles & structural holes |
| 11 | Normalised Laplacian & random walk mixing |
| 12 | Cospectral graphs: limits of spectral fingerprints |
| 13 | Bipartite networks: people connecting through things |
| 14 | Hypergraph Laplacian: group interactions |
| 15 | Multi-layer networks & the supra-Laplacian |
| 16 | Temporal tracking: spectral health dashboard |
| 17 | Data quality: threshold sensitivity |
| 18 | Summary reference table |

---

## Running the notebook

### Option 1: Google Colab (recommended for beginners)

Click the badge at the top of this README, or use this link:

```
https://colab.research.google.com/github/johanm/graph-matrixmath-ona/blob/main/graphmatrixmath.ipynb
```

Colab runs entirely in your browser. No installation required. You will need a Google account. Once the notebook opens, go to **Runtime → Run all** to execute all cells, or run them one at a time with **Shift+Enter**.

The notebook installs no unusual packages; it uses only `numpy`, `scipy`, `matplotlib`, `networkx`, `pandas`, and `scikit-learn`, all of which are pre-installed in Colab.

### Option 2: Local Jupyter

```bash
pip install numpy scipy matplotlib networkx pandas scikit-learn
jupyter notebook graphmatrixmath.ipynb
```

Or with JupyterLab:

```bash
jupyter lab graphmatrixmath.ipynb
```

Python 3.9 or later is recommended.

### Option 3: VS Code

Open the `.ipynb` file directly in VS Code with the Jupyter extension installed. Select a Python kernel with the dependencies above.

---

## A note on notebook file size

Jupyter embeds every plot as a base64-encoded image inside the `.ipynb` JSON file. After running all 18 parts (Parts 0–6 and 8–18, ~30 figures), the notebook will grow significantly. Part 0 explains the DPI setting that controls this. If you want to commit a clean version to git, run **Kernel → Restart & Clear Output** before saving.

---

## Author

Created by **[Johan Myrberger](https://www.linkedin.com/in/myrberger/)**, who explored how matrix algebra and matrix operations relate to graph analysis and organizational network science. The essay and notebook were co-created with the assistance of Claude (Anthropic).

---

## Background and motivation

The mathematical content draws on classical results in spectral and algebraic graph theory, in particular the work of Fiedler (algebraic connectivity), Hall (spectral graph drawing), and Tutte (spring embeddings).

A highly recommended companion resource is Daniel Spielman's lecture **"Miracles of Algebraic Graph Theory"**, an accessible and inspiring overview of spectral graph theory from one of its leading researchers. The lecture covers spectral graph drawing, the Laplacian quadratic form, Tutte's spring embedding theorem, and the connection between the Fiedler value and network drawability, all topics developed further in the essay and notebook here.

[![Miracles of Algebraic Graph Theory, Daniel Spielman](https://img.youtube.com/vi/CDMQR422LGM/0.jpg)](https://www.youtube.com/watch?v=CDMQR422LGM)

The ONA framing (connecting each mathematical object to a concrete organizational question) is Johan's own.

---

## Suggested reading order

1. Read the essay through once for the big picture, skimming the formal definitions.
2. Open the notebook and run Part 0 (setup), then follow along with whichever essay section interests you.
3. The notebook's Part 18 (summary reference table) is a useful cheat sheet once you've been through the material.

For readers new to network analysis entirely, Parts 1–5 of the notebook (adjacency matrix through spectral clustering, including the sign ambiguity interlude at Part 4b) form a self-contained introduction that covers the most practically useful ideas. Part 12 (cospectral graphs) uses a verified pair of non-isomorphic graphs with identical spectra, confirmed computationally.

---

## License

The essay and notebook are released for educational use. If you build on this material, a link back to this repository is appreciated.
