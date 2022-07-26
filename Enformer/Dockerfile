ARG BASE_CONTAINER=tensorflow/tensorflow:latest-gpu-jupyter 
FROM $BASE_CONTAINER
# USER root
# RUN conda install cudatoolkit
RUN pip install \
	'dm-sonnet==2.0.0' \
	'kipoiseq==0.5.2'\	
	'numpy'\
	'pandas'\
	'tensorflow'\
	'tensorflow-hub==0.11.0'\
