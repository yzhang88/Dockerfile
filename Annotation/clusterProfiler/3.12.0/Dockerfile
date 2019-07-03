FROM matthewee/biocmanager:1.30.4
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
LABEL clusterProfiler=3.12.0
# dependence
RUN yum install -y libxml2-devel && yum install -y openssl-devel
RUN R -e 'BiocManager::install(c("clusterProfiler", "org.Hs.eg.db"), ask = FALSE)'
VOLUME /mnt
CMD ["bash"]
