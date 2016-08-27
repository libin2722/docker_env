#
# MAINTAINER        Terry.Li<libin2722@sohu.com>
# DOCKER-VERSION    1.12.1
#
# Dockerizing CentOS7: Dockerfile for building CentOS images
#
FROM       centos:latest
MAINTAINER Terry.Li,<libin2722@sohu.com>

ADD aliyun-mirror.repo /etc/yum.repos.d/CentOS-Base.repo
ADD aliyun-epel.repo /etc/yum.repos.d/epel.repo

#RUN echo "192.168.58.137 tomcat.terry.com" >> /etc/hosts

RUN yum install -y nginx vim

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

#RUN sh /opt/software/nginx/start.sh

#ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
