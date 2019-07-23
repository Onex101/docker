# FROM ubuntu:14.04

# RUN apt-get update -y &&\
# 	apt-get upgrade -y &&\
# 	apt-get install git gcc wget sqlite3 -y


# ENV GOPATH=/home/git/go
# ENV GOROOT=/usr/local/src/go
# ENV PATH=${PATH}:$GOROOT/bin
# USER root

# RUN adduser --disabled-login --gecos 'Gogs' git
# RUN wget https://dl.google.com/go/go1.12.6.linux-amd64.tar.gz
# RUN tar -xzf go1.12.6.linux-amd64.tar.gz
# RUN mv go /usr/local/src

# RUN go get -d github.com/gogs/gogs

# WORKDIR $GOPATH/src/github.com/gogs/gogs
# RUN	go build -tags "sqlite" 
# RUN mkdir data
# RUN touch data/gogs.db
# RUN chmod 777 data/gogs.db

# USER git
# EXPOSE 3000

# ENTRYPOINT ./gogs web

FROM ubuntu

EXPOSE 3000
EXPOSE 8022

RUN apt-get update -y && apt-get upgrade -y && apt-get install git -y && apt-get install wget -y && apt-get install -y build-essential && apt-get install gcc -y

RUN wget https://dl.gogs.io/0.11.66/gogs_0.11.66_linux_amd64.tar.gz && tar -xvf gogs_0.11.66_linux_amd64.tar.gz && cd gogs

ENV USER=root

WORKDIR /gogs

ENTRYPOINT ./gogs web