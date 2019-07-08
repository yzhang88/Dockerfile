FROM matthewee/debian_stretch-r:3.6.0
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
LABEL BiocManager=1.30.4
RUN R -e 'install.packages("https://cran.r-project.org/src/contrib/BiocManager_1.30.4.tar.gz", repos = NULL, type = "source", dependencies = TRUE, clean = TRUE)'
VOLUME /mnt
CMD ["bash"]
