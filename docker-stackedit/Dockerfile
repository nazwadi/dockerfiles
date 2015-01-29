FROM centos:centos7

RUN yum update -y
RUN yum upgrade -y
RUN yum install -y git curl && curl -sL https://rpm.nodesource.com/setup | bash - \
    && yum install -y nodejs && git clone https://github.com/benweet/stackedit.git
WORKDIR stackedit

# Prevent resolution errors that have occurred when using git as the url
RUN git config --global url."https://".insteadOf git://

RUN npm install \
    && node_modules/bower/bin/bower install --allow-root --production --config.interactive=false
CMD node server.js

EXPOSE 3000
