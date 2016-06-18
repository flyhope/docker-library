FROM registry.aliyuncs.com/huati/centos:7
MAINTAINER Leelmes "chengxuan@staff.weibo.com"

# 安装GCC
RUN mkdir -p /data1/download
WORKDIR /data1/download

# 安装编译工具
RUN yum install -y wget gcc gcc-c++ make bzip2 && curl -o /data1/download/gcc-6.1.0.tar.bz2 http://mirrors.ustc.edu.cn/gnu/gcc/gcc-6.1.0/gcc-6.1.0.tar.bz2 && tar jxf gcc-6.1.0.tar.bz2 && cd /data1/download/gcc-6.1.0 && ./contrib/download_prerequisites && ./configure --enable-checking=release --enable-languages=c,c++ --disable-multilib && make -j4 && make install && yum -y erase wget gcc gcc-c++ make bzip && yum clean all && rm -Rf /data1/download

# 设置工作目录
WORKDIR /data1/
