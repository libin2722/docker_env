#
# MAINTAINER        Terry.Li<libin2722@sohu.com>
# DOCKER-VERSION    1.12.1
#
# Dockerizing TOMCAT: Dockerfile for building CentOS images
#
FROM       terry.com/jdk:1.8.0
MAINTAINER Terry.Li,<libin2722@sohu.com>

ENV TOMCAT_MAJOR_VERSION 9
ENV TOMCAT_MINOR_VERSION 9.0.0.M9
ENV CATALINA_HOME /opt/tomcat
ENV APP_DIR ${CATALINA_HOME}/webapps/

ADD docker.repo /etc/yum.repos.d/docker.repo 

COPY apache-tomcat-${TOMCAT_MINOR_VERSION}.tar.gz /tmp/apache-tomcat-${TOMCAT_MINOR_VERSION}.tar.gz

RUN yum install -y vim curl wget

RUN tar -zxf /tmp/apache-tomcat-${TOMCAT_MINOR_VERSION}.tar.gz -C /opt \
    && mv /opt/apache-tomcat* /opt/tomcat 

ENTRYPOINT sh $CATALINA_HOME/bin/startup.sh && tail -f $CATALINA_HOME/logs/catalina.out

EXPOSE 8080
