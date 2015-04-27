FROM ubuntu:14.04

# Install.
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  apt-get update && \
  apt-get -y upgrade && \
  apt-get install -y build-essential && \
  apt-get install -y software-properties-common git && \
  apt-get install -y libreadline-dev libsqlite3-dev libbz2-dev libssl-dev wget python-gdbm libffi-dev libxml2-dev libxslt1-dev 

RUN \
  wget https://www.python.org/ftp/python/3.4.3/Python-3.4.3.tgz && \
  tar xvfz Python-3.4.3.tgz

RUN cd Python-3.4.3 && \
  ./configure && \
  make -j && \
  make install

RUN wget ftp://ftp.gnu.org/gnu/gdbm/gdbm-1.11.tar.gz && \
    tar xfz gdbm-1.11.tar.gz && \
    cd gdbm-1.11 && \
    ./configure && \
    make && \
    make install

RUN wget https://bootstrap.pypa.io/get-pip.py && \
  python3 get-pip.py && \
  pip3 install virtualenv && \
  rm -rf Python-3.4.3 Python-3.4.3.tgz get-pip.py gdbm-1.11 gdbm-1.11.tar.gz

RUN virtualenv /env

