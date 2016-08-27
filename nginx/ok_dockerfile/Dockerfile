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

#RUN yum install yum-fastestmirror && \
#    yum install -y curl wget tar gzip zlib zlib-devel openssl openssl-devel pcre-devel bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \ 
#    yum install -y gcc gcc-c++ git make automake autofonf cmake patch logrotate python-devel libpng-devel libjpeg-devel && \
#    yum install -y --enablerepo=epel pwgen python-pip && \
#    yum install -y nginx && \
#    yum clean all

#RUN pip install supervisor

#ADD supervisord.conf /etc/supervisord.conf

#RUN mkdir -p /etc/supervisor.conf.d && mkdir -p /var/log/supervisor

#RUN mkdir -p /opt/software/nginx

#COPY start.sh /opt/software/nginx/

#RUN chmod +x /opt/software/nginx/start.sh

RUN yum install -y nginx

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

#RUN sh /opt/software/nginx/start.sh

#ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c", "/etc/supervisord.conf"]
