FROM ubuntu:16.04
MAINTAINER Alex Asabin

RUN apt-get update

#Install utilities 
RUN apt-get install -y apt-transport-https
RUN apt-get install -y apt-utils
RUN apt-get install -y curl 
RUN apt-get install -y mc
RUN apt-get install -y software-properties-common
RUN apt-get install -y git

#Install Dot.Net
RUN curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
RUN mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
RUN sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
RUN apt-get update
RUN apt-get install -y dotnet-sdk-2.0.3
RUN apt-get update

#Install nginx
RUN add-apt-repository ppa:nginx/development
RUN apt-get update
RUN apt-get install -y nginx
ADD default /etc/nginx/sites-enabled

#Install Supervisor
RUN apt-get install -y supervisor
ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 80/tcp


