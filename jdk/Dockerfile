#
# MAINTAINER        Terry.Li<libin2722@sohu.com>
# DOCKER-VERSION    1.12.1
#
# Dockerizing JDK: Dockerfile for building CentOS images
#
FROM       centos:latest
MAINTAINER Terry.Li,<libin2722@sohu.com>

ENV JAVA_VERSION 1.8.0
ENV JDK_HOME /usr/lib/jvm/java-${JAVA_VERSION}-openjdk
ENV JRE_HOME /usr/lib/jvm/jre-${JAVA_VERSION}-openjdk

ADD docker.repo /etc/yum.repos.d/docker.repo

RUN yum install -y java-${JAVA_VERSION}-openjdk java-${JAVA_VERSION}-openjdk-devel
