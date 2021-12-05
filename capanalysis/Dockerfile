FROM ubuntu:xenial-20180705
LABEL MAINTAINER="Laith <laith@bayt.cloud>"
# Set the working directory to /root
WORKDIR /root
VOLUME "/root/src"
ENV http_proxy ""
ENV ftp_proxy ""
ENV TZ=America/Toronto
EXPOSE 9877

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Install packages
ENV DEBIAN_FRONTEND noninteractive 

RUN apt-get update && \ 
    apt-get -y install wget apt-utils gdebi php postgresql apache2 whois sudo 
RUN wget https://sourceforge.net/projects/capanalysis/files/version%201.2.2/capanalysis_1.2.2_amd64.deb 
RUN gdebi --n capanalysis_1.2.2_amd64.deb 
RUN apt-get clean && \ 
    rm -rf /var/lib/apt/lists*

RUN echo '#!/bin/sh' > /usr/sbin/policy-rc.d \
    && echo 'exit 101' >> /usr/sbin/policy-rc.d \
    && chmod +x /usr/sbin/policy-rc.d

RUN sed -i -e 's/PRIORITY=1 #(0..20)/PRIORITY=0 #(0..20)Z/g' /etc/init.d/capanalysis

CMD service postgresql restart && \
    service apache2 restart && \
    service capanalysis restart && \
    tail -f /var/log/apache2/access.log
