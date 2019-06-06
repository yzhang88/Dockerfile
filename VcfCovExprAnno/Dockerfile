FROM conda/miniconda3:latest
LABEL maintainer="xizhihui <zhihui_xi@qq.com>"
LABEL description="Docker image for annotation in neoantigen prediction pipeline"
LABEL lastModified="2019-06-08"

ARG author="xizhihui"
USER root

# bam-readcount-helper-cwl
RUN apt-get update \
    && apt-get install -y build-essential git-core cmake>=2.8.3 zlib1g-dev libncurses-dev patch wget
RUN mkdir -p /software/bam-readcount
WORKDIR /software/bam-readcount
RUN git clone https://github.com/genome/bam-readcount.git /tmp/bam-readcount \
    && cmake /tmp/bam-readcount\
    && make \
    && rm -rf /tmp/bam-readcount \
    && ln -s /software/bam-readcount/bin/bam-readcount /usr/bin/bam-readcount
RUN wget https://raw.githubusercontent.com/genome/docker-bam_readcount_helper-cwl/master/bam_readcount_helper.py -O /usr/bin/bam_readcount_helper.py \
    && chmod 775 /usr/bin/bam_readcount_helper.py

# samtools, vt (vcftools)
RUN conda config --add channels bioconda \
    && conda config --add channels conda-forge \
    && conda install -y samtools vt openjdk

# vatools(vcf-annotate-tools)
RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple vatools cyvcf2

# wrappers
ADD annotate /usr/bin/annotate
RUN chmod 775 /usr/bin/annotate \
	&& chmod 775 /usr/bin/bam_readcount_helper.py

# add user
RUN groupadd -r -g 1000 ${author} \
&& useradd -r -g ${author} -u 1000 ${author} \
&& mkdir /home/${author} \
&& ln -s /usr/bin/java /bin/ \
&& chown -R ${author}:${author} /home/${author}
WORKDIR /home/${author}
USER ${author}