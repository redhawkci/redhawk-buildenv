FROM ubuntu:14.04

RUN apt-get update -qq && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:redhawksdr/omnievents-2.7 && \
    apt-get update -qq && \
    apt-get install -y autoconf \
                       automake \
                       autotools-dev \
                       build-essential \
                       git \
                       gfortran \
                       libboost-dev \
                       libboost-filesystem-dev \
                       libboost-iostreams-dev \
                       libboost-regex-dev \
                       libboost-system-dev \
                       libboost-thread-dev \
                       libcos4-dev \
                       liblapack-dev \
                       liblog4cxx10-dev \
                       libomnievents-dev \
                       libomniorb4-dev \
                       libopenblas-dev \
                       libtool \
                       libxml2-utils \
                       omnievents \
                       omniidl \
                       omniidl-python \
                       omniorb \
                       omniorb-idl \
                       openjdk-7-jdk \
                       python2.7-dev \
                       python-omniorb \
                       python-numpy \
                       python-pip \
                       uuid-dev \
                       uuid-runtime \
                       xsdcxx && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install nose \
                scipy \
                unittest-xml-reporting

ENV JAVA_HOME /usr/lib/jvm/java-7-openjdk-amd64

ONBUILD RUN apt-get update -qq && \
            apt-get upgrade -y && \
            apt-get clean && \
            rm -rf /var/lib/apt/lists/*

CMD ["/bin/bash", "-l"]
