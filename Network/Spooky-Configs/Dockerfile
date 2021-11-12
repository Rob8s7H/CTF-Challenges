FROM ubuntu:latest
    
RUN apt update && apt install openssh-server sudo -y

RUN apt install proftpd -y

RUN mkdir /home/dpumpkins

RUN chmod 776 /home/dpumpkins

RUN useradd -rm -d /home/dpumpkins -s /bin/bash -g root -G sudo -u 1000 dpumpkins

RUN mkdir /home/wcoldwater

RUN useradd -d /home/wcoldwater wcoldwater

RUN  echo 'wcoldwater:CHANGEME!' | chpasswd

RUN  echo 'dpumpkins:zxcvbnm' | chpasswd

RUN service ssh start

COPY proftpd.conf /etc/proftpd/

COPY flag1.txt /srv/ftp/

COPY welcome.msg /srv/ftp/

COPY newusers.txt /srv/ftp/

COPY so-spoopy.jpg /srv/ftp

COPY flag2.txt /home/wcoldwater

COPY flag3.txt /home/dpumpkins

COPY dpumpkins.jpg /home/dpumpkins

RUN service proftpd start

RUN chmod 774 /etc/passwd

RUN chmod 774 /etc/shadow

EXPOSE 22/tcp 21/tcp

CMD ["/usr/sbin/sshd","-D"]
