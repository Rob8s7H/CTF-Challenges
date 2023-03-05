FROM ubuntu:latest

RUN apt update && apt install socat sudo -y

RUN apt update && apt install  openssh-server sudo -y

RUN useradd -rm -d /home/ubuntu -s /bin/bash -g root -G sudo -u 1000 Tanuki

RUN  echo 'Tanuki:Password1' | chpasswd

RUN service ssh start

EXPOSE 8788

EXPOSE 8722

CMD ["socat", "TCP-LISTEN:8788,fork,reuseaddr", "EXEC:'echo utflag{P0m-p0k0-p0m-P0m}',pty,echo=0"]



