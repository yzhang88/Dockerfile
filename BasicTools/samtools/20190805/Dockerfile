FROM debian:stretch-20190610
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

WORKDIR /App
RUN apt-get update && \
    apt-get install -y --no-install-recommends bzip2 \
	autoconf \
	automake \
	make \
	gcc \
	perl \
	zlib1g-dev \
	libbz2-dev \
	liblzma-dev \
	libcurl4-gnutls-dev \
	libssl-dev \
	libncurses5-dev \
	libperl-dev \
	libgsl0-dev \
	bedtools \
	wget && \
	wget  --no-check-certificate https://github.com/samtools/htslib/releases/download/1.9/htslib-1.9.tar.bz2 && \
	wget --no-check-certificate https://github.com/samtools/bcftools/releases/download/1.9/bcftools-1.9.tar.bz2 && \
	wget --no-check-certificate https://github.com/samtools/samtools/releases/download/1.9/samtools-1.9.tar.bz2 && \
	tar -jxf htslib-1.9.tar.bz2 && \
	tar -jxf bcftools-1.9.tar.bz2 && \
	tar -jxf samtools-1.9.tar.bz2 && \
	cd htslib-1.9 && \
	./configure && \
	make && \
	make install && \
	cd ../samtools-1.9 && \
	./configure --with-htslib=system && \
	make && \
	make install && \
    cd ../bcftools-1.9 && \
    ./configure --with-htslib=system && \
	make && \
	make install && \
    apt-get clean && \
	echo "LD_LIBRARY_PATH=/usr/local/lib/" >> ~/.bashrc && \
	cd /App && \
	rm -rf *

CMD ["bash"]
