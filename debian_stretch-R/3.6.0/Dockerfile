FROM debian:stretch-20190610
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
LABEL R=3.6.0

WORKDIR /App

# Prepare environment. "build-essential" and "gfortran" for build/compile. "libreadline-dev" for "--with-readline=yes". 
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
	wget \
	build-essential \
	gfortran \
	libreadline-dev \
    libx11-dev \
	xorg-dev \
	libbz2-dev \
	ca-certificates \
	liblzma-dev \
	libpcre++-dev \
	libcurl4-openssl-dev \
	default-jre \
	&& apt-get clean

# Download and install R-3.6.0
RUN wget https://cran.r-project.org/src/base/R-3/R-3.6.0.tar.gz \
    && tar -xf R-3.6.0.tar.gz \
	&& rm R-3.6.0.tar.gz \
	&& cd R-3.6.0 \
	&& ./configure \
	&& make \
	&& make install

# select CRAN mirror
RUN echo options\(\"repos\" = c\(CRAN=\"https://mirrors.tuna.tsinghua.edu.cn/CRAN/\"\)\) >> ~/.Rprofile

WORKDIR /mnt
RUN mkdir /MntWorkdir /MntData /MntDatabase /MntResult /Mnt1 /Mnt2 /Mnt3
VOLUME /mnt
CMD ["bash"]
