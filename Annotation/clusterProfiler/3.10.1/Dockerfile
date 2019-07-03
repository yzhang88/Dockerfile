FROM matthewee/biocmanager:1.30.4
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
LABEL clusterProfiler=3.10.1
# dependence
RUN yum install -y libxml2-devel openssl-devel libpng-devel
RUN R -e 'BiocManager::install(c("clusterProfiler", "org.Hs.eg.db", "pathview"), ask = FALSE)'
VOLUME /mnt
CMD ["bash"]
