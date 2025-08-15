# Single-cell Transcriptome Analysis of Colorectal Cancer Post-Chemotherapy

This repository contains a Jupyter Notebook that outlines and reproduces the key steps for single-cell RNA sequencing (scRNA-seq) data analysis in Colorectal Cancer (CRC) patients undergoing chemotherapy. The analysis aims to identify potential mechanisms of chemoresistance by comparing patients with a positive treatment response (responders) to those with disease progression (progressors).

The code was utilized for the analysis presented in the manuscript:
**CANLET-D-25-01949**, "Single-cell Transcriptome Profiling of Post-treatment and Treatment-naïve Colorectal Cancer: Insights into Putative Mechanisms of Chemoresistance."

**Laboratory:** Translational Cancer Genomics Lab, UMR 981, Gustave Roussy.

---

### Structure and Workflow

The `CRC_Celsius_notebook.ipynb` notebook covers the following stages of analysis:

1.  **Data Loading:** Loading a single, pre-processed, and concatenated AnnData object.
2.  **Clinical Data Integration:** Incorporating clinical information such as KRAS mutation status and metastasis location.
3.  **Quality Control and Pre-processing:** Filtering cells and genes based on standard quality metrics.
4.  **Data Integration and Dimensionality Reduction:** Using `scVI` to correct for batch effects and compute a low-dimensional representation.
5.  **Cell Type Annotation:** Classifying cells based on known marker genes.
6.  **Tumor Cell Detection:** Identifying malignant cells based on Copy Number Variations (CNV) using `infercnvpy`.
7.  **Differential Gene Expression (DEG) Analysis:** Comparing gene expression between `responders` and `progressors` within the tumor cell population using downsampling.
8.  **Molecular Pathway (MP) Signatures Analysis (GSEA):** Evaluating the enrichment of pathway signatures in the comparison groups.

---

### Dependencies

To run the notebook, you will need the following Python packages. You can install them using pip:

```bash
pip install anndata hdf5plugin scanpy scvi-tools decoupler infercnvpy wget gseapy
