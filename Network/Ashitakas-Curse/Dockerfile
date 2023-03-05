FROM ubuntu:latest

RUN apt update && apt install openssh-server sudo -y

RUN mkdir /home/LadyEboshi

RUN chmod 600 /home/LadyEboshi

RUN mkdir /home/Ashitaka

RUN useradd -rm -d /home/LadyEboshi -s /bin/bash -g root -G sudo -u 1000 LadyEboshi

RUN useradd -rm -d /home/Ashitaka -s /bin/bash -u 1001 Ashitaka

COPY 'MessageFromSan(Flag).txt' /home/LadyEboshi

RUN chown root:root /home/LadyEboshi/'MessageFromSan(Flag).txt'

RUN  echo 'LadyEboshi:Howtokillagod' | chpasswd

RUN  echo 'Ashitaka:ImHuman' | chpasswd

RUN echo "Ashitaka ALL=(ALL) NOPASSWD: /usr/bin/su" > /etc/sudoers

RUN service ssh start

RUN echo "ClientAliveInterval 160" > /etc/ssh/ssh_config

RUN echo "ClientAliveCountMax 3" > /etc/ssh/ssh_config

EXPOSE 8722

CMD ["/usr/sbin/sshd","-D"]
