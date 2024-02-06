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
COPY umm-service.jar /papertrl/apps/umm-service.jar
EXPOSE 9003

#CMD ["java", "-jar", "/papertrl/apps/umm-service.jar", "--server.address=0.0.0.0", "--server.port=9003"]
CMD ["java", "-jar", "/papertrl/apps/umm-service.jar"]
