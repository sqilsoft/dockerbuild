FROM dhub.sqil.by/testproject/ubuntu_core-2.0
MAINTAINER Alex Asabin

RUN apt-get update

#Clone OXF from github application
WORKDIR /root/projects
RUN git clone https://github.com/AlexAsabin/oxf

#Build OXF
WORKDIR /root/projects/oxf
RUN dotnet restore
RUN dotnet build

ENTRYPOINT ["/usr/bin/supervisord"]