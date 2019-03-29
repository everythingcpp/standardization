FROM centos:7.6.1810
LABEL maintainer="Robert Dougls <rwdougla@gmail.com>"

ENV GCC_VERSION "cxx-modules"

RUN yum install -y \
        gcc gcc-c++ flex make time vim svn gmp gmp-devel mpfr mpfr-devel libmpc libmpc-devel

RUN mkdir /gcc_build && cd /gcc_build

RUN svn co svn://gcc.gnu.org/svn/gcc/branches/c++-modules

RUN mkdir build && cd build && ../c++-modules/configure --disable-multilib  --enable-languages=c,c++ && make -j 6 && make install

