FROM centos:7
LABEL github "https://github.com/hellobioinfo"
LABEL maintainer "matthewhakka@gmail.com"
WORKDIR /app

# install dependence. see: https://davetang.org/muse/2018/02/06/compiling-r-gnu-readline/
RUN yum groupinstall "Development Tools" -y && yum install -y readline-devel libXt-devel zlib-devel bzip2-devel xz xz-devel pcre-devel libcurl-devel

# download R 3.6.0 and instll
RUN curl -C - -o R3.6 https://cran.r-project.org/src/base/R-3/R-3.6.0.tar.gz && tar -zxf /app/R3.6 && cd /app/R-3.6.0
RUN ./configure --prefix=/opt/R/3.6 --with-x=yes --enable-R-shlib=yes --with-cairo=yes --with-libpng=yes && make 

CMD ["bash"]
