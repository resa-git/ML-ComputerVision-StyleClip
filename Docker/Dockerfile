# VERSION: 0.1.0
# DESCRIPTION: Basic extensible Jupyter Notebook/Lab Container
# BUILD: docker build --rm -t docker-jupyter-extensible .

FROM jupyter/minimal-notebook:ubuntu-20.04
USER root
RUN apt-get update && apt-get install -y \
    libfcgi-dev                          \
	wget								 \
	curl								 \
	git								     \
    libglib2.0-dev                       \
    libsoup2.4-dev                       \
    libssl-dev                           \
    python3-pip                          \
	ffmpeg	                             \
    unzip                                \
    valac                                \
	bash								\
    && rm -rf /var/lib/apt/lists/* &&	 \
    apt-get update 				 

#RUN git clone https://github.com/stylegan-human/StyleGAN-Human.git

ADD https://github.com/ninja-build/ninja/releases/download/v1.8.2/ninja-linux.zip /tmp
RUN unzip /tmp/ninja-linux.zip -d /usr/local/bin
RUN rm -f /tmp/ninja-linux.zip
RUN update-alternatives --install /usr/bin/ninja ninja /usr/local/bin/ninja 1 --force 

USER $NB_UID
#COPY /home/jovyan/StyleGAN-Human /home/jovyan/work/StyleGAN-Human
#RUN pip install opencv-python-headless Pillow 
#RUN pip install -U click

RUN conda update conda
#COPY requirements.txt requirements.txt
#RUN pip install -r requirements.txt --user
#-----------------------------------

COPY environment.yml environment.yml
#USER root
#RUN conda install conda-build
#RUN conda update conda
#RUN conda update conda-build

RUN conda env create -f environment.yml 
#RUN python -m ipykernel install --user --name stylehuman --display-name "stylehuman"
#RUN source activate base
#RUN conda env update -n base -f environment.yml --prune
#ENV PATH /opt/conda/envs/mro_env/bin:$PATH

