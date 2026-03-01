PROJECT OVERVIEW


In this project, I explored whether DNA methylation patterns can reveal hidden molecular subtypes within lung adenocarcinoma (LUAD) patients.
Using publicly available methylation data from GEO (Illumina 450K platform), I performed unsupervised machine learning to identify natural patient groupings based purely on epigenetic variation.
The goal was not prediction — but subgroup discovery.

BIOLOGICAL BACKGROUND (My Simple Explanation)


DNA methylation is an epigenetic modification that can regulate gene activity without changing the DNA sequence.
In cancer, abnormal methylation patterns can:
Silence tumor suppressor genes
Activate oncogenic pathways
Reflect different tumor evolution states
Therefore, clustering patients based on methylation profiles may reveal biologically distinct tumor subtypes.



WHAT I DID



1. Data Processing
Loaded genome-wide DNA methylation beta values
Selected only methylation intensity (Avg Beta) values
Transposed matrix so rows = patients, columns = CpG sites
Selected the top 5000 most variable CpG sites
Standardized the data
Final dataset shape:
88 patients × 5000 CpG sites
   

3. Dimensionality Reduction (PCA)
Performed Principal Component Analysis to:
Reduce dimensionality
Visualize patient distribution
The first two principal components explained ~39% of variance.
PCA visualization suggested natural grouping patterns.


3. Determining Optimal Clusters
Used the Elbow Method to determine optimal k.
The bend occurred at k = 3, indicating three potential subgroups.



4. K-means Clustering
Applied K-means clustering with k = 3.
The clusters showed clear separation in PCA space, suggesting:
Distinct methylation-driven tumor subgroups
Epigenetic heterogeneity within LUAD


INTERPRETATION

This analysis suggests that lung adenocarcinoma patients can be stratified into methylation-based molecular subtypes.
These subtypes may reflect:
Different tumor epigenetic states
Distinct biological pathways
Potentially different clinical behavior
Further downstream analysis (clinical correlation, pathway enrichment) would be required to validate biological significance.
