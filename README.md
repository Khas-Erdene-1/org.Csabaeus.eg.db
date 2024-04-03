# org.Csabaeus.eg.db

# Description
Package: org.Csabaeus.eg.db, 
Title: Genome wide annotation for Chlorocebus sabaeus, 
Description: Genome wide annotation for Chlorocebus sabaeus, primarily based on mapping using Entrez Gene identifiers.
Version: 0.1, 
Author1: Khas Erdene Battogtokh <khaserdene@korea.ac.kr>, 
Author2: Lee Haram <lee1006hr@korea.ac.kr>, 
Maintainer: Khas Erdene Battogtokh <khaserdene@korea.ac.kr>, 
Depends: R (>= 2.7.0), methods, AnnotationDbi (>= 1.64.1), 
Suggests: DBI, annotate, RUnit, 
License: Artistic-2.0, 
organism: Chlorocebus sabaeus, 
species: Chlorocebus sabaeus, 
biocViews: OrgDb, annotation,

# Installation
Depends: R (>= 2.7.0), methods, AnnotationDbi (>= 1.64.1)

```r
# Load required packages
library(clusterProfiler)
library(org.Csabaeus.eg.db)

# Example gene list (replace with your own gene list)
gene_list <- c("ENSCSAG00000041768", "ENSCSAG00000004341", "ENSCSAG00000006335", "ENSCSAG00000025821", "ENSCSAG00000024023")

# Perform GO enrichment analysis
go_result <- enrichGO(
  gene          = gene_list,               # Input gene list
  OrgDb         = org.Csabaeus.eg.db,      # Organism annotation database
  keyType       = "ENSEMBL",               # Gene ID type
  ont           = "BP",                    # Ontology: Biological Process
  pAdjustMethod = "BH",                    # Adjust p-values using Benjamini-Hochberg method
  pvalueCutoff  = 0.05                     # Significance cutoff for adjusted p-values
)

# Print the top enriched GO terms
print(head(go_result))
```
# References
1. [AnnotationForge](https://bioconductor.org/packages/release/bioc/html/AnnotationForge.html)
1. [AnnotationDbi](https://bioconductor.org/packages/release/bioc/html/AnnotationDbi.html)
