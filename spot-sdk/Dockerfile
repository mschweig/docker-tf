# Base image which contains global dependencies
FROM ubuntu:18.04 as base
WORKDIR /workdir
ARG DEBIAN_FRONTEND=noninteractive

# System dependencies
RUN mkdir /workdir/spot && \
    apt-get -y update && \
    apt-get -y upgrade && \
    apt-get -y install \
        wget \
        build-essential \
		iputils-ping \
		python3-pip \
        checkinstall \
        libreadline-gplv2-dev \
		libncursesw5-dev \
		libssl-dev \
		libsqlite3-dev \
		tk-dev \
		libgdbm-dev \
		libc6-dev \
		libbz2-dev \
		libffi-dev \
		zlib1g-dev \
        git \
        python3-setuptools \
        libncurses5 libncurses5-dev \
		python3-pyqt5 \
		python3-pyqt4 \
        libyaml-dev libfdt1 && \
    mkdir tmp && cd tmp && \
	wget https://www.python.org/ftp/python/3.7.9/Python-3.7.9.tgz && \
	tar xzf Python-3.7.9.tgz && \
	cd Python-3.7.9 && \
	./configure --enable-optimizations && \
	make altinstall && \
	cd .. && rm -rf tmp && \
	#Install BostonDynamics SDK
	python3 -m pip install --upgrade bosdyn-client bosdyn-mission bosdyn-choreography-client \