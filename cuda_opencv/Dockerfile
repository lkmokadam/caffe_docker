FROM nvidia/cuda:8.0-cudnn6-devel-ubuntu16.04
LABEL maintainer lkmokadam[at]gmail[dot]com

RUN apt-get update && apt-get install -y unzip

RUN apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        cmake \
        git \
        wget \
        libatlas-base-dev \
        libboost-all-dev \
        libgflags-dev \
        libgoogle-glog-dev \
        libhdf5-serial-dev \
        libleveldb-dev \
        liblmdb-dev \
        libopencv-dev \
        libprotobuf-dev \
        libsnappy-dev \
        protobuf-compiler \
        python-dev \
        python-numpy \
        python-pip \
        python-setuptools \
        python-scipy && \
    rm -rf /var/lib/apt/lists/*

RUN cd /tmp && \
	wget https://github.com/opencv/opencv/archive/3.2.0.zip && \
	unzip 3.2.0.zip && \
	rm 3.2.0.zip && \
	mv opencv-3.2.0 OpenCV && \
	cd OpenCV && \
	mkdir build && \
	cd build && \
	cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local .. && \
	make -j4  && \
	make install && \
        ldconfig
RUN rm -rf /tmp/*


