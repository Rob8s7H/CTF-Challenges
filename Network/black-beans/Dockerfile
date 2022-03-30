FROM ubuntu:latest
    
RUN apt update && apt install openssh-server sudo -y

RUN mkdir /home/admin

RUN chmod 776 /home/admin

RUN useradd -rm -d /home/admin -s /bin/bash -g root -G sudo -u 1000 admin

RUN mkdir /home/scotty

RUN useradd -d /home/scotty scotty

RUN  echo 'scotty:beanmeup!' | chpasswd

RUN  echo 'admin:coffee' | chpasswd

RUN service ssh start

COPY flag.txt /home/admin

RUN chmod 774 /etc/passwd

RUN chmod 774 /etc/shadow

EXPOSE 8822/tcp

CMD ["/usr/sbin/sshd","-D"]
