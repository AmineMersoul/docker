FROM debian
RUN apt-get update -y && apt-get upgrade -y && \
    apt-get install bzip2 wget -y && \
    wget http://dl.4players.de/ts/releases/3.5.0/teamspeak3-server_linux_amd64-3.5.0.tar.bz2 && \
    tar xfvj teamspeak3-server_linux_amd64-3.5.0.tar.bz2 && \
    cd teamspeak3-server_linux_amd64 && \
    touch .ts3server_license_accepted
CMD ["sh", "teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# docker run -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ts_image