FROM matthewee/r-centos7:R-3.5.3
LABEL ggbiplot_Version=0.55
LABEL factoextra=1.0.5.999
LABEL R_Version="3.5.3"
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

# dependence for devtools
RUN yum install -y openssl-devel
RUN Rscript -e "install.packages('devtools')" && Rscript -e "devtools::install_github('vqv/ggbiplot')" && Rscript -e "devtools::install_github('kassambara/factoextra')"
VOLUME /mnt
CMD ["bash"]
