FROM hyperledger/fabric-orderer:1.4
RUN mkdir /var/hyperledger/bin \
 && chown -R :0 /etc/hyperledger \
 && chmod -R a+w /etc/hyperledger \
 && chown -R :0 /var/hyperledger \
 && chmod -R a+w /var/hyperledger
RUN apt-get -y update \
 && apt-get -y upgrade \
 && apt-get -y install libltdl7 \
 && apt-get -y install rsync \
 && apt-get -y install nano \
 && apt-get -y install joe \
 && apt-get -y install less\
 && apt-get -y install p7zip-full \
 && apt-get -y install tree \
 && apt-get -y install telnet
RUN echo alias ll='ls -l --color=auto' >> /etc/profile
RUN touch /.bash_history \
 && cp /root/.bash* / \
 && chown -R :0 /.bash* \
 && chmod -R g+rw /.bash* \
 && chmod -R o+r /.bash* \
 && echo PS1=\"\\[\\w\\]\\nuser@\\h:\\\\$ \" >> \.bashrc \
 && echo cd /etc/hyperledger >> /.bashrc
EXPOSE 7050
VOLUME /var/hyperledger/orderer/channel-artifacts
VOLUME /var/hyperledger/orderer/msp
VOLUME /var/hyperledger/orderer/tls
VOLUME /var/hyperledger/bin
CMD orderer start