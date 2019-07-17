FROM debian
RUN apt-get update
RUN apt-get install wget -y bzip2
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar xfvj teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN touch ./teamspeak3-server_linux_amd64/ts3server_license_accepted
RUN ./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh start
RUN ./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh status