FROM centos:7
MAINTAINER Leelmes "i@chengxuan.li"

# 复制YUM配置
COPY ./files/CentOS-Base.repo /etc/yum.repos.d/
COPY ./files/epel.repo /etc/yum.repos.d/

# 处理目录
RUN mkdir -p /data1/ && echo 'PS1="\033[1m\033[36m$PS1\033[0m"' >> /etc/bashrc && echo "alias ls='ls --color'" >> /etc/bashrc && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && yum install -y vim rsync lrzsz python34 python34-setuptools && yum clean all && easy_install-3.4 pyyaml && echo "set number" >> /etc/vimrc && echo "setlocal cursorline" >> /etc/vimrc

# 设置环境变量
ENV LC_ALL en_US.UTF-8

# 工作目录
WORKDIR /data1

# 初始化脚本
CMD ["/bin/bash"]
