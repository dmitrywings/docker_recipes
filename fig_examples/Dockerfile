FROM dockerfile/nodejs

RUN apt-get update && apt-get install -y \
    git \
    libxml2-dev \
    python \
    build-essential \
    make \
    gcc \
    python-dev \
    locales \
    python-pip \
    supervisor


RUN npm install -g forever
RUN npm install -g node-inspector

RUN mkdir -p /var/log/supervisor
RUN mkdir -p /data/public/logs

ADD ../../../ /opt/nodeapp/
WORKDIR /opt/nodeapp
RUN npm install

ADD ./supervisord.conf /etc/supervisor/conf.d/supervisord.conf

