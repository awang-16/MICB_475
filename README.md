# MICB475 Project 2 Lab notebook
This repository contains ongoing notes on project 2, compiled by AW, IP, SD, SKA, and TW. The project aims to elucidate the combined impacts of diet Westernisation (low fibre consumption and high blood LDL levels) and smoking on gut microbial metabolism.

The file MICB475_R_code.Rmd should be run to reproduce all figures seen in the manuscript. It loads data produced by QIIME2 and PICRUSt2 processing, the bash scripts for which are also displayed here.

### R code outline

**Alpha diversity** (line 54-173): performs alpha-diversity analyses (Observed, Shannon, Chao1, ACE, Simpson, InvSimpson, and Fisher) on the data as categorised both by smoking and LDL status, and by smoking and fiber status. Produces box plots and statistical test results (One-Way ANOVA).

**Beta diversity** (line 175-250): performs beta-diversity analyses (weighted and unweighted unifrac, Bray-Curtis, and Jaccard) using the phyloseq package on the data as categorised above. Produces PCoA plots and performs statistical tests (PERMANOVA).

**DESeq2 analysis** (line 251-346): uses DESEq2 package to perform differential abundance analysis, producing volcano and bar plots to show differentially abundant ASVs labelled at the genera level.

**PICRUSt2 analysis** (line 348-495): uses ggpicrust2 package to analyse pathway patterns and changes in microbiota function, producing bar plots annotated with function.

### Project Aims

1. Identify changes in microbiome composition (a/ß diversity) in smokers vs. nonsmokers, and by diet categories

   1.1. bin data based on fiber and cholesterol levels (H/L)

   *Figure outputs: All alpha-diversity metrics (Shannons, Faith's PD) in boxplots by non/smoking and fiber/LDL categories. All beta-diversity metrics (unweighted, weighted unifrac, Bray-Curtis) in PCA plots with PERMANOVA analysis*
   
2. Analyse changes in metabolic function between smokers and non-smokers, using picrust.

   2.1. Install picrust, process data to remove all features in table.qza file that are mitochondria/chloroplasts and also <5 (increase efficiency) through QIIME

   *Figure outputs: Pathway tables, enzyme tables. Produce table of top 10 upregulated pathways, and top 10 downregulated. Produce heatmap & volcano  to visualise.*

3. Within the smoking population, how how does fibre intake affect metabolic gut function?

   Split into four groups (nonsmoker high-fibre, nonsmoker low-fibre, smoker high-fibre, smoker low-fibre), generate plot showing which pathways are up/downregulated. Control is low-fibre group.

   *Figure outputs: same as A2*

4. Within the smoking population, how how does LDL intake affect metabolic gut function?

   _Same as A3._


### Papers referenced

[Gut microbiota is associated with obesity and cardiometabolic disease in a population in the midst of Westernization](https://www.nature.com/articles/s41598-018-29687-x) Scientific Reports, Sept 2018.

* Original dataset compiled by de la Cuesta-Zuluaga et al of Columbian adults' fecal microbiomes.

[Exploring  non-WEIRD  populations  gut  microbiota:  the relative  importance  of  obesity  metrics  on  gut  microbiome diversity and composition in Colombian adults](https://ojs.library.ubc.ca/index.php/UJEMI/article/view/198186/192791?fbclid=IwAR0iTZopMvDnj4u4ff_Y713ByjeSGnvi86pGAkuLxliEXvQDzXDXm4_k-OA) UJEMI+ Volume 9, Sept. 2021. 

* Significance analysis of all metadata categories on alpha- and beta-diversity metrics; high-significance factors include city, sex, medication, fibre intake etc.

[Individuals with abnormal cardiometabolic statuses are more vulnerable  to  smoking-induced  alterations  of  the  gut microbiome  in  a Colombian  population  undergoing Westernization](https://ojs.library.ubc.ca/index.php/UJEMI/article/view/198169/192803) UJEMI+ Volume 9, Sept. 2021

* Investigates relationship between cardiometabolic status and smoking on gut microbiome, has supplementary figure indicating involvement of a confounding variable causing differences in population unrelated to smoking status.

