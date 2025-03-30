This projects developed for the Scientific Computing Methods exam (Metodi del Calcolo Scientifico) as part of the Master's Degree in Computer Science at the University of Milano-Bicocca (Academic Year 2022-2023). The work consists of two main parts, focusing on the practical application and comparative analysis of numerical methods in different programming environments.

### **Project 1: Analysis of Solvers for Sparse Symmetric Positive Definite Linear Systems**

* **Objective:** To evaluate and compare the performance of solvers for linear systems $Ax=b$, where $A$ is a large, sparse, symmetric, and positive-definite matrix. The analysis aimed to benchmark the proprietary environment MATLAB against the open-source environment Python (using the SciPy library).
* **Methodology:**
    * Utilized matrices from the *SuiteSparse Matrix Collection*.
    * Implemented scripts in MATLAB and Python to solve the linear systems using optimized sparse solvers (e.g., backslash operator `\` in MATLAB, `scipy.sparse.linalg.spsolve` in Python).
    * Measured performance on both Windows and Linux operating systems, analyzing:
        * Execution Time
        * Memory Usage (profiled during solver execution)
        * Accuracy (via relative error compared to a known exact solution).
* **Technologies Used:**
    * MATLAB (Utilizing built-in linear algebra and profiling tools)
    * Python
    * SciPy (for sparse linear algebra)
    * NumPy (for numerical array manipulation)
    * memory-profiler (for detailed memory usage analysis in Python)
    * Pandas (for data handling and exporting results)
    * Matplotlib (for data visualization)
* **Key Findings & Outcomes:**
    * Conducted a detailed comparative performance analysis across platforms. MATLAB demonstrated significantly faster execution times for the larger matrices tested.
    * Python (SciPy) showed better computational performance on Linux compared to Windows for this specific task.
    * Memory usage patterns differed between environments, analyzed in relation to matrix properties and solver behavior.
    * Relative errors were generally very low, confirming solver accuracy, with minor differences observed between configurations.
    * Analyzed the trade-offs between proprietary (MATLAB) and open-source (Python/SciPy) solutions, considering factors like license cost, computation time, and potential hardware scaling requirements for equivalent throughput. Linux emerged as a preferable OS environment.

### **Project 2: Grayscale Image Compression using Discrete Cosine Transform (DCT2)**

* **Objective:** To implement and study a grayscale image compression algorithm based on the 2D Discrete Cosine Transform (DCT2) in an open-source environment. This involved comparing DCT implementations and developing a demonstrative application.
* **Key Goals:**
    1.  Implement a custom DCT2 function and compare its performance against the optimized library implementation (SciPy).
    2.  Develop and analyze a block-based image compression algorithm inspired by JPEG (using DCT2 and frequency thresholding, without a quantization matrix).
    3.  Create a graphical user interface (GUI) allowing users to load a grayscale BMP image, set compression parameters (block size `F`, frequency threshold `D`), and visualize the original vs. compressed image.
* **Methodology:**
    * Compared the execution time of a custom DCT2 (using `numpy.fft`) against `scipy.fftpack.dct`.
    * Implemented the compression algorithm: dividing the image into FxF blocks, applying DCT2, zeroing out high-frequency coefficients where $i+j > D$, and reconstructing blocks using the Inverse DCT2 (IDCT). Handled image edges not perfectly divisible by F.
    * Developed a user-friendly GUI application.
* **Technologies Used:**
    * Python
    * NumPy (for array manipulation and custom DCT)
    * SciPy (for optimized DCT/IDCT functions from `fftpack`)
    * Pillow (PIL fork - for image loading and manipulation)
    * Matplotlib (for image display and performance plotting)
    * Pandas (for logging performance data)
    * PySimpleGUI (for building the GUI)
    * Git (for version control)
* **Key Findings & Outcomes:**
    * Verified the significant performance advantage of using optimized library functions (SciPy) for transforms like DCT compared to the custom implementation.
    * Analyzed the impact of compression parameters (block size F, threshold D) on image quality, finding that smaller blocks and maintaining a D/F ratio above ~0.2 generally yielded better visual results.
    * Successfully developed a functional GUI application demonstrating the image compression pipeline and allowing interactive parameter testing.

---
