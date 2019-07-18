FROM debian
RUN apt-get update
RUN apt-get install wget -y bzip2
RUN wget http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2
RUN tar xfvj teamspeak3-server_linux_amd64-3.4.0.tar.bz2
RUN touch ./teamspeak3-server_linux_amd64/ts3server_license_accepted

ENV TS3SERVER_LICENSE=accept

EXPOSE	9987/udp 10011 30033

ENTRYPOINT sh /teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start
