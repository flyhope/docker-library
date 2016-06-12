FROM centos:6
MAINTAINER Leelmes "i@chengxuan.li"

# 复制YUM配置
COPY ./files/CentOS-Base.repo /etc/yum.repos.d/
COPY ./files/epel.repo /etc/yum.repos.d/

# 处理目录
RUN mkdir -p /data1/

# 设置特定头颜色
RUN echo 'PS1="\033[1m\033[36m$PS1\033[0m"' >> /etc/bashrc

# 工作目录
WORKDIR /data1

# 初始化脚本
CMD ["/bin/bash"]
