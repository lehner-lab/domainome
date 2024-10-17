Welcome to the GitHub repository for the following publication: Site-saturation mutagenesis of 500 human protein domains reveals the contribution of protein destabilization to genetic disease (Beltran A et al, 2024).

Here you'll find source code for computational analyses and to reproduce the figures in the paper.

# Table Of Contents

* **1. [Required Software](#required-software)**
* **2. [Required Data](#required-data)**
* **3. [Installation Instructions](#installation-instructions)**
* **4. [Usage](#usage)**

# Required Software

To run the pipeline you will need the following software and associated packages:

* **[_R_](https://www.r-project.org/)** (GGally, bigsnpr, bio3d, data.table, dplyr, drc, factoextra, ggplot2, ggpubr, ggrepel, minpack.lm, mltools, msir, OneR, PRROC, pROC, reshape2, scales, stringr, viridis)



# Required Data

The read counts (DiMSum output), fitness scores, MoCHI weights, and required miscellaneous files should be downloaded from **[here](https://zenodo.org/records/11493742)** and copied to an 'analysis_files' folder in your project directory (named 'base_dir'). An 'output_files' directory in which results files will be written should be created in 'base_dir'.

# Installation Instructions

Make sure you have git and conda installed and then run (expected install time <10min):

```
# Install dependencies (preferably in a fresh conda environment)
conda install -c conda-forge r-ggally r-bigsnpr r-bio3d r-data.table r-dplyr r-drc r-factoextra r-ggplot2 r-ggpubr r-ggrepel r-minpack.lm r-mltools r-msir r-oner r-prroc r-scales r-stringr r-viridis r-proc r-msir r-reshape2
```

The R session info including package and dependency versions can be found in R_session_info.txt.


# Usage

The R Markdown files contain the code to reproduce the figures and results from the computational analyses described in the following publication: Site-saturation mutagenesis of 500 human protein domains reveals the contribution of protein destabilization to genetic disease (Beltran A et al, 2024). See [Required Data](#required-data) for instructions on how to obtain all required data and miscellaneous files before running the analysis (total run time < 2h).

R Markdown files are meant to be run in the following order:

* **1. 00_merge_fitness_tables.Rmd**
* **2. 00_totalnumbers_human_proteome.Rmd**
* **3. 01_QC_reproducibility_bydomain.Rmd**
* **4. 02_validation.Rmd**
* **5. 03_foldseek_distances_network.Rmd**
* **6. 04_predictor_comparisons.Rmd**
* **7. 05_clinical_variants_uniprot.Rmd**
* **8. 06_clinical_variants_clinvar.Rmd**
* **9. 07_clinical_variants_classification.Rmd**
* **10. 08_wmean_fitness_on_structures.Rmd**
* **11. 09_esm1v_residuals.Rmd**
* **12. 10_esm1v_residuals_analysis.Rmd**
* **13. 11_prepare_data_for_homolog_mochi.Rmd**
* **14. 12_evaluate_mochi_models.Rmd**
* **15. 13_left_out_domains.Rmd**
* **16. 14_epistaticmutations_epistaticsites.Rmd**
* **17. 15_clinical_variants_clinvar_mochi.Rmd**
* **18. 16_clinical_variants_uniprot_mochi.Rmd**
* **19. 17_gnomad_v4_variants_mochi.Rmd**
* **20. 18_clinical_variants_merged_mochi.Rmd**
* **21. 19_total_expansion_counts.Rmd**
* **22. 20_homolog_model_weight_correlations.Rmd**
* **23. 21_minimum_distance_pairs.Rmd**
* **24. 22_mochi_homologmodels_evaluation.Rmd**

# Additional scripts and software

If you wish to regenerate all the fitness scores and inferred homolog-averaged energies from the raw sequencing data, the following software packages are required:

* **[DiMSum](https://github.com/lehner-lab/DiMSum) v1.2.9** (pipeline for pre-processing deep mutational scanning data i.e. FASTQ to fitness). Download the FastQ files from Gene Expression Omnibus (GEO) with accession number GSE265942. Shell scripts and configuration files  to run Dimsum can be found in the Zenodo repository.

The following software package is required to fit thermodynamic models to the fitness data (DiMSum output):

* **[MoCHI](https://github.com/lehner-lab/MoCHI)** (pipeline to fit thermodynamic models to fitness data i.e. fitness to energies). Shell scripts and configuration files to use MoCHI to fit energy models to protein families can be found in the Zenodo repository. 


