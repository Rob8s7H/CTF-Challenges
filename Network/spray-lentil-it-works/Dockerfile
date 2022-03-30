FROM ubuntu:latest

RUN apt update && apt install  openssh-server sudo -y

RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 OPayne

RUN  echo 'OPayne:Password123!' | chpasswd

RUN service ssh start

EXPOSE 8722

COPY flag.txt /home/ubuntu

CMD ["/usr/sbin/sshd","-D"]
