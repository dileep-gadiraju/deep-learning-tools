# Jupyter notebook with dependecies to debug layout detection pipeline
FROM jupyter/minimal-notebook
#FROM bgruening/docker-jupyter-notebook

LABEL maintainer="Dileep Gadiraju"

ENV DEBIAN_FRONTEND="noninteractive"
## Allow colab to connect to this container
#ENV CORS_ORIGIN="https://colab.research.google.com"
USER root

RUN apt-get update && apt-get install -y software-properties-common build-essential
RUN apt install -y libssl-dev libffi-dev libxml2-dev libxslt1-dev zlib1g-dev
RUN apt-get install -y libcurl4-gnutls-dev
RUN apt update && apt install -y python3-pip
RUN pip install --upgrade pip setuptools wheel &&\
  pip install scikit-build &&\
  pip install cmake &&\
  apt install -y libopencv-dev python3-opencv

RUN pip install jupyter_http_over_ws && \
    jupyter serverextension enable --py jupyter_http_over_ws

RUN apt install -y curl


RUN apt-get install -y make git
RUN pip install torch
RUN pip install layoutparser==0.1.2 && pip install Shapely==1.7.1 && pip install pytesseract && pip install pdf2image
RUN pip install 'git+https://github.com/facebookresearch/detectron2.git#egg=detectron2'
RUN apt-get install poppler-utils
RUN apt install tesseract-ocr -y
RUN apt install tesseract-ocr-script-latn -y
RUN apt-get install libfreetype6-dev -y
RUN pip install pillow==4.1.1

RUN echo "c.NotebookApp.ip = '*'" >> ~/.jupyter/jupyter_notebook_config.py
RUN echo "c.NotebookApp.allow_origin = '*'" >> ~/.jupyter/jupyter_notebook_config.py

USER $NB_UID