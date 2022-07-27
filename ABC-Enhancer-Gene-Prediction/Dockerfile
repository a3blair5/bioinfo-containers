ARG BASE_CONTAINER=jupyter/datascience-notebook:latest
FROM $BASE_CONTAINER

USER root
RUN apt-get update && apt-get install -y \
    default-jdk \
    gawk \
    gcc \
    git \
    libz-dev \
    locales \
    make \
    unzip \
    bzip2 \
    libbz2-dev \
    zlib1g-dev \
    zlib1g \
    liblzma-dev \
    wget \
    libncurses5-dev \	
&& rm -rf /var/lib/apt/lists/*

# GAWK has the 'and' function, needed for chimeric_blacklist
RUN echo 'alias awk=gawk' >> ~/.bashrc

# Need to be sure we have this for stats
RUN locale-gen en_US.UTF-8

WORKDIR /opt/

ADD https://github.com/lh3/bwa/archive/v0.7.17.zip .
RUN unzip v0.7.17.zip 
RUN cd bwa-0.7.17/ && make
RUN ln -s bwa-0.7.17/bwa bwa

RUN conda install -c bioconda/label/cf201901 samtools
RUN conda install -c bioconda tabix
RUN conda install -c bioconda bedtools
RUN conda install -c bioconda pyranges

RUN git clone https://github.com/broadinstitute/ABC-Enhancer-Gene-Prediction.git
RUN conda env create -f ABC-Enhancer-Gene-Prediction/macs.yml
RUN conda env create -f ABC-Enhancer-Gene-Prediction/abcenv.yml

RUN git clone https://github.com/aidenlab/juicer.git

