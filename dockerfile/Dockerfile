#FROM ubuntu:20.04
FROM continuumio/miniconda3

ENV DEBIAN_FRONTEND=noninteractive

RUN cd /root && git clone https://github.com/sxyu/svox2.git
RUN cd /root/svox2 && conda env create -f environment.yml

#SHELL ["/bin/bash", "--login", "-c"]
RUN ["/bin/bash", "--login", "-c", "cd /root/svox2 && conda activate plenoxel && pip install . && conda deactivate"]
RUN ["/bin/bash", "--login", "-c", "cd /root/svox2 && conda activate plenoxel && pip install gdown && conda deactivate"]



