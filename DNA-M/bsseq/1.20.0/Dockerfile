FROM matthewee/biocmanager:1.30.4
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
LABEL R=3.6.0
LABEL bsseq=1.20.0

RUN apt-get install -y --no-install-recommends libxml2-dev && apt-get clean
RUN R -e "BiocManager::install('bsseq', ask = FALSE)"
VOLUME /mnt
CMD ["bash"]
