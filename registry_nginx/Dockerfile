#
# MAINTAINER        Terry,terry.li <libin2722@sohu.com>
# DOCKER-VERSION    1.12.1
#
# Dockerizing Nginx: Dockerfile for building Nginx images
#
FROM       terry.com/centos7:7.2.1511
MAINTAINER Terry.Li<libin2722@sohu.com>

ENV TZ "Asia/Shanghai"
ENV TERM xterm

ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

RUN mkdir -p /opt/tools
RUN mkdir -p /opt/software/nginx

COPY nginx-1.8.1.tar.gz /opt/tools/

RUN yum install -y gcc gcc-c++ autoconf automake && \
    yum install -y tar zlib zlib-devel openssl openssl-devel pcre-devel && \
    yum clean all

RUN tar -zxvf /opt/tools/nginx-1.8.1.tar.gz -C /opt/software/
   
RUN /opt/software/nginx-1.8.1/configure

RUN cd /opt/software/nginx-1.8.1/

RUN make && make install

RUN pip install supervisor
ADD supervisord.conf /etc/supervisord.conf

RUN mkdir -p /etc/supervisor.conf.d && \
    mkdir -p /var/log/supervisor

EXPOSE 80

ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
