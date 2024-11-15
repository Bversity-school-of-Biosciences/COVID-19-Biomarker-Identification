# COVID-19-Biomarker-Identification
**Understanding the Immune Response by analyzing mRNA Expression Profiles in COVID-19 Patients**

**Overview**
This project explores the immune response to COVID-19 by analyzing mRNA expression profiles in patients. The primary objective is to identify potential biomarkers from the immune system's response to the virus, which could aid in diagnostics and drug discovery. By examining gene expression data, we aim to uncover patterns that reveal key immune pathways, which may contribute to understanding how the body reacts to COVID-19 infection.

**Tools Used**
The project utilizes a range of tools and platforms for data processing, annotation, and visualization:

* Google Sheets: For organizing and manipulating the gene expression data in spreadsheet format.
* Gene Expression Omnibus (GEO) Datasets: Data is obtained from the GEO database hosted by NCBI, which contains gene expression profiles related to COVID-19 patients.
* DAVID Bioinformatics Resources: Used for functional annotation to analyze biological, molecular, and cellular functions of the identified genes.
* ENSEMBL Symbol Converter: A tool for converting ENSEMBL gene IDs to their respective gene symbols and names.
* Tableau: For visualizing the results, including key biomarkers, gene interactions, and immune pathways.
* PubMed: To search for relevant research papers and existing literature related to the identified genes and their role in immune responses.
* ClinicalTrials.gov: For finding ongoing clinical trials that target the identified biomarkers or genes, assisting in linking the results to real-world applications.

**Data Collection**
The mRNA expression data for this project was sourced from the Gene Expression Omnibus (GEO), a publicly accessible database containing a wide range of gene expression datasets. The accession number is  GSE152418 for this dataset which provides gene expression profiles comparing healthy samples with COVID-19 diseased samples, helping to identify immune system responses during infection.

**Data Preparation & Analysis**

**Data Download & Import:**
The gene expression data was downloaded from the GEO database in .txt format, using the dataset identified by the accession number GSE152418. The raw data was then imported into Google Sheets for cleaning and analysis.

**Data Cleaning:**
The dataset was cleaned by filtering out blank and zero values for gene expression. This step was necessary to ensure the accuracy and reliability of the analysis, as blank or zero values would introduce bias into the results.

**Separating Healthy and Diseased Samples:**
The next step involved calculating the average gene expression values for both the healthy and COVID-19 diseased samples. The values for the healthy samples were stored in a separate column, and the values for the diseased samples were placed in another column.

**Fold Change Calculation:**
In a new column, the fold change for each gene was calculated by dividing the average diseased value by the average healthy value. This step is crucial for identifying the magnitude of change in gene expression between healthy and diseased states. A fold change greater than 2 was considered significant for further analysis.

**Statistical Analysis (T-test):**
A T-test was conducted to calculate the p-value for each gene, assessing whether the difference in expression between healthy and diseased samples was statistically significant. The p-value threshold for significance was set to <= 0.05.

**Filtering Significant Genes:**
After conducting the T-test, genes with a p-value <= 0.05 and a fold change >= 2 were retained for further analysis. These criteria were used to focus on genes that show both statistical significance and substantial differences in expression between healthy and diseased samples.

**Gene Annotation Using DAVID:**
The filtered dataset, consisting of significant genes, was uploaded to the DAVID Bioinformatics Resources tool. DAVID was used to perform functional annotation of the genes, identifying key biological pathways, molecular functions, and cellular components associated with the immune response to COVID-19. A subset of 24 genes was selected for sample annotation purposes based on a referenced paper. These genes were used as an example for deeper exploration, but further analysis could certainly include additional genes identified in the dataset.

**Data Visualization**

**Importing Data to Tableau:**
After completing the data preparation and filtering steps, the cleaned and processed dataset was imported into Tableau Public Desktop for visualization. This tool was used to create insightful visual representations of the data.

**Selecting Visualization Type:**
To effectively display the results, a horizontal bar graph was chosen as the most appropriate chart type. This allows for easy comparison of gene expression changes across the healthy and diseased conditions.

**Configuring the Graph:**
* The rows of the bar graph contain the gene symbols.
* The columns include key data points such as fold change, p-value, average control values, and average diseased values. This allows for a clear comparison of the gene expression levels between healthy and 
  diseased samples, as well as the statistical significance of the changes.
  
**Using Color to Represent Fold Change:**
* A color gradient was applied to the bar graph to represent the range of fold changes. This helps to visually distinguish between genes with small and large changes in expression, providing an at-a-glance 
  overview of which genes show the most significant differences.

**Labeling Gene Expression Values:**
The labeling option was used to display the exact fold change values for each gene on the bar graph. This ensures that users can easily interpret the magnitude of change for each gene without needing to refer back to the raw data.

**Visual Insights:**
The horizontal bar graph provides a clear visual representation of the most significantly differentially expressed genes, highlighting those with the largest fold changes and the most statistically significant p-values. This visualization helps to identify potential biomarkers that could be further investigated for their roles in the immune response to COVID-19.

**Conclusion**
This project analyzed mRNA expression profiles from COVID-19 patients using the GSE152418 dataset to identify potential biomarkers for diagnostic and therapeutic applications. By comparing gene expression between healthy and diseased samples, significant genes were identified through statistical analysis and functional annotation. The results were visualized in Tableau to highlight key gene expression changes. While a subset of 24 genes was analyzed as a sample, this methodology can be extended to other datasets in the GEO database, offering further insights into the immune response to COVID-19 and potential biomarkers for future research.
