FROM tensorflow/tensorflow:latest-gpu-jupyter

ARG DEBIAN_FRONTEND=noninteractive

# Install apt dependencies
RUN apt-get update && apt-get install -y \
    git \
    gpg-agent \
    python3-cairocffi \
    protobuf-compiler \
    python3-pil \
    python3-lxml \
    python3-tk \
    wget

# Add new user to avoid running as root
RUN useradd -ms /bin/bash tensorflow
USER tensorflow

# permissions to user
RUN chmod 777 /home/tensorflow && \
chown ${uid}:${gid} -R /home/tensorflow
ENV HOME /home/tensorflow

WORKDIR /home/tensorflow

ENV TF_CPP_MIN_LOG_LEVEL 3

#-----------------------------------------------------------------------------------------------------------


#STEPS TO CREATE AND RUN DOCKER IMAGE
#Host machine:
#   docker build -t tf2 .
#   docker run --gpus all -it --rm --user $(id -u):$(id -g) --group-add users -p 8888:8888 -p 6006:6006 -v /home/1644451/Documents:/home/tensorflow/Documents tf2 bash

# docker run --gpus all -it --rm --user $(id -u):$(id -g) --group-add users --network=host -v /home/1644451:/home/tensorflow/Documents tf2 bash


#We used some specific flags in this command:
#-it is used to open an interactive terminal
#--rm is used so that when we exit the container, it will remove it
#--name is used to name the container with a custom name
#--network=host is used to have access to the Internet in the container (same network as the host machine)


#Inside the Container : 
#   cd Documents/Tensorflow #folder_you_need_in_jupter_notebook
#   jupyter notebook --ip 0.0.0.0 --no-browser --allow-root

#NOTE: above command works even without no-browser flag!

#Host machine access this url : 
#   localhost:8888/tree‌​ 



