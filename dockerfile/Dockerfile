#FROM ubuntu:20.04
FROM continuumio/miniconda3

ENV DEBIAN_FRONTEND=noninteractive

#Get latest. (Is this a good idea?)
RUN apt-get update -y && apt-get upgrade -y

# Add gdown. This talks to google drive. We may need this later for samples.
RUN pip install gdown

# Clone project into sxyu/svox2 into docker image.
RUN cd /root && git clone https://github.com/sxyu/svox2.git

# Setup the "env"
RUN cd /root/svox2 && conda env create -f environment.yml

# Note: After setting up the "env" anthing you want to do in it must "cd /root/svox2 && conda activate plenoxel"
# Note: To setup a full shell use "/bin/bash", "--login", "-c"

#SHELL ["/bin/bash", "--login", "-c"]
RUN ["/bin/bash", "--login", "-c", "cd /root/svox2 && conda activate plenoxel && pip install . && conda deactivate"]
RUN ["/bin/bash", "--login", "-c", "cd /root/svox2 && conda activate plenoxel && pip install gdown && conda deactivate"]

#CMD bash --login -i -c "cd /root/svox2 && conda activate plenoxel && bash"




