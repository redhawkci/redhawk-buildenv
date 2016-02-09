FROM centos:6

COPY redhawk-deps.repo /etc/yum.repos.d/

RUN touch /var/lib/rpm/* && \
    yum update -y && \
    yum install -y epel-release && \
    yum install -y @buildsys-build \
                   ant-junit \
                   autoconf \
                   automake \
                   boost-devel \
                   cppunit-devel \
                   curl-devel \
                   expat-devel \
                   gettext-devel \
                   java7-devel \
                   junit4 \
                   lapack-devel \
                   libomniEvents2-devel \
                   libtool \
                   libuuid-devel \
                   log4cxx-devel \
                   octave-devel \
                   omniORB-devel \
                   omniORB-utils \
                   omniORBpy-devel \
                   openssl-devel \
                   perl-devel \
                   perl-ExtUtils-MakeMaker \
                   python-devel \
                   valgrind \
                   xsd \
                   yum-utils \
                   zlib-devel && \
    yum clean all

RUN rm -rf /etc/yum.repos.d/redhawk-deps.repo

RUN curl --silent --show-error --retry 5 https://bootstrap.pypa.io/get-pip.py | python && \
    pip install jinja2 \
                nose \
                'numpy<1.9.0' \
                scipy \
                unittest-xml-reporting

RUN curl -fsSL https://www.kernel.org/pub/software/scm/git/git-2.7.0.tar.gz | tar xzf - -C /usr/src && \
    cd /usr/src/git-2.7.0 && \
    make prefix=/usr/local all && \
    make prefix=/usr/local install && \
    rm -rf /usr/src/git-2.7.0

COPY omniORB.cfg /etc/

CMD ["/bin/bash", "-l"]
