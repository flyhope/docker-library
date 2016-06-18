FROM centos:7
MAINTAINER Leelmes "i@chengxuan.li"

# 复制YUM配置
COPY ./files/CentOS-Base.repo /etc/yum.repos.d/
COPY ./files/epel.repo /etc/yum.repos.d/

# 处理目录
RUN mkdir -p /data1/

# 设置特定头颜色
RUN echo 'PS1="\033[1m\033[36m$PS1\033[0m"' >> /etc/bashrc

# 设置颜色
RUN echo "alias ls='ls --color'" >> /etc/bashrc

# 设置环境变量
ENV LC_ALL en_US.UTF-8

# 设置时区为中国时区
RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime

# 工作目录
WORKDIR /data1

# 初始化脚本
CMD ["/bin/bash"]
