FROM bioconductor:3.17

USER idies

WORKDIR /home/idies

# https://carpentries-incubator.github.io/bioc-intro
RUN Rscript -e \
    "pkgs_biocintro <- c( 'SummarizedExperiment', 'UCLouvain-CBIO/rWSBIM1207', 'hexbin', 'patchwork', 'gridExtra', 'tidySummarizedExperiment' ); \
    BiocManager::install( pkgs_biocintro )"

# RNA-seq
RUN Rscript -e \
    "pkgs_rnaseq <- c( 'DESeq2', 'tximport', 'biomaRt', 'clusterProfiler', 'pathview', 'pheatmap' ); \
    BiocManager::install( pkgs_rnaseq )"

# Genomes
RUN Rscript -e \
    "pkgs_genomes <- c( 'org.Mm.eg.db', 'org.Dm.eg.db', 'org.Dr.eg.db' ); \
    BiocManager::install( pkgs_genomes )"

# single-cell
RUN Rscript -e \
    "pkgs_bioc <- c( 'reticulate', 'GenomicRanges', 'rtracklayer', 'GEOquery', 'CoGAPS' ); \
    pkgs_osca <- c( 'DropletUtils', 'Rtsne', 'scRNAseq', 'scuttle', 'scran', 'scater', 'velociraptor', 'uwot' ); \
    pkgs_monocle3 <- c( 'DelayedMatrixStats', 'limma', 'SingleCellExperiment', 'batchelor', 'Matrix.utils' ); \
    BiocManager::install( c( pkgs_bioc, pkgs_osca, pkgs_monocle3 ) ); \
    remotes::install_version( 'Seurat', version='4.3.0' ); \
    remotes::install_github( 'cole-trapnell-lab/leidenbase@v0.1.9' ); \
    remotes::install_github( 'cole-trapnell-lab/monocle3@v1.3.1' ); \
    remotes::install_github( 'pcahan1/singleCellNet@v0.4.1' );"

# PG2022
RUN Rscript -e \
    "pkgs_pg2022 <- c( 'swirl', 'rebook', 'DropletTestFiles', 'EnsDb.Hsapiens.v86', 'mbkmeans', 'dendextend', 'apcluster', 'dynamicTreeCut', 'celldex', 'SingleR', 'GSEABase', 'AUCell', 'GO.db', 'TENxPBMCData', 'MouseGastrulationData', 'TSCAN', 'slingshot', 'tradeSeq' ); \
    BiocManager::install( pkgs_pg2022 )"

USER root
