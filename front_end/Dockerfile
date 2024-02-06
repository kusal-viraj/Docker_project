FROM centos:7

RUN yum -y update
RUN yum -y install curl
RUN yum install -y unzip
RUN yum install -y telnet
RUN yum install -y mariadb
RUN yum install -y net-tools
RUN curl -fsSL https://rpm.nodesource.com/setup_16.x |  bash -
RUN yum install -y nodejs

RUN mkdir -p /papertrl/apps
# Set working directory (optional)
#WORKDIR /app

COPY papertrlui-v2/. /papertrl/apps/papertrlui-v2
WORKDIR /papertrl/apps/papertrlui-v2

ENV NODE_OPTIONS="--max_old_space_size=4096"

RUN npm -f install
RUN npm install -g @angular/cli@14.2.8



# Expose default Node.js port (change if needed)
EXPOSE 4200

# Entrypoint command (optional)
CMD ["npm", "start"]
