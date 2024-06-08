FROM lscr.io/linuxserver/bookstack:latest
WORKDIR /app/

COPY ./config/init_container.sh /app/
 # Start and enable SSH
RUN apk add openssh
RUN echo "root:Docker!" | chpasswd 
RUN chmod +x /app/init_container.sh 
RUN cd /etc/ssh/ 
RUN ssh-keygen -A

COPY ./config/sshd_config /etc/ssh/


EXPOSE  2222 80 443
ENTRYPOINT [ "/app/init_container.sh" ]

