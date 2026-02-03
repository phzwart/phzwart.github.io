---
layout: archive
title: "Software"
permalink: /software/
author_profile: true
---

## Research Software

### ssbc
**PAC-Conformal Prediction with Small Sample Guarantees**

Python package implementing Small Sample Beta Correction for conformal prediction. Provides tight PAC coverage guarantees even in small-sample regimes, enabling accountable automation for scientific applications.

**Features:**
- Distribution-free, finite-sample guarantees
- Operational rate estimation
- Applications in toxicity screening, molecular property prediction, structural biology
- Integration with scikit-learn pipelines

[GitHub Repository](https://github.com/phzwart/ssbc)

---

### dlsia
**Deep Learning for Scientific Image Analysis**

Comprehensive ML toolkit for scientific imaging applications including segmentation, anomaly detection, and tensor processing across multiple modalities.

**Applications:**
- Tomography reconstruction and analysis
- Lattice light sheet microscopy
- Electron microscopy
- X-ray scattering data analysis

**Key capabilities:**
- CNN-based segmentation
- Anomaly detection algorithms
- Multi-modal image processing
- Integration with experimental workflows

[GitHub Repository](https://github.com/phzwart/dlsia)

---

### qlty
**Out-of-Core Tensor Management**

Framework for efficient ML training and inference on memory-constrained hardware. Enables processing of large-scale imaging datasets that exceed available RAM.

**Features:**
- Intelligent chunking and caching strategies
- PyTorch integration
- Memory-efficient data loading
- Support for distributed computing

[GitHub Repository](https://github.com/phzwart/qlty)

---

## Major Infrastructure Contributions

### PHENIX
**Macromolecular Structure Determination Suite**

Core developer and contributor to PHENIX, a comprehensive system for automated determination of macromolecular structures using X-ray crystallography and other methods.

**My contributions:**
- Xtriage: Quality control and pathology detection
- Twinning detection algorithms
- Integration of computational crystallography methods
- Automation workflows

**Impact:** Used by thousands of structural biologists worldwide; cited >10,000 times

[PHENIX Website](https://phenix-online.org/)  
[Adams et al. (2010) Acta Cryst. D](https://doi.org/10.1107/S0907444909052925)

---

### CCTBX
**Computational Crystallography Toolbox**

Foundational crystallographic infrastructure providing core algorithms and data structures for crystallographic computing.

**Contributions:**
- Data pathology detection algorithms
- Statistical analysis tools
- Integration with experimental beamline systems
- Python bindings and user interfaces

**Impact:** Forms the computational backbone for PHENIX and numerous other crystallographic software packages

[GitHub Repository](https://github.com/cctbx/cctbx_project)

---

### Xtriage
**Crystallographic Data Quality Control**

Automated quality control system for crystallographic data, detecting common pathologies and data collection problems.

**Features:**
- Twinning detection
- Ice ring identification
- Wilson plot analysis
- Anomalous signal detection
- Automated reporting

**Adoption:** Integrated into the Protein Data Bank validation pipeline, checking all deposited structures worldwide

---

## Domain-Specific Tools

### SAXS Analysis Pipeline
**Small-Angle X-ray Scattering**

Developed automated analysis pipeline achieving 10× speedup for SAXS data processing at the Advanced Light Source.

**Capabilities:**
- Automated data reduction
- Buffer subtraction
- Guinier analysis
- Distance distribution functions
- Integration with experimental control systems

---

### FEL Workflows
**Free-Electron Laser Data Processing**

Exascale computational workflows for serial femtosecond crystallography and other FEL techniques.

**Features:**
- Real-time data processing
- Hit finding and indexing
- Structure factor extraction
- Scalable to exascale systems
- Integration with NERSC infrastructure

---

## Development Practices

All research software follows:
- Version control with Git
- Continuous integration testing
- Comprehensive documentation
- Open-source licensing (typically BSD-3-Clause or MIT)
- Active community engagement

## Collaborative Development

I actively collaborate on software development with:
- DOE facility computational staff
- Academic research groups
- Open-source community contributors
- Industry partners

---

## Technical Stack

**Languages:** Python, C++  
**ML Frameworks:** PyTorch, NumPy, SciPy, scikit-learn, scikit-image  
**Computing:** HPC/Exascale systems, CUDA, distributed computing  
**Tools:** Git, GitHub, CI/CD, Docker, Jupyter  
**Domains:** Scientific imaging, structural biology, FEL science, spectroscopy

---

*For publications describing these tools and methods, see the [Publications](/publications/) page.*
