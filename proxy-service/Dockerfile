FROM centos:7

RUN yum -y update && \
    yum install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel


ENV JAVA_HOME /etc/alternatives/jre

RUN yum -y install curl
RUN yum install -y unzip
RUN yum install -y telnet
RUN yum install -y mariadb
RUN yum install -y net-tools


RUN mkdir -p /papertrl/apps
COPY proxy-service.jar /papertrl/apps/proxy-service.jar
EXPOSE 8082

#CMD ["java", "-jar", "/papertrl/apps/proxy-service.jar", "--server.address=0.0.0.0", "--server.port=8082" ]
CMD ["java", "-jar", "/papertrl/apps/proxy-service.jar"]
