FROM matthewee/debian_stretch-r:3.6.0
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

RUN R -e "install.packages('pheatmap', dependencies = TRUE, clean = TRUE)" && \
    R -e "BiocManager::install('ComplexHeatmap', ask = FALSE, clean = TRUE)" && \
    R -e "devtools::install_github('caleblareau/BuenColors', clean = TRUE)"
CMD ["bash"]
