Epigenetic Regulation of COL5A2 in Lung Adenocarcinoma – Bioinformatics Workflow

Abstract 
Collagen type V alpha 2 (COL5A2) has emerged as an important regulator of tumor progression across multiple cancer types, but its epigenetic regulation in lung adenocarcinoma (LUAD) remains incompletely understood. In this study, we performed a pan‑cancer bioinformatics analysis of COL5A2 using publicly available cancer transcriptomic databases to characterize its expression patterns, clinicopathological associations, immune infiltration correlations, and prognostic relevance. We further integrated miRNA–mRNA interaction data to identify tumor‑suppressor miRNAs that may regulate COL5A2 and impact patient survival in LUAD. The analyses highlight COL5A2 and its regulatory miRNAs, miR‑101‑3p and miR‑29c‑3p, as potential diagnostic and prognostic biomarkers and modulators of the tumor immune microenvironment in lung adenocarcinoma.


Data and tools
All analyses were performed using publicly accessible web tools and TCGA-derived resources. 
No raw sequencing data are stored in this repository; instead, we provide a protocol to reproduce all results directly from the original sources.

External databases and web tools

1. TIMER2.0 – Tumor Immune Estimation Resource (URL: http://timer.cistrome.org/)
Used for:

A. COL5A2 expression in tumor vs normal tissues (Figure 1)

B. Correlation between COL5A2 expression and tumor‑infiltrating immune cells (Figure 3)


2. UALCAN – TCGA-based clinical and expression analysis (URL: https://ualcan.path.uab.edu/)

Used for:

A. Expression of COL5A2 across clinicopathological features (gender, age, race, stage) (described in manuscript text and supplementary figures)


3. GEPIA – Gene Expression Profiling Interactive Analysis (URL: http://gepia.cancer-pku.cn/)

Used for:

A. COL5A2 expression across tumor pathological stages (Figure 2)


4. Kaplan–Meier Plotter (URL: https://kmplot.com/analysis/)

Used for:

A. Overall survival analysis for COL5A2 expression in LUAD, STAD, and THCA (Figure 4)

5. STRING – Protein–protein interaction networks and enrichment (URL: https://cn.string-db.org/)

Used for:

A. COL5A2-centered protein–protein interaction network and extracellular matrix‑related partners (Figure 5)

B. Gene Ontology enrichment analysis


6. miRNet – miRNA–target interaction and network analysis (URL: http://www.mirnet.ca/)

Used for:

A. Identification of tumor‑suppressor miRNAs predicted to regulate COL5A2 (Figure 6)


7. StarBase – miRNA–mRNA interactome, expression, correlation, and survival (URL: http://starbase.sysu.edu.cn/)

Used for:

A. Differential expression of COL5A2‑related tumor‑suppressor miRNAs in LUAD and STAD (Figure 7)

B. Co‑expression (correlation) analysis between COL5A2 and miRNAs (Figure 8)

C. Univariate survival analysis of COL5A2‑related miRNAs in LUAD (Figure 9)


8. Sankey / network visualization platform (URL: https://www.bioinformatics.com.cn/en)

Used for:Schematic Sankey diagram of the proposed COL5A2–miRNA regulatory axis in LUAD (Figure 10)


Reproducibility instructions
This section documents, step by step, how each figure in the manuscript was generated for the inquiry gene COL5A2 using public web tools.

Figure 1 – COL5A2 expression profiles in tumors vs normal (TIMER2.0)
Tool: TIMER2.0 (http://timer.cistrome.org/)
Access date: 5 October 2025
Steps:
1. Open TIMER2.0 in a web browser.
2. Go to the “Gene_DE” module.
3. In the Gene symbol box, enter COL5A2.
4. Keep all TCGA cancer types and default settings.
5. Click Submit to generate boxplots of COL5A2 expression in tumor vs matched normal tissues.
6. Export the figure and/or the underlying data table and save as Figure1_TIMER2_COL5A2_DE_2025-10-05.*.

Figure 2 – COL5A2 expression across tumor stages (GEPIA)
Tool: GEPIA (http://gepia.cancer-pku.cn/)
Access date: 10 October 2025
Steps:
1. Open GEPIA.
2. Click the “Stage Plot” module.
3. In the Gene field, enter COL5A2.
4. Select each cancer type of interest (e.g., LUAD, STAD, THCA, etc.) from the TCGA list, one at a time.
5. Use default settings (ANOVA on tumor samples only, no predefined reference stage, normal tissues excluded).
6. Click Plot to generate stage-wise expression plots.
7. Download plots for the selected cancers and save as Figure2_GEPIA_COL5A2_[Cancer]_Stage_2025-10-10.*.

Figure 3 – Correlations between COL5A2 and immune cells in LUAD, STAD, THCA (TIMER2)
Tool: TIMER2.0 (http://timer.cistrome.org/)
Access date: 12 October 2025
Steps:
1. Open TIMER2.0.
2. Go to the “Immune” (or “Immune Gene”) module.
3. Set Gene = COL5A2.
4. For each cancer type (LUAD, STAD, THCA):
5. Select the cancer in the cancer-type dropdown.
6. Keep default immune cell types (e.g., B cells, CD8+ T cells, CD4+ T cells, macrophages).
7. Click Submit to obtain scatterplots and correlation statistics between COL5A2 expression and each immune cell type.
8. Export the correlation plots for LUAD, STAD, and THCA.
9. Save outputs as Figure3_TIMER2_COL5A2_Immune_LUAD_2025-10-12.*, ..._STAD_..., ..._THCA_....

Figure 4 – Association between COL5A2 and overall survival (Kaplan–Meier Plotter)
Tool: Kaplan–Meier Plotter (https://kmplot.com/analysis/)
Access date: 13 October 2025
Steps:
1. Open Kaplan–Meier Plotter and select the appropriate section for mRNA survival analysis. For each cancer (LUAD, STAD, THCA):
2. Choose the cancer type (e.g., lung adenocarcinoma, stomach adenocarcinoma, thyroid carcinoma).
3. In the Gene symbol box, enter COL5A2.
4. Set Split patients by median expression (high vs low) as in the manuscript.
5. Choose Overall survival (OS) as the endpoint.
6. Keep other settings at default unless otherwise specified.
7. Click “Draw Kaplan–Meier plot” to generate the survival curve.
8. Record the hazard ratio, confidence interval, and log‑rank p‑value reported by the tool.
9. Save each plot as Figure4_KMplotter_COL5A2_LUAD_OS_2025-10-13.*, ..._STAD_..., ..._THCA_....

Figure 5 – Protein–protein interaction network and ECM proteins (STRING)
Tool: STRING (https://cn.string-db.org/)
Access date: 15 October 2025
Steps:
1. Open STRING.
2.Select “Multiple proteins” input mode.
3.Enter COL5A2 as the query and set Species = Homo sapiens.
4.Set Edge meaning to “Evidence”.
5.Under Active interaction sources, select: Experiments, Text mining, Databases, Expression, Neighborhood, Co‑occurrence.
6.Set Minimum required interaction score to “medium confidence (0.400)”.
7.Limit the maximum number of interactors to 10 (or to the number used in the manuscript).
8.Run the query to obtain the COL5A2-centered interaction network.
9.Identify and highlight extracellular matrix–related proteins according to the STRING functional annotation or GO terms.
10.Export the network figure and, if used, tables of interacting proteins and GO enrichment.
11.Save as Figure5_STRING_COL5A2_network_2025-10-15.*.


Figure 6 – Tumor‑suppressor miRNAs predicted to regulate COL5A2 (miRNet)
Tool: miRNet (http://www.mirnet.ca/)
Access date: 18 October 2025
Steps:
1.Open miRNet.
2.Start a new analysis and set organism to Human.
3.Choose “Gene” as the input type.
4.Enter COL5A2 as the input gene.
5.Run the analysis to obtain miRNAs predicted/known to target COL5A2.
6.If used in the manuscript, filter the list to retain miRNAs with a tumor‑suppressor role based on literature.
7.Export the miRNA–gene interaction table and, if applicable, the network visualization.
8.Save as Figure6_miRNet_COL5A2_miRNAs_2025-10-18.*.


Figure 7 – Differential expression of downregulated tumor‑suppressor miRNAs (StarBase)
Tool: StarBase (http://starbase.sysu.edu.cn/)
Access date: 19 October 2025
Steps:
1.Open StarBase.
2.Navigate to the module for miRNA expression across cancers (v2.0 or version used).
3.For each selected tumor‑suppressor miRNA predicted to target COL5A2 (e.g., hsa-miR-101-3p, hsa-miR-29c-3p):
4.Query its expression profile in LUAD and STAD vs normal tissues.
5.Use default parameters for TCGA-based differential expression unless otherwise specified.
6.Extract plots or tables showing that these miRNAs are downregulated in LUAD and STAD.
7.Export the differential expression plots/tables.
8.Save as Figure7_StarBase_[miRNA]_LUAD_STAD_DE_2025-10-19.*.



Figure 8 – Co‑expression analysis between COL5A2 and tumor‑suppressor miRNAs (StarBase)
Tool: StarBase (http://starbase.sysu.edu.cn/)
Access date: 19 October 2025
Steps:
1.In StarBase, navigate to the module for miRNA–mRNA correlation.
2.For each selected tumor‑suppressor miRNA (e.g., hsa-miR-101-3p, hsa-miR-29c-3p):
3.Set mRNA = COL5A2.
4.Set miRNA = the miRNA of interest.
5.Select LUAD or STAD as the cancer type.
6.Run the correlation analysis to obtain the correlation coefficient (r) and p‑value between COL5A2 and each miRNA.
7.Export the correlation plots/tables for LUAD and STAD.
8.Save as Figure8_StarBase_COL5A2_[miRNA]_corr_LUAD_2025-10-19.*, ..._STAD_....



Figure 9 – Univariate survival analysis of COL5A2‑related miRNAs in LUAD (StarBase)
Tool: StarBase (http://starbase.sysu.edu.cn/)
Access date: 19 October 2025
Steps:
1.In StarBase, open the miRNA survival analysis module.
2.For each COL5A2‑related tumor‑suppressor miRNA of interest:
3.Select LUAD as the cancer type.
4.Input the miRNA name (e.g., hsa-miR-101-3p, hsa-miR-29c-3p).
5.Use the default or specified cut‑off (e.g., median expression) to divide patients into high- vs low‑expression groups.
6.Choose overall survival as the endpoint.
7.Run the survival analysis to generate Kaplan–Meier curves, and record hazard ratios and p‑values.
8.Export survival plots and tables.
9.Save as Figure9_StarBase_[miRNA]_LUAD_survival_2025-10-19.*.




Figure 10 – Schematic representation of the COL5A2–miRNA axis in LUAD (Sankey)
Tool: Bioinformatics visualization platform (e.g., https://www.bioinformatics.com.cn/en or similar Sankey tool)
Steps:
1.Prepare an input table listing the relationships between:COL5A2,tumor‑suppressor miRNAs (e.g., hsa-miR-101-3p, hsa-miR-29c-3p),relevant cancer types or functional categories.
2.Go to the Sankey diagram module of the chosen platform.
3.Upload the prepared table in the required format (e.g., source–target–value columns).
4.Customize node labels and colors to distinguish COL5A2, miRNAs, and cancer types (e.g., LUAD).
5.Keep other settings at default or as described in the manuscript.
6.Generate the Sankey diagram and export it as a high‑resolution image.
7. Save as Figure10_Sankey_COL5A2_miRNA_axis_LUAD_2025-10-20.*.



