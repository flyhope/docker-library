FROM flyhope/centos:7
MAINTAINER Leelmes "i@chengxuan.li"

# 安装GCC
RUN mkdir -p /data1/download

# 安装编译工具
RUN cd /data1/download && \
	yum update -y && \
    yum install -y wget gcc gcc-c++ make xz && \
    echo "Download gcc" && \
    wget -q -O /data1/download/gcc-8.2.0.tar.xz http://www.netgull.com/gcc/releases/gcc-8.2.0/gcc-8.2.0.tar.xz && \
    echo "Unpack gcc" && \
    tar xf gcc-*.xz && cd /data1/download/gcc-* && \
    ./contrib/download_prerequisites && \
    ./configure --enable-checking=release --enable-languages=c,c++ --disable-multilib && \
    make -j4 && \
    make install && \
    yum -y erase wget gcc gcc-c++ bzip && \
    yum clean all && \
    cd /data1 && \
    rm -Rf /data1/download

# 设置工作目录
WORKDIR /data1/
