
**code repo for the manuscript:** 


_A soil fungus confers plant resistance against a phytophagous insect by disrupting the symbiotic role of its gut microbiota_


![alt text](https://www.koppert.it/content/_processed_/1/7/csm_Trichoderma_2_ff9dab76c1.jpg)


This repository contains the code and intermediate files used to study how a soil fungus can modulate of plant–insect interaction. 


Experiment reads have been deposited under the NCBI BioProject [**PRJNA784009**](https://www.ncbi.nlm.nih.gov/bioproject/PRJNA784009).


The manuscript is available [here](https://doi.org/10.1073/pnas.2216922120).


The intermediate files are available on [FigShare](https://figshare.com/s/b6db24859a65c391e629?file=35157163).

The [code_repo.md]() is a markdown file that includes all the bioinformatics steps and is structured in 8 main sections:

1. Survival analysis
2. Digestive enzyme assays
3. Midgut Gene Differential Expression Analyses
4. Midgut DE genes GO enrichment
5. Targeted Metagenome Taxonomy Analyses
6. Targeted Metatgenome Diversity Analyses
7. Midgut Metatranscriptome Analyses
8. Metabolomics Analyses

Each subsection is then subdivided in:

- Section name - SOFTWARE: all relevant software used in the section
- Section name - INPUTS AND INTERMEDIATE FILES: raw inputs and intermediate files to carry out specific sections of analyses 
- Section name - OUTPUTS: the final outputs as identified in the manuscript (Figures and Tables)
- Section name - CODE: multiple code (or commands) blocks

All commands have to be executed from the main folder.

Here is the list of all softwares and tools used in the manuscript; the details on their usage are reported in the code_repo.md file.

- Prism (GraphPad Software Inc. version 6.0b, CA, US);
- FastQC (ref. 46 of the manuscript);
- STAR v2.7.5 (ref. 48 of the manuscript);
- FeatureCounts v2.0.1 (ref. 49 of the manuscript);
- Deseq2 (ref. 50 of the manuscript);
- PANNZER2 (ref. 51 of the manuscript);
- TopGO package in Bioconductor (ref. 52 of the manuscript);
- REVIGO (ref. 53 of the manuscript);
- DADA2 pipeline (ref. 56 of the manuscript);
- q2-clawback plugin(ref. 60 of the manuscript);
- QIIME2 platform (ref. 61 of the manuscript); 
- iNEXT (ref. 68 of the manuscript);
- HUMAnN 2.0 https://huttenhower.sph.harvard.edu/humann2/
- ggplot2 (ref. 70 of the manuscript);
- MaAsLin 2 https://huttenhower.sph.harvard.edu/maaslin/
- MSConvertGUI (ProteoWizard) https://proteowizard.sourceforge.io/tools.shtml
- XCMS Online https://xcmsonline.scripps.edu/landing_page.php?pgcontent=mainPage
- R software (https://www.r-project.org/)
- Geneious 10.2
