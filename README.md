# M.Tech Dissertation: Change-point Analysis of High-dimensional Data Based on Clustering

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

## 📌 Overview

This repository contains the code, thesis, and presentation slides for my M.Tech dissertation completed at the **Indian Statistical Institute (ISI), Kolkata** under the supervision of **Prof. Anil Kumar Ghosh**.

The research focuses on developing a novel clustering-based algorithm for detecting change-points in high-dimensional data using modified Agglomerative Hierarchical Clustering with **L1 norm Mean Absolute Difference of Distances (MADD)**.

## 🎯 Research Objectives

- Develop an efficient change-point detection algorithm for high-dimensional datasets
- Address limitations of Euclidean distance in high-dimensional settings
- Propose MADD-based L1 dissimilarity measure for robust change-point detection
- Introduce Penalized DUNN Index (PDI) for estimating the number of change-points
- Demonstrate theoretical consistency under HDLSS (High-Dimensional Low Sample Size) scenarios

## 📁 Repository Structure
```
M.Tech-Dissertation/
├── Coding/                    # Implementation code
│   ├── ChangePointDataAnalysisScratch.ipynb
│   └── ChangePointDataAnalysisTraceData.ipynb
├── Slides/                    # Presentation slides
├── Thesis/                    # Dissertation document
└── README.md
```

## 🔬 Methodology

### Problem Statement
Change-point analysis involves examining time-ordered data to identify alterations in underlying distributions. Traditional methods using Euclidean distance fail in high-dimensional settings, especially when distributions differ in scale or higher moments.

### Proposed Approach

1. **Modified Hierarchical Clustering**: Agglomerative clustering with single linkage, modified to merge only consecutive clusters

2. **MADD Dissimilarity**: Mean Absolute Difference of Distance
```
   δ₀(Xᵢ, Xⱼ) = 1/(n-2) Σₖ |‖Xᵢ - Xₖ‖ - ‖Xⱼ - Xₖ‖|
```

3. **L1-norm MADD**: For detecting changes beyond first two moments
```
   δ₁(Xᵢ, Xⱼ) = 1/(n-2) Σₖ |Σₗ|Xᵢ⁽ˡ⁾ - Xₖ⁽ˡ⁾| - Σₗ|Xⱼ⁽ˡ⁾ - Xₖ⁽ˡ⁾||
```

4. **Penalized DUNN Index (PDI)**: For estimating optimal number of clusters
```
   PD(k) = B(k)/W(k) - k·ζ(d)
```

### Key Contributions

- **Theoretical Consistency**: Proved high-dimensional consistency of proposed methods under appropriate regularity conditions
- **Handles Multiple Scenarios**: Works for location, scale, and distributional changes
- **Single Cluster Detection**: PDI overcomes DUNN index limitation in detecting single-cluster scenarios

## 📊 Results

The proposed method was tested on:

| Example | Data Type | DI/PDI Performance |
|---------|-----------|-------------------|
| Location Problem | Different means | 100% accuracy |
| Scale Problem | Different variances | 100% accuracy |
| Distribution Problem | t₄ vs Normal | 90% accuracy |
| Real Data | MIT Reality Mining | Detected winter break transition |

### Comparison with State-of-the-art

Outperformed existing methods including:
- E-divisive method (energy distances)
- Kernel-based methods
- Graph-based methods (MST, NNG, MDP)

## 🛠️ Installation
```bash
# Clone the repository
git clone https://github.com/Banashree06/M.Tech-Dissertation.git

# Navigate to the directory
cd M.Tech-Dissertation

# Install required packages
pip install -r requirements.txt
```

## 📦 Dependencies

- Python 3.8+
- NumPy
- Pandas
- Scikit-learn
- SciPy
- Matplotlib
- Seaborn

## 🚀 Usage
```python
# Open Jupyter Notebook
jupyter notebook

# Navigate to Coding folder and run the notebooks
# 1. ChangePointDataAnalysisScratch.ipynb - Implementation from scratch
# 2. ChangePointDataAnalysisTraceData.ipynb - Analysis on trace data
```

## 📝 Citation

If you find this work useful, please cite:
```bibtex
@mastersthesis{ghosh2023changepoint,
  title={Change-point Analysis of High-dimensional Data Based on Clustering},
  author={Ghosh, Banashree},
  school={Indian Statistical Institute, Kolkata},
  year={2023},
  month={June},
  type={M.Tech Dissertation},
  supervisor={Prof. Anil Kumar Ghosh}
}
```

## 📚 Key References

- Sarkar & Ghosh (2020). "On Perfect Clustering of High Dimension, Low Sample Size Data." IEEE TPAMI.
- Matteson & James (2014). "A Nonparametric Approach for Multiple Change Point Analysis." JASA.
- Chen & Zhang (2014). "Graph-Based Change-Point Detection."

## 👩‍💻 Author

**Banashree Ghosh**
- 🎓 M.Tech in Computer Science (Data Science), ISI Kolkata (2022-2024)
- 📧 Email: banashreeghosh006@gmail.com
- 💼 LinkedIn: [Banashree Ghosh](https://www.linkedin.com/in/banashree-ghosh-627332208)
- 🌐 Portfolio: [banashreeghosh](https://www.banashreeghosh06.com/about)
- 💻 GitHub: [Banashree06](https://github.com/Banashree06)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- **Prof. Anil Kumar Ghosh**, ISI Kolkata, for invaluable guidance and supervision
- Indian Statistical Institute, Kolkata for providing resources and support
- Computer and Communication Sciences Division, ISI Kolkata

---

⭐ If you find this repository helpful, please consider giving it a star!
