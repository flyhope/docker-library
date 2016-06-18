FROM registry.aliyuncs.com/huati/centos:7
MAINTAINER Leelmes "chengxuan@staff.weibo.com"

# 安装编译工具
RUN yum install -y wget gcc gcc-c++ make bzip

# 安装GCC
RUN mkdir -p /data1/download
WORKDIR /data1/download
ADD http://mirrors.ustc.edu.cn/gnu/gcc/gcc-6.1.0/gcc-6.1.0.tar.bz2 /data1/download/
RUN tar jxf gcc-6.1.0.tar.bz2
WORKDIR /data1/download/gcc-6.1.0
RUN ./contrib/download_prerequisites
RUN ./configure --enable-checking=release --enable-languages=c,c++ --disable-multilib
RUN make -j4
RUN make install

# 清理垃圾
RUN yum -y erase wget gcc gcc-c++ make bzip
RUN yum clean all
RUN rm -Rf /data1/download
