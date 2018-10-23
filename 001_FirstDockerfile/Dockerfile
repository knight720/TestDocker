FROM centos:7
MAINTAINER ninku720@yahoo.com.tw

RUN yum install -y wget

RUN cd /

ADD jdk-8u192-linux-x64.tar.gz /

RUN wget http://apache.stu.edu.tw/tomcat/tomcat-7/v7.0.91/bin/apache-tomcat-7.0.91.tar.gz
RUN tar zxvf apache-tomcat-7.0.91.tar.gz

ENV JAVA_HOME=/jdk1.8.0_192
ENV PATH=$PATH:/jdk1.8.0_192/bin
CMD ["/apache-tomcat-7.0.91/bin/catalina.sh", "run"]