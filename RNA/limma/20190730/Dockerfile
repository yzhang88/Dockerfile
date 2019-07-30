FROM matthewee/debian_stretch-r:3.6.0
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

RUN R -e 'BiocManager::install(c("Biobase", "GEOquery", "limma", "org.Hs.eg.db", "biomaRt", "org.Mm.eg.db", "org.Rn.eg.db", "maSigPro"), ask=FALSE, clean=TRUE, quiet=TRUE)'
CMD ["bash"]
