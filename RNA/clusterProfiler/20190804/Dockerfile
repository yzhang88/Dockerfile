FROM matthewee/debian_stretch-r:3.6.0
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

RUN R -e "BiocManager::install(c('clusterProfiler', 'pathview', 'org.Hs.eg.db', 'org.Mm.eg.db', 'org.Rn.eg.db', 'KEGGREST', 'enrichplot'), ask = FALSE, clean=TRUE)"
CMD ["bash"]
