FROM debian

RUN apt-get update -y &&\
	apt-get upgrade -y &&\
	apt-get install git gcc wget -y &&\
    apt-get install libpam0g-dev -y

EXPOSE 3000

RUN adduser --disabled-login --gecos 'Gogs' git
USER root

RUN mkdir -p home/local
WORKDIR $HOME/local
RUN wget https://dl.google.com/go/go1.12.6.linux-amd64.tar.gz
RUN	tar -C /home/local -xzf go1.12.6.linux-amd64.tar.gz

ENV GOROOT=/home/local/go
ENV GOPATH=/home/projects
ENV PATH=$PATH:$GOROOT/bin:$GOPATH/bin

WORKDIR $GOPATH

RUN wget https://dl.gogs.io/0.11.66/gogs_0.11.66_linux_amd64.tar.gz
RUN tar -xvf gogs_0.11.66_linux_amd64.tar.gz

RUN	go build -o /gogs

USER root

ENTRYPOINT ./gogs web