FROM r-centos7:R-3.5.3
LABEL PureCN_Version="1.12.2"
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

ENV PURECN=/usr/local/lib64/R/library/PureCN/extdata
WORKDIR /app

# install dependence first. libxml2-devel for "XML" in R.
RUN yum install -y libxml2-devel openssl-devel

# install PureCN from Bioconductor
RUN R -e "install.packages('BiocManager')" && R -e "BiocManager::install('PureCN', ask = FALSE)" && R -e "install.packages('optparse')"

CMD ["bash"]
