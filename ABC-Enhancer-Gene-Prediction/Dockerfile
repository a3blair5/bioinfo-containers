ARG BASE_CONTAINER=jupyter/datascience-notebook:latest
FROM $BASE_CONTAINER

USER root
RUN apt-get update && apt-get install -y zlib1g-dev zlib1g libbz2-dev liblzma-dev wget libncurses5-dev


RUN conda install -c bioconda/label/cf201901 samtools
RUN conda install -c bioconda tabix
RUN conda install -c bioconda bedtools
RUN conda install -c bioconda pyranges
#RUN conda install numpy pandas scipy pyBigWig
#RUN conda install pandas
#RUN conda install scipy
#RUN conda install pyBigWig

RUN git clone https://github.com/broadinstitute/ABC-Enhancer-Gene-Prediction.git
RUN conda env create -f ABC-Enhancer-Gene-Prediction/macs.yml
RUN conda env create -f ABC-Enhancer-Gene-Prediction/abcenv.yml

#RUN wget https://sourceforge.net/projects/samtools/files/tabix/tabix-0.2.5.tar.bz2
#RUN tar jxvf tabix-0.2.5.tar.bz2
#RUN cd tabix-0.2.5 && make
#CMD make
#RUN cd ..
#RUN git clone https://github.com/broadinstitute/ABC-Enhancer-Gene-Prediction.git
#RUN git clone https://github.com/aidenlab/juicer.git
#RUN cd ABC-Enhancer-Gene-Prediction
#RUN conda env create -f macs.yml 
#RUN conda env create -f abcenv.yml

