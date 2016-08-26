#
# MAINTAINER        Terry,terry.li <libin2722@sohu.com>
# DOCKER-VERSION    1.12.1
#
# Dockerizing Nginx: Dockerfile for building Nginx images
#
#FROM       terry.com/centos7:7.2.1511
FROM		lucky.com/centos7:latest
MAINTAINER Terry.Li<libin2722@sohu.com>

#ENV TZ "Asia/Shanghai"
#ENV TERM xterm

ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo
COPY nginx-1.8.1.tar.gz nginx-1.8.1.tar.gz

RUN yum install -y gcc gcc-c++ make cmake autoconf automake && \
    yum install -y pcre-devel zlib-devel openssl openssl-devel && \
    yum clean all

RUN tar zxf nginx-1.8.1.tar.gz -C /usr/local/src/ && \
    cd /usr/local/src/ && \
    mv nginx-1.8.1 nginx && \
    cd nginx && \
    ./configure --prefix=/opt/software/nginx --with-http_ssl_module && \
    make && make install

COPY scripts/start.sh /opt/software/nginx/sbin/start.sh

RUN chmod +x /opt/software/nginx/sbin/start.sh

#RUN mkdir -p /opt/tools
#RUN mkdir -p /opt/software/nginx

#COPY nginx-1.8.1.tar.gz /opt/tools/

#RUN yum install -y gcc gcc-c++ autoconf automake && \
#    yum install -y tar zlib zlib-devel openssl openssl-devel pcre-devel && \
#    yum clean all

#RUN tar -zxvf /opt/tools/nginx-1.8.1.tar.gz -C /opt/software/
   
#RUN /opt/software/nginx-1.8.1/configure

#RUN cd /opt/software/nginx-1.8.1/

#RUN make && make install

#RUN pip install supervisor
#ADD supervisord.conf /etc/supervisord.conf

#RUN mkdir -p /etc/supervisor.conf.d && \
#    mkdir -p /var/log/supervisor

EXPOSE 80 443

#RUN /opt/software/nginx/sbin/nginx

#ENTRYPOINT ["/opt/software/nginx/sbin/start.sh"]
#ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
