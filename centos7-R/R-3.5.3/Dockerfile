FROM centos:7
LABEL R_Version="3.5.3"
LABEL github="https://github.com/hellobioinfo"
LABEL maintainer="matthewhakka@gmail.com"
WORKDIR /app

# install dependence. see: https://davetang.org/muse/2018/02/06/compiling-r-gnu-readline/
RUN yum groupinstall "Development Tools" -y && yum install -y zlib-devel bzip2-devel xz-devel pcre-devel libcurl-devel java-1.8.0-openjdk-devel readline-devel  && yum clean all

# download R 3.5.3 and install
RUN curl -C - -o R3.5 https://cran.r-project.org/src/base/R-3/R-3.5.3.tar.gz && tar -zxf /app/R3.5 && rm -rf /app/R3.5
WORKDIR /app/R-3.5.3
RUN ./configure --with-x=no --with-readline=yes && make && make install

# select CRAN mirror
RUN echo options\(\"repos\" = c\(CRAN=\"https://mirrors.tuna.tsinghua.edu.cn/CRAN/\"\)\) >> ~/.Rprofile

# dirs for future mount(bind)
RUN mkdir /MntWorkdir /MntData /MntDatabase /MntResult /Mnt1 /Mnt2 /Mnt3

CMD ["bash"]
