FROM matthewee/r-centos7:R-3.5.3
LABEL phyloseq_version="1.24.2"
LABEL R_Version="3.5.3"
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
RUN Rscript -e "source('http://bioconductor.org/biocLite.R');biocLite('phyloseq', ask = F, clean = T)"
VOLUME /mnt
CMD ["bash"]
