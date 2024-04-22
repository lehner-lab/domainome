Welcome to the GitHub repository for the following publication: Site-saturation mutagenesis of 500 human protein domains reveals the contribution of protein destabilization to genetic disease (Beltran A et al, 2024).

Here you'll find source code for computational analyses and to reproduce the figures in the paper.

# Table Of Contents

* **1. [Required Software](#required-software)**
* **2. [Required Data](#required-data)**
* **3. [Installation Instructions](#installation-instructions)**
* **4. [Usage](#usage)**

# Required Software

To run the pipeline you will need the following software and associated packages:

* **[_R_](https://www.r-project.org/)** (GGally, bigsnpr, bio3d, data.table, dplyr, drc, factoextra, ggplot2, ggpubr, ggrepel, gplots, minpack.lm, mltools, msir, OneR, PRROC, scales, stringr, viridis)



# Required Data

The read counts (DiMSum output), fitness scores, MoCHI weights, and required miscellaneous files should be downloaded from **[here](https://zenodo.org/records/10491695)** and copied to an 'analysis_files' folder in your project directory (named 'base_dir'). An 'output_files' directory in which results files will be written should be created in 'base_dir'.

# Installation Instructions

Make sure you have git and conda installed and then run (expected install time <10min):

```
# Install dependencies (preferably in a fresh conda environment)
conda install -c conda-forge r-ggally r-bigsnpr r-bio3d r-data.table r-dplyr r-drc r-factoextra r-ggplot2 r-ggpubr r-ggrepel r-gplots r-minpack.lm r-mltools r-msir r-oner r-prroc r-scales r-stringr r-viridis
```

# Usage

The R Markdown files contain the code to reproduce the figures and results from the computational analyses described in the following publication: Site-saturation mutagenesis of 500 human protein domains reveals the contribution of protein destabilization to genetic disease (Beltran A et al, 2024). See [Required Data](#required-data) for instructions on how to obtain all required data and miscellaneous files before running the analysis.

R Markdown files are meant to be run in the following order:

* **1. 00_merge_fitness_tables.Rmd**
* **2. 01_QC_reproducibility_bydomain.Rmd**
* **3. 02_validation.Rmd**
* **4. 03_foldseek_distances_network.Rmd**
* **5. 04_predictor_comparisons.Rmd**
* **6. 05_clinical_variants_uniprot.Rmd**
* **7. 06_clinical_variants_clinvar.Rmd**
* **8. 07_clinical_variants_classification.Rmd**
* **9. 08_wmean_fitness_on_structures.Rmd**
* **10. 09_esm1v_residuals.Rmd**
* **11. 10_esm1v_residuals_analysis.Rmd**
* **12. 11_prepare_data_for_homolog_mochi.Rmd**
* **13. 12_evaluate_mochi_models.Rmd**
* **14. 13_left_out_domains.Rmd**
* **15. 14_epistaticmutations_epistaticsites.Rmd**
* **16. 15_clinical_variants_clinvar_mochi.Rmd**
* **17. 16_clinical_variants_uniprot_mochi.Rmd**
* **18. 17_gnomad_v4_variants_mochi.Rmd**
* **19. 18_clinical_variants_merged_mochi.Rmd**
* **20. 19_total_expansion_counts.Rmd**

# Additional scripts and software

If you wish to regenerate all the fitness scores and inferred homolog-averaged energies from the raw sequencing data, the following software packages are required:

* **[DiMSum](https://github.com/lehner-lab/DiMSum) v1.2.9** (pipeline for pre-processing deep mutational scanning data i.e. FASTQ to fitness). Download the FastQ files from Gene Expression Omnibus (GEO) with accession number GSE247740:link to your base directory (base_dir). Shell scripts to run Dimsum and configuration files can be found in the 'DiMSum' folder in [Required Data](#required-data).

The following software package is required to fit thermodynamic models to the fitness data (DiMSum output):

* **[MoCHI](https://github.com/lehner-lab/MoCHI)** (pipeline to fit thermodynamic models to fitness data i.e. fitness to energies). In order to fit all 5 blocks of Src together, DiMSum fitness tables need to be modified to extend the sequence of each block to the full length Src sequence, and the sign of the kinase activity fitness assay needs to be changed due to the inverse relationship between fitness and activity in the activity assay. DiMSum output tables, the code to modify them, the modified tables ready for MoCHI fitting, and shell scripts to execute MoCHI can be found in the 'MoCHI' folder in [Required Data](#required-data). 


