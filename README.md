This repository contains projects developed for the Scientific Computing Methods (Metodi del Calcolo Scientifico) exam as part of the Master's Degree in Computer Science at the University of Milano-Bicocca (Academic Year 2022-2023). The work consists of two main parts, focusing on the practical application and comparative analysis of numerical methods in different programming environments.

## Repository Content

* **Project 1**: Comparative performance analysis of MATLAB and Python/SciPy in solving sparse, symmetric, and positive-definite linear systems.
* **Project 2**: Implementation and analysis of grayscale image compression using the 2D Discrete Cosine Transform (DCT2), including a GUI application.
* **Reports**: Detailed analysis documents (`Relazione_Progetto1.pdf`, `Relazione_Progetto2.pdf` - *Note: These report files are in Italian*) illustrating the methodology, results, and conclusions for each project.

---

## Project 1: Comparative Analysis of Solvers for Sparse Symmetric Positive Definite Linear Systems

### Objective
To evaluate and compare the performance of solvers for linear systems $Ax=b$, where $A$ is a large, sparse, symmetric, and positive-definite matrix. The analysis benchmarked the proprietary environment MATLAB against the open-source environment Python (using the SciPy library).

### Methodology
* Utilized matrices from the **SuiteSparse Matrix Collection**, covering a range of sizes and sparsity patterns.
* Implemented scripts in MATLAB and Python to solve the linear systems using optimized sparse solvers.
* Measured performance on both **Windows** and **Linux** operating systems, analyzing:
    * **Execution Time**: Wall-clock time for the solver execution.
    * **Memory Usage**: Profiled memory consumption during solver execution using MATLAB Profiler and Python's `memory-profiler`.
    * **Accuracy**: Computed the relative error `norm(x - xe) / norm(xe)` compared to a known exact solution `xe = ones(...)`.

### Technologies Used
* **Languages**: MATLAB, Python 3
* **Core Libraries**:
    * MATLAB.
    * Python:
        * **SciPy**: Sparse linear algebra (`sparse.linalg.spsolve`), matrix I/O (`io.loadmat`).
        * **NumPy**: Fundamental numerical array manipulation.
        * **memory-profiler**: Detailed memory usage analysis in Python.
        * **Pandas**: Data handling and exporting results to CSV.
* **Operating Systems**: Windows, Linux (used for comparative testing).

### Key Findings & Outcomes
* **Performance Benchmark**: Conducted a detailed comparative performance analysis, quantifying execution times and memory consumption across platforms and problem sizes. MATLAB demonstrated **significantly faster execution times**, particularly for the largest matrices tested, highlighting the optimization level of its proprietary solver.
* **OS Impact**: Python (SciPy) exhibited **better computational performance** (lower execution times) on **Linux** compared to its execution on Windows for this specific task, suggesting potential advantages of the Linux environment for numerical workloads in Python.
* **Memory Footprint**: Memory usage patterns differed between environments and were analyzed in relation to matrix properties (size, nnz) and solver behavior. Python's `memory-profiler` provided granular insights into peak memory allocation during the `spsolve` execution.
* **Accuracy Validation**: Relative errors were consistently **very low** (e.g., typically below $10^{-12}$), confirming the numerical stability and accuracy of both solvers, with only negligible differences observed between configurations.
* **Cost-Performance Trade-offs**: Provided a quantitative basis for evaluating the trade-offs between proprietary (MATLAB) and open-source (Python/SciPy) solutions. While MATLAB offered superior speed for large problems, the analysis considered factors like license cost versus computation time, indicating that **Python/SciPy on Linux presents a viable, cost-effective alternative**, potentially requiring hardware scaling to match MATLAB's throughput on demanding tasks.

---

## Project 2: Grayscale Image Compression using Discrete Cosine Transform (DCT2)

### Objective
To implement and study a grayscale image compression algorithm based on the 2D Discrete Cosine Transform (DCT2) within an open-source Python environment. This involved comparing DCT implementations and developing a demonstrative GUI application.

### Key Goals
1.  Implement a custom DCT2 function and **quantitatively compare its performance** against the highly optimized library implementation (`scipy.fftpack.dct`).
2.  Develop and analyze a **block-based image compression algorithm** inspired by JPEG (using DCT2 and frequency thresholding via parameter `D`, without a separate quantization matrix).
3.  Create a **graphical user interface (GUI)** allowing users to load a grayscale BMP image, interactively set compression parameters (block size `F`, frequency threshold `D`), and visually compare the original vs. compressed image side-by-side.

### Methodology
* Benchmarked the execution time of a **custom DCT2** (built upon `numpy.fft.rfft`) against `scipy.fftpack.dct` for various matrix sizes.
* Implemented the compression algorithm: dividing the image into non-overlapping `F x F` blocks, applying DCT2 (`scipy.fftpack.dct`), **zeroing out high-frequency coefficients** where the sum of indices $i+j > D$, and reconstructing blocks using the Inverse DCT2 (`scipy.fftpack.idct`). Handled image dimensions not perfectly divisible by `F`. Pixel values were clamped to [0, 255] post-reconstruction.
* Developed a user-friendly GUI application using `PySimpleGUI` for parameter input, image loading (BMP, grayscale validated), triggering compression, and displaying results using `matplotlib` integration.

### Technologies Used
* **Language**: Python 
* **Core Libraries**:
    * **NumPy**: Array manipulation, custom DCT implementation base.
    * **SciPy**: Optimized DCT/IDCT functions (`fftpack.dct`, `fftpack.idct`).
    * **Pillow** (PIL fork): Image loading (`Image.open`) and manipulation.
    * **Matplotlib**: Image display and performance plotting.
    * **Pandas**: Logging performance data (Part 1).
    * **PySimpleGUI**: Building the interactive GUI.

### Key Findings & Outcomes
* **Library Optimization**: Quantitatively verified the **substantial performance advantage** (often orders of magnitude faster) of using optimized library functions (`scipy.fftpack.dct`) for computationally intensive transforms compared to a custom NumPy-based implementation, reinforcing the importance of leveraging optimized libraries in scientific computing.
* **Compression Parameter Impact**: Systematically analyzed the impact of compression parameters (block size `F`, threshold `D`) on resulting image quality (visual assessment) and implied compression ratio. Found that smaller block sizes (`F=8` or `F=16`) and maintaining a **relative threshold `D/(2F-2)` above a certain level** (e.g., ~0.2, keeping more low-frequency components) generally yielded a better balance between compression and visual fidelity for the tested images.
* **Functional Demonstrator**: Successfully developed a **functional and interactive GUI application** that effectively demonstrates the core principles of DCT-based image compression, allowing for **intuitive exploration of parameter effects** on image reconstruction.
