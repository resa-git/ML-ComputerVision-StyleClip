FROM python:3.6
RUN apt-get update -y && \
    apt-get install build-essential cmake pkg-config -y
WORKDIR /home
RUN pip install dlib==19.9.0
RUN pip install jupyter -U && pip install jupyterlab
RUN pip install opencv-python-headless face_recognition matplotlib
EXPOSE 8888
#RUN docker with following commands
#docker run -it -p 8888:8888 -v "$(pwd)"/work:/home/work face:latest /bin/bash
#jupyter lab --ip=0.0.0.0 --allow-root
