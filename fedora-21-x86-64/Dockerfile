FROM fedora:21
MAINTAINER Alan Franzoni username@franzoni.eu
ADD files/etc/yum.conf /etc/
RUN sed -i.original -e 's/^/#/' /etc/yum.repos.d/*.repo
ADD files/etc/rpm/macros.drb /etc/rpm/macros.drb
ADD files/tmp /tmp
RUN rpm --import  /tmp/*.txt
RUN yum install deltarpm
RUN yum clean metadata
RUN yum update
RUN yum install @buildsys-build yum-utils rpm-sign gnupg
