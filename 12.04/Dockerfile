FROM       ubuntu:12.04
MAINTAINER Andrew Beveridge "https://github.com/beveradb"

RUN apt-get update

RUN apt-get install -y openssh-server git wget vim php sshpass
RUN mkdir /var/run/sshd

RUN echo 'root:root' |chpasswd

RUN sed -ri 's/^PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

EXPOSE 22

CMD    ["/usr/sbin/sshd", "-D"]
