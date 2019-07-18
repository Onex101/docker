FROM    debian

RUN apt-get -y update
RUN apt-get install wget -y bzip2
RUN wget http://dl.4players.de/ts/releases/3.4.0/teamspeak3-server_linux_amd64-3.4.0.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.4.0.tar.bz2
RUN mkdir /home/teamspeak

RUN cd teamspeak3-server_linux_amd64
RUN mv * /home/teamspeak
RUN cd .. 
RUN rm -rf teamspeak3*
RUN	adduser --disabled-login teamspeak 
RUN	touch /home/teamspeak/.ts3server_license_accepted
RUN	chown -R teamspeak:teamspeak /home/teamspeak

ENV TS3SERVER_LICENSE=accept

EXPOSE 9987/udp 10011 30033

ENTRYPOINT sh /home/teamspeak/ts3server_minimal_runscript.sh start

# docker build . -t teamspeak
# docker run -it --name ts -p 9987:9987/udp -p 30033:30033 -p10011:10011 --rm teamspeak