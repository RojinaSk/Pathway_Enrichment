# Pathway_Enrichment_Analysis
Clustering and classification of RNAseq gene expression profiles and functional enrichment analysis
## The tasks of this project are :
1) Functional enrichment analysis of differentially expressed genes and
2) Application of clustering and classification of gene expression profiles.

## Data  
The files can be downloaded from Data folder.

### Data1.xxx contains:

1) Gene_Name: the gene names of RNAseq data sorted in ascending order of t-test p-values

2) P_value: the p-values of aforementioned genes

3) SeqData: 20,131 gene expressions of 276 samples. The gene dimension is matched with Gene_Name

### Data2.xxx contains:

1) Gene_Name: the gene names of RNAseq data sorted in ascending order of t-test p-values

2) P_value: the p-values of aforementioned genes

3) training_data: 20,131 gene expressions of 150 samples. The gene dimension is matched with Gene_Name

4) training_label: label information of the 150 training samples (1: dead and with the last follow-up days less than 1080 (3 years), 0:  have the last follow-up days more than 1080)

3) testing_data: 20,131 gene expressions of 37 samples. The gene dimension is matched with Gene_Name

4) testing_label: label information of the 37 testing samples (1: dead and with the last follow-up days less than 1080 (3 years), 0:  have the last follow-up days more than 1080)

 

## Part a) Functional enrichment analysis

In previous project, I performed t-test to select differentially expressed genes from RNAseq data. To further validate the selected differentially expressed genes, I will perform functional enrichment analysis of the genes.

Load Data1.xxx into R  and select the first 200 genes in Gene_Name to perform functional enrichment analysis with GSEA online toolLinks to an external site..

 
## Part b) Unsupervised learning (K-means clustering)

Cluster analysis is used to identify genes with similar expression patterns over experiment conditions or possibly related functions. We will first perform k-means clustering and check the functions of the genes in the same clusters. 
Load Data1.xxx into R. Select the first top 1000 genes from Gene_Name and perform k-means clustering (KMeansLinks to an external site. in cluster module of sklearn package for Python, kmeansLinks to an external site. in stats library for R and built in function kmeansLinks to an external site. for MATLAB) with k=10, 20, 50 on the expression profiles of these 1000 genes. For each case, plot the histogram of the cluster sizes.

2) Select one cluster from the k-means clustering with k = 20. Perform functional enrichment analysis of the genes in the cluster. Describe the enriched functions of the genes in the cluster. You should report the list of genes in the cluster and the enriched functions.

 

## Part c) Supervised learning (KNN and SVM)

Download Data2.xxx and perform classification to predict clinical outcome of patients with KNN and linear SVM in Python (KNeighborsClassifierLinks to an external site. in neighbors module of sklearn package, LinearSVCLinks to an external site. in svm module of sklearn package), R (knnLinks to an external site. in class library and svmLinks to an external site. in e1071 library) or MATLAB (knnclassifyLinks to an external site., svmtrainLinks to an external site.and svmclassifyLinks to an external site.). (For Python and MATLAB, you do not need to tune any parameters for SVMs, just use the default setting of SVM, for R, you need to set the kernel option to be ‘linear’ explicitly) 
1) Run KNN classifier with k=1, 3, 5 using the samples in training_data as training data and the samples in testing_data as test data. Report your classification accuracy for the three cases.

2) Now, instead of using all the genes as features you can select top 1,000 genes from Gene_Name as features. Repeat 1) using only these 1000 genes. Describe why the classification performance is improved if you only use 1000 genes as features.

3) Apply SVM with a linear kernel on the same data using the 1,000 genes as features. Report your classification accuracy.
