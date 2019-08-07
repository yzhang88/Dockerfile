FROM debian:stretch-20190610
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"

WORKDIR /App
# install bedtools use apt-get
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
	bedtools && \
    apt-get clean

COPY *.tar.bz2 /App/

RUN	tar -jxf htslib-1.9.tar.bz2 && \
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
	echo "export LD_LIBRARY_PATH=/usr/local/lib/" >> ~/.bashrc && \
	cd /App && \
	rm -rf *

CMD ["bash"]
