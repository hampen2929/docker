# base

## CPU
FROM ubuntu18.04

## GPU
# FROM nvidia/cuda:10.1-cudnn7-runtime-ubuntu18.04
# FROM nvcr.io/nvidia/pytorch:19.12-py3
# FROM nvcr.io/nvidia/pytorch:20.03-py3

# init
USER root
ENV http_proxy $HTTP_PROXY
ENV https_proxy $HTTP_PROXY

RUN apt-get update && apt-get install -y --no-install-recommends \
    wget cpio sudo git zip unzip curl xterm vim bzip2 ca-certificates lsb-release && \
    rm -rf /var/lib/apt/lists/*

# ubuntu
WORKDIR /workspace/

RUN useradd -m -s /bin/bash ubuntu
RUN gpasswd -a ubuntu sudo
RUN gpasswd -a ubuntu video

USER ubuntu 
WORKDIR /workspace/
