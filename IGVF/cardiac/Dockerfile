FROM jupyter/datascience-notebook:latest

USER root
RUN conda install -c conda-forge r-seurat
RUN R -e "install.packages(c('cluster','enrichR','BiocManager'), repos='http://cran.us.r-project.org')"
RUN R -e "BiocManager::install(c('limma', 'rGREAT', 'annotatr', 'karyoploteR','TxDb.Hsapiens.UCSC.hg19.knownGene', 'org.Hs.eg.db', 'BSgenome.Hsapiens.UCSC.hg19', 'BSgenome.Hsapiens.UCSC.hg19.masked'))"
RUN R -e "devtools::install_github('jokergoo/rGREAT')"
RUN conda install --channel conda-forge --channel bioconda pybedtools bedtools htslib
#RUN conda install --channel conda-forge --channel bioconda bedtools htslib
RUN conda install -c plotly plotly 
RUN conda install chart-studio
USER $NB_UID
RUN pip install --user biopython synapseclient



