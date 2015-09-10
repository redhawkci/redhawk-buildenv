FROM centos:6

COPY redhawk-deps.repo /etc/yum.repos.d/

RUN yum clean all && \
    yum install -y epel-release && \
    yum install -y @buildsys-build \
                   autoconf \
                   automake \
                   boost-devel \
                   expat-devel \
                   java7-devel \
                   libomniEvents2-devel \
                   libtool \
                   libuuid-devel \
                   log4cxx-devel \
                   omniORB-devel \
                   omniORBpy-devel \
                   python-devel \
                   xsd && \
    yum clean all

RUN rm -rf /etc/yum.repos.d/redhawk-deps.repo

#ONBUILD COPY . /build
#ONBUILD WORKDIR /build

CMD ["/bin/bash", "-l"]
